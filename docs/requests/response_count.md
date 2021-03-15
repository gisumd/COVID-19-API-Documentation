---
layout: default
title: Retrieve survey reponse counts
nav_order: 5
parent: Requests
---

# Reponse Count
To get Part-A and Full survey response counts you need to make a call to the following URL:
`https://covidmap.umd.edu/api/counts?date={date}`

For example, to get the survey repsonse count for `1/29/2021` use:
`https://covidmap.umd.edu/api/counts?date=20210129`

```
{"data":
 [
    {
        "parta_responses": 120007.0,
        "full_responses": 119229.0,
		"survey_date": 20210129
    }
 ], "status":"success"
}
```


