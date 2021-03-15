---
layout: default
title: Retrieve data from the API using R
nav_order: 1
parent: Tutorials
---

## How to use this API in R

This sample code gets `smoothed` `covid` data for `France` between `11/15/2020` and `11/30/2020`
```
library(tidyverse)
library(httr)
library(jsonlite)

# add url
path <- "https://covidmap.umd.edu/api/resources?indicator=covid&type=smoothed&country=France&daterange=20201115-20201130"

# request data from api
request <- GET(url = path)

# make sure the content is encoded with 'UTF-8'
response <- content(request, as = "text", encoding = "UTF-8")

# now we have a dataframe for use!
coviddata <- fromJSON(response, flatten = TRUE) %>% data.frame()
```