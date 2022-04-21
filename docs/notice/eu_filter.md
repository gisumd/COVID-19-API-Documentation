---
layout: default
title: R and Python code snippets to remove EU responses from your microdata
nav_order: 6
parent: Notices and Updates
---

## How to remove EU response in R

This sample R code can remove the EU responses from the microdata CSV by specifying the file path and date to remove. The output will rewrite the origin file.
```r
library(readr)
library(tidyverse)
library(lubridate)
CountryList <- 
  c("Austria","Belgium","Bulgaria", "Croatia", "Cyprus", "Czech Republic", 
    "Denmark", "Estonia",  "Finland", "France", "Germany","Greece", "Hungary", 
    "Ireland", "Italy",  "Latvia",  "Lithuania",  "Luxembourg", "Malta",  
    "Netherlands",  "Poland", "Portugal", "Romania",  "Slovakia", "Slovenia", 
    "Spain","Sweden", "United Kingdom",  "Iceland",  "Norway",  "Andorra", 
    "Switzerland")

# Define cutoff date
CurrentCutoffDate = as.Date("2020-05-04")

# Set file folder path
setwd("path to your data folder")

# Fetch file list
paths<-list.files(pattern = ".csv.gz$", recursive = TRUE)
allfiles<-length(paths)
count=0

#Loop to filter
for (path in paths){
  count= count+1
  filepath<-path
  CTISData <- read_csv(filepath,show_col_types = FALSE,progress = FALSE)
  CTISData <- CTISData %>%
    # Make sure you use the correct timezone
    mutate(RecordedDate = force_tz(RecordedDate, "America/Los_Angeles")) %>%
    filter(
      # Individual data from ROW will be kept for all dates
      survey_region == "ROW"| 
        # Individual data from EU not older than two years will be kept
        survey_region == "EU" & RecordedDate > CurrentCutoffDate |
        country_agg %in% CountryList & RecordedDate > CurrentCutoffDate
    )
  # Showing progress
  cat("Currently processing ",count, " out of ", allfiles,"files. \n")
  # Save your data
  write_csv(x = CTISData, file = filepath,progress = FALSE)
}
```

## How to remove EU response in Python

This sample Python code can remove the EU responses from the microdata CSV by specifying the file path and date to remove. The output will rewrite the origin file.
```py
from datetime import date, timedelta
import re, gzip
import pandas as pd


######## DATES TO BE REMOVED FROM THE EUROPEAN DATA ##########

sdate = date(2020, 4, 23)   # start date
edate = date(2020, 5, 23)   # end date

delta = edate - sdate       # as timedelta
dates_to_be_removed=[]
for i in range(delta.days + 1):
    day = sdate + timedelta(days=i)
    dates_to_be_removed.append(str(sdate + timedelta(days=i)))
list(dates_to_be_removed)




EU_Countries = ['Austria','Belgium','Bulgaria','Croatia','Cyprus','Czech Republic','Denmark','Estonia','Finland','France','Germany','Greece','Hungary','Ireland','Italy','Latvia','Lithuania','Luxembourg','Malta','Netherlands','Poland','Portugal','Romania','Slovakia','Slovenia','Spain','Sweden','United Kingdom','Iceland','Norway','Andorra','Switzerland']
EU_Countries

####### PATH INDICATING THE LOCATION OF THE FILES ####### 
data_path = '/gpfs/data1/cgis1gp/covid_survey_data_warehouse/survey_microdata/micro_release_gz/v1.7/2020/04/'

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