---
layout: default
title: R and Python code snippets to remove EU responses from your microdata
nav_order: 6
parent: Notices and Updates
---

## How to remove EU responses that have reached the retention deadline in R

This sample R code can remove EU responses in the microdata that have reached the 2-year retention deadline. These responses will be removed from the microdata CSV by specifying the file path and date to remove. The output will rewrite the origin file.
```r

# Load packages needed
library(tidyverse)
library(lubridate)

# First specify which data set you would like to clean
filepath <- "FilePathToCTISData.csv"

# Import the data
CTISData <- read_csv(filepath)

# Determine current cutoff date
CurrentCutoffDate = ymd(Sys.Date()) - years(2)

# List of countries affected
CountryList <- 
  c("Austria","Belgium","Bulgaria", "Croatia", "Cyprus", "Czech Republic", 
  "Denmark", "Estonia",  "Finland", "France", "Germany","Greece", "Hungary", 
  "Ireland", "Italy",  "Latvia",  "Lithuania",  "Luxembourg", "Malta",  
  "Netherlands",  "Poland", "Portugal", "Romania",  "Slovakia", "Slovenia", 
  "Spain","Sweden", "United Kingdom",  "Iceland",  "Norway",  "Andorra", 
  "Switzerland")

CTISData <- CTISData %>%
  # Default when importing the data is UTC for readr, 
  # but the dates were recorded in GMT-7 (America/Los Angeles)
  mutate(RecordedDate = force_tz(RecordedDate, "America/Los_Angeles")) %>%
  filter(
    # Individual data from ROW will be kept for all dates
    # Individual data from EU not older than two years will be kept
    survey_region == "ROW" & !(country_agg %in% CountryList)| 
    survey_region == "EU" & RecordedDate > CurrentCutoffDate |
    country_agg %in% CountryList & RecordedDate > CurrentCutoffDate
    )

# Save your data
write_csv(x = CTISData, file = filepath)

```

## How to remove EU responses that have reached the retention deadline in Python
This sample Python code can remove EU responses in the microdata that have reached the 2-year retention deadline. These responses will be removed from the microdata CSV by specifying the file path and the date range to remove. The output will rewrite the origin file.

```py
from datetime import date, timedelta
import re, gzip
import pandas as pd


######## DATES TO BE REMOVED FROM THE EUROPEAN DATA ##########
# survey start date
sdate = date(2020, 4, 23)   
# set end date, default 2 years age. for custom dates: use edate = date(year,month,day) like sdate
today =  date.today()
edate = today.replace(year=today.year-2) 

delta = edate - sdate       # as timedelta
dates_to_be_removed=[]
for i in range(delta.days + 1):
    day = sdate + timedelta(days=i)
    dates_to_be_removed.append(str(sdate + timedelta(days=i)))
list(dates_to_be_removed)




EU_Countries = ['Austria','Belgium','Bulgaria','Croatia','Cyprus','Czech Republic','Denmark','Estonia','Finland','France','Germany','Greece','Hungary','Ireland','Italy','Latvia','Lithuania','Luxembourg','Malta','Netherlands','Poland','Portugal','Romania','Slovakia','Slovenia','Spain','Sweden','United Kingdom','Iceland','Norway','Andorra','Switzerland']
EU_Countries

####### PATH INDICATING THE LOCATION OF THE FILES ####### 
data_path = '/path/to/survey_microdata/v1.7/2020/04/'

glob.glob(data_path+"*.gz")

############ LIST ALL THE FILES IN THE DIRECTORY ENDING WITH .gz ############
import glob
list_of_files = []
for file in sorted(glob.glob(data_path+"*.gz")):
    list_of_files.append(str(file).replace(data_path,""))
list_of_files 


for file in list_of_files:
    print("Processing file: ",str(file))
    DF = pd.read_csv(data_path+file)
    DF = DF.join(DF['RecordedDate'].str.split(' ', expand=True).rename(columns={0:'Date', 1:'Time'}))     
    DF = DF.drop(DF[((DF["survey_region"]=="EU")|(DF["country_agg"].isin(EU_Countries))) & (DF["Date"].isin(dates_to_be_removed))].index)
    DF = DF.drop(['Date', 'Time'], axis=1)
    DF.to_csv(data_path+file,index=False)

```