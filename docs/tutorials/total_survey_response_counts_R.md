---
layout: default
title: Retrieve total survey response counts from the API using R
nav_order: 4
parent: Tutorials
---

## How to Retrieve the Total Number of Survey Responses using R

Using R you can retrieve the total number of responses for Part-A and Full survey responses. 

This sample code gets and calculates the total number of responses from the start of the survey to the latest available date. 

```r
library(tidyverse)
library(httr)
library(jsonlite)

# Get latest survey date
# latest_date = today - 2 days 
latest_date <- Sys.Date() - 2
latest_date <- format(latest_date, "%Y%m%d")

# request survey response count data from api form start of the survey to latest available date
# Start = 4/23/2020
url <- paste0("https://covidmap.umd.edu/api/counts?daterange=20200423-", latest_date)
request <- GET(url = url)

# make sure the content is encoded with 'UTF-8'
response <- content(request, as = "text", encoding = "UTF-8")

# get a dataframe to use
coviddata <- fromJSON(response, flatten = TRUE) %>% data.frame()

# Get total part-a and full survey responses
parta_responses = sum(coviddata$data.parta_responses)
full_responses = sum(coviddata$data.full_responses)

# print totals
cat("Part-A Responses: ", parta_responses)
cat("Full Responses: ", full_responses)
```