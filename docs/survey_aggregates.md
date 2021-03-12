---
layout: default
title: Survey Aggregates
nav_order: 4
---

# Survey Aggregates

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

Wildcard characters `%` and `_` are enabled for `country` and `region`. See requests section for examples.  
If you prefer to use `iso_code` , `gid_0` and `gid_1` , you can use our [lookup table](https://covidmap.umd.edu/country_region_codes.csv) to convert country names or region names into the geocodes you prefer.  
**Note:** the upper limit of returned records of a query is 3600. Users will receive a status message at the end of the JSON data saying, "data truncated when the upper limit is reached."