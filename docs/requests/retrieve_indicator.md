---
layout: default
title: Retrieve data for a particular indicator
nav_order: 3
parent: Requests
---

## Retrieve data for a particular indicator
To retrive data for an indicator for a country:

Specify the `indicator`, the `type`, the `country`, and a `date` or `daterange`.

For example, to get the `daily` data for the `mask` indicator for the country of `Finland` from `9/21/2020` to `10/6/2020` use:
`https://covidmap.umd.edu/api/resources?indicator=mask&type=daily&country=Finland&daterange=20201201-20201204`

```
{"data":
 [
    {
        "percent_mc": 0.728795,
        "mc_se": 0.021479,
		"percent_mc_unw": 0.725173,
		"mc_se_unw": 0.02139,
		"sample_size": 433.0,
		"country": Finland,
		"iso_code": FIN,
		"gid_0": FIN,
		"survey_date": "20201201"
    },
	...
    {
        "percent_mc": 0.0.76261,
        "mc_se": 0.019669,
		"percent_mc_unw": 0.750515,
		"mc_se_unw": 0.01934,
		"sample_size": 485.0,
		"country": Finland,
		"iso_code": FIN,
		"gid_0": FIN,
		"survey_date": "20201204"
	}
 ]
}
```

To retrive data for an indicator for a region:

Specify the `indicator`, the `type`, the `country`, the `region`, and a `date` or `daterange`.

For example, to get the `daily` data for the `covid` indicator for the country of `Saint Petersburg, Russia` from `1/1/2021` to `1/3/2021` use:
`https://covidmap.umd.edu/api/resources?indicator=covid&type=daily&country=Russia&region=Saint%20Petersburg&daterange=20210101-20210103`
```
{"data":
 [
    {
        "percent_cli": 0.055563,
        "cli_se": 0.027017,
		"percent_cli_unw": 0.058442,
		"cli_se_unw": 0.018903,
		"sample_size": 154.0,
		"country": Russia,
		"region": Saint Petersburg,
		"iso_code": RUS,
		"gid_0": RUS,
		"gid_1": RUS.14_1",
		"survey_date": "20210101"
    },
	...
    {
        "percent_cli": 0.020649,
        "cli_se": 0.014852,
		"percent_cli_unw": 0.02649,
		"cli_se_unw": 0.013068,
		"sample_size": 151.0,
		"country": Russia,
		"region": Saint Petersburg,
		"iso_code": RUS,
		"gid_0": RUS,
		"gid_1": RUS.14_1,
		"survey_date": "20210103"
	}
 ], "status":"success"
}
```