---
layout: default
title: Retrieve survey dates
nav_order: 2
parent: Requests
---

## Retrieve all dates for survey responses for a particular place
To retrieve the available dates for a country use:

`https://covidmap.umd.edu/api/datesavail?country={country}`

Example to get the available dates for `Paraguay` use:
`https://covidmap.umd.edu/api/datesavail?country=Paraguay`

```
{"data":
 [
    {
        "country": "Paraguay",
        "survey_date": "20200423"
    },
    {
        "country": "Paraguay",
        "survey_date": "20200424"
	},
	...
 ]
}
```

To retrieve the available dates for a region use:

`https://covidmap.umd.edu/api/datesavail?country={country}&region={region}`

Example to get the available dates for `Magdalena, Colombia` use:
`https://covidmap.umd.edu/api/datesavail?country=Colombia&region=Magdalena`

```
{"data":
 [
    {
        "country": "Colombia",
        "region": "Magdalena",
        "survey_date": "20200423"
    },
    {
        "country": "Colombia",
        "region": "Magdalena",
        "survey_date": "20200424"
	},
	...
 ]
}
```
