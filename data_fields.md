---
layout: default
title: Data Fields
nav_order: 5
---

# Data Fields

Data fields returned form an API query

| Field              | Description          |
|:-------------------|:---------------------|
| country            | Country name         |
| region             | Sub-country region name. Generally, it is at the state or province-level or equivalent         |
| pct\_*             | Sub-country region name. Generally, it is at the state or province-level or equivalent         |
| pct\_\*\_unw       | Sub-country region name. Generally, it is at the state or province-level or equivalent         |
| smoothed\_\*       | Seven-day rolling average of pct\_\*         |
| \*\_se             | Standard error of pct\_\*                    |
| \*\_se\_unw        | Standard error of pct\_\*\_unw               |
| smoothed\_\*\_se   | Seven-day rolling average of pct\_\*         |
| sample\_size\_\*   | Sample size for calculating the targeted indicator value         |
| iso\_code          | The ISO country codes are internationally recognized codes that designate every country and most of the dependent areas a two-letter or three-letter combination        |
| gid\_0             | The code for join country level data to the [GADM](https://gadm.org) country-level data ([click to download](https://biogeo.ucdavis.edu/data/gadm3.6/gadm36_shp.zip))         |
| gid\_1             | The code for join region-level data to the [GADM](https://gadm.org) region-level data ([click to download](https://biogeo.ucdavis.edu/data/gadm3.6/gadm36_levels_shp.zip))       |

<!-- | pct\_\*      | Weighted percentage of respondents that have reported the specified indicator, where * is the indicator, except for the following indicators:\s\scovid, where \* = cli  
flu, where \* = ili  
mask, where \* = mc  
contact, where \* = dc  
finance, where \* = hf  
anosmia, where \* = anos  
vaccine_acpt, where \* = vu|
| pct_\*_unw     | Unweighted percentage of respondents that have reported the specified indicator, where * is the indicator, except for the following indicators:
covid, where \* = cli  
flu, where \* = ili  
mask, where \* = mc  
contact, where \* = dc  
finance, where \* = hf  
anosmia, where \* = anos  
vaccine_acpt, where \* = vu |
| smoothed_\*    | Seven-day rolling average of pct\_\* |
| \*_se          | Standard error of pct\_\*   |
| \*_se_unw      | Standard error of unweighted percent   |
| smoothed_\*_se | Standard error of smoothed percent    |
| sample_size_\* | Sample size for calculating the targeted indicator value   |
| iso_code      | The ISO country codes are internationally recognized codes that designate every country and most of the dependent areas a two-letter or three-letter combination.   |
| gid_0         | The code for join country level data to the [GADM](https://gadm.org) country-level data (click to download)   |
| gid_1         | The code for join region-level data to the [GADM](https://gadm.org) region-level data (click to download)  |
| survey_date   | Survey date for the data   | -->