---
layout: default
title: Survey Aggregates
nav_order: 4
---

# Survey Aggregates

---
**Note:** Aggregates for the API, map, and survey results page are shown for **weighted countries only**. Please find the complete list of countries that are weighted by Facebook [here](https://covidmap.umd.edu/CTIS_Weighted_Country_List.xlsx).  
Microdata files include both weighted and unweighted countries. For more information on how to gain access to the microdata go [here](https://dataforgood.fb.com/docs/covid-19-symptom-survey-request-for-data-access/).

---

To get aggregates you need to make a call to the following url:

`https://covidmap.umd.edu/api/resources?indicator={indicator}&type={type}&country={country}&date={date}`

### Query Parameters

| Parameter    | Description                                       | Example |
|:-------------|:--------------------------------------------------|:--------|
| indicator    | Aggregate data to query                           | `covid`, `mask`, `vaccine_acpt`    |
| type         | Aggregate data type to use                        | `daily` or `smoothed`    |
| country      | Country to query aggregates for                   | `Italy`, `Colombia`, `Autralia`     |
| region       | Region to query aggregates for                    | (optional) `Piemonte`, `Santander`, `New South Wales`    |
| date         | Used to query aggregate data for a specific day   | `20210101`    |
| daterange    | Used to query aggregates data within a time range | (optional) `20210101-20210115`    |

The mandatory parameters here are `indicator`, `type`, `country`, and `date`.  
Set `country` to `all` to retrieve data for all countries.  
Set `region` to `all` to retrieve data for all regions for a specific country.  
Set both `country` and `region` to `all` to retrieve all data.  

Wildcard characters `%` and `_` are enabled for `country` and `region`. See [Requests]({{ site.baseurl }}{% link docs/requests/requests.md %}) section for examples.

If you prefer to use `iso_code` , `gid_0` and `gid_1` , you can use our [lookup table](https://covidmap.umd.edu/country_region_codes.csv) to convert country names or region names into the geocodes you prefer.  

**Note:** the upper limit of returned records of a query is 3600. Users will receive a status message at the end of the JSON data saying, "data truncated when the upper limit is reached."