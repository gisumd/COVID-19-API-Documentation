---
layout: default
title: Data Fields
nav_order: 6
---

# Data Fields

Data fields returned form an API query.

**Note:** all smoothed data fields are weighted. 

| Field              | Description          |
|:-------------------|:---------------------|
| country            | Country name         |
| region             | Sub-country region name. Generally, it is at the state or province-level or equivalent.        |
| pct\_*             | Weighted percentage of respondents that have reported the specified indicator, where \* is the indicator, except for the following indicators:<br />`covid`, where \* = cli<br />`flu`, where \* = ili<br />`mask`, where \* = mc<br />`contact`, where \* = dc<br />`finance`, where \* = hf<br />`anosmia`, where \* = anos<br />`vaccine_acpt`, where \* = vu        |
| pct\_\*\_unw       | Unweighted percentage of respondents that have reported the specified indicator, where \* is the indicator, except for the following indicators:<br />`covid`, where \* = cli<br />`flu`, where \* = ili<br />`mask`, where \* = mc<br />`contact`, where \* = dc<br />`finance`, where \* = hf<br />`anosmia`, where \* = anos<br />`vaccine_acpt`, where \* = vu         |
| smoothed\_\*       | Seven-day rolling average of pct\_\*         |
| \*\_se             | Standard error of pct\_\*                    |
| \*\_se\_unw        | Standard error of pct\_\*\_unw               |
| smoothed\_\*\_se   | Standard error of smoothed\_\*         |
| sample\_size\_\*   | Sample size for calculating the targeted indicator value.         |
| iso\_code          | The ISO country codes are internationally recognized codes that designate every country and most of the dependent areas a two-letter or three-letter combination        |
| gid\_0             | The code for join country level data to the [GADM](https://gadm.org) country-level data ([click to download](https://biogeo.ucdavis.edu/data/gadm3.6/gadm36_shp.zip)).         |
| gid\_1             | The code for join region-level data to the [GADM](https://gadm.org) region-level data ([click to download](https://biogeo.ucdavis.edu/data/gadm3.6/gadm36_levels_shp.zip)).       |
