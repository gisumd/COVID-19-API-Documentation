---
layout: default
title: Retrieve data from the API using Python
nav_order: 2
parent: Tutorials
---

## How to use this API in Python

This sample code gets `smoothed` `covid` data for `France` between `11/15/2020` and `11/30/2020`
```py
import requests
import json
import pandas

# request data from api
response = requests.get("https://covidmap.umd.edu/api/resources?indicator=covid&type=smoothed&country=France&daterange=20201115-20201130").text

#convert json data to dic data for use!
jsonData = json.loads(response)

# convert to pandas dataframe
df = pandas.DataFrame.from_dict(jsonData['data'])
```