---
layout: default
title: Issues
nav_order: 11
---

# Data issues and correction status

This page provides updates on known issues and the status of any corrections. Please report any data issues on the [issue page](https://github.com/gisumd/COVID-19-API-Documentation/issues) of this documentation. You are also welcome to contact our survey team regarding any data-related issues or data questions.

| Data product involved             | Description          |Fix status           |Backfill status |
|:-------------------|:---------------------|:---------------------|:---------------------|
| Contingency tables            | Indicators (food security, finance, worried become ill) got 0 percent and se values but had positive sample size        | Pipeline fixed and applied to weekly table 20211212-1218 and other data generated after 2021-12-19 | Backfilling is in progress           |
| Microdata/Aggregates/Contingency tables    |  A routine maintenance on the programming of the Qualtrics survey instrument on December 21, 2021 caused an error in our pipelines that process the data. The issue affected all the data products after 12-21.     | Pipeline fixed and applied after 2021-12-28 | Backfilling for contingency tables is in progress. Microdata and daily API are backfilled.        |