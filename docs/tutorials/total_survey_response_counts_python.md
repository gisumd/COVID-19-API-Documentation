---
layout: default
title: Retrieve total survey response counts using Python
nav_order: 3
parent: Tutorials
---

## How to Retrieve the Total Number of Survey Responses using Python

Using Python you can retrieve the total number of responses for Part-A and Full survey responses. 

This sample code gets and calculates the total number of responses from the start of the survey to the latest available date. 

```py
import pandas
import json
import requests
import datetime

# Get latest survey date
# latest_date = today - 2 days 
today = datetime.datetime.now()
n_days_ago = datetime.timedelta(days = 2)
latest_date = today - n_days_ago
latest_date = latest_date.strftime('%Y%m%d')

# request survey response count data from api form start of the survey to latest available date
# Start = 4/23/2020
response = requests.get(f"https://covidmap.umd.edu/api/counts?daterange=20200423-{latest_date}").text

# convert json data to dic data for use
jsonData = json.loads(response)

# convert to pandas dataframe
df = pd.DataFrame.from_dict(jsonData['data'])

# Get total part-a and full survey responses
parta_responses = sum(df.parta_responses)
full_responses = sum(df.full_responses)

print("Part-A Responses:", parta_responses)
print("Full Responses:", full_responses)
```