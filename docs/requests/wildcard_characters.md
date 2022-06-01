---
layout: default
title: Response data using wildcard characters
nav_order: 4
parent: Requests
---

# Retrieve data using wildcard characters
A wildcard character is a special character that represents one or more other characters.
- `%` matches any sequence of zero of more characters or numbers.
- `_` matches any single character or number.

To retrieve data using the `%` character:

The following will return data for the `appointment_have` indicator for any countries whose name starts with `United` on `20210307`:

`https://covidmap.umd.edu/api/resources?indicator=appointment_have&type=daily&country=United%&date=20210307`

```
{"data":
 [
	{"pct_appointment_have": 0.084841},
    {"appointment_have_se": 0.031799},
    {"pct_appointment_have_unw": 0.131579},
    {"appointment_have_se_unw": 0.026213},
    {"sample_size": 114.0},
    {"country": "United Arab Emirates"},
    {"iso_code": "ARE"},
    {"gid_0": "ARE"},
    {"survey_date": "20210307"},
        
    {"pct_appointment_have": 0.109083},
    {"appointment_have_se": 0.008475},
    {"pct_appointment_have_unw": 0.107623},
    {"appointment_have_se_unw": 0.008526},
    {"sample_size": 1338.0},
    {"country": "United Kingdom"},
    {"iso_code": "GBR"},
    {"gid_0": "GBR"},
    {"survey_date": "20210307"},
 ], "status":"success"
}
```

To retrieve data using the `_` character:

The following will return all the dates for survey responses for any countries with a six-character name where the first three characters are `g`, `r`, `e` and the last two characters are `c`, `e`.

`https://covidmap.umd.edu/api/datesavail?country=gre_ce`

```
{"data": 
 [
    {
        "country": "Greece",
        "survey_date": "20200423"
    },
    {
        "country": "Greece",
        "survey_date": "20200424"
    },
    ...
    {
        "country": "Greece",
        "survey_date": "20200425"
    },
    ...
 ]
    "status": "success"
}
```
