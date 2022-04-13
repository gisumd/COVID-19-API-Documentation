---
layout: default
title: Get Started
nav_order: 2
---

# Get Started

## An open API from the University of Maryland
This is an API for accessing the daily COVID-19 World Symptoms Survey data. 
The details of our methodology, disclaimer, and release log can be checked [here](https://covidmap.umd.edu/methodology.html).

Data calculated based on the Facebook global symptoms survey data. Using the survey data, we estimate the percentage of people in a given country or region.

**The base path.** All URLs referenced in the documentation have the base path `https://covidmap.umd.edu/apiv2/`

**The endpoint path.** For example, `resources?indicator={indicator}&type={type}&country={country}&date={date}`

**Required parameters.** These parameters must be included in a request. In the example above, `{indicator}`, `{type}`, and `{country}`are required. `{date}`,`{daterange}` and `{region}` are optional. In a request, you will replace the placeholders with real values. Checkout the API usages in the [Survey Aggregates]({{ site.baseurl }}{% link docs/survey_aggregates.md %}) page.

**Optional parameters.** These additional parameters can be included to customize a query to get regional aggregates, smoothed aggregates, all regions, etc.

### Example
`https://covidmap.umd.edu/apiv2/resources?indicator=covid&type=smoothed&country=Italy&date=20201110`

```
{"data":
  [
    {
      "country":"Italy",
      "survey_date":"20201110",
      "indicator":"covid",
      "sample_size":30879,
      "pct":0.00924,
      "se":0.000759
    }
  ]
}
```

