---
layout: default
title: Issues
nav_order: 11
---

# Data issues and correction status

This page provides updates on known issues and the status of any corrections. Please report any data issues on the [issue page](https://github.com/gisumd/COVID-19-API-Documentation/issues) of this documentation. You are also welcome to contact our survey team regarding any data-related issues or data questions.

| Data product involved             | Description          |Fix status           |Backfill status |
|:-------------------|:---------------------|:---------------------|:---------------------|
| Contingency tables            | Indicators (food security, finance, worried become ill) got 0 percent and se values but had positive sample size        | Pipeline fixed and applied to weekly table 20211212-1218 and other data generated after 2021-12-19 | Backfilling for the active period of the involved indicators(all months and weeks from 2020-04-23 to 2021-12-19) is in progress           |
| Contingency tables            | Indicator (Want_info_none ) is wrongly overwritten with the definition of received_news_local_health. | Pipeline fixed and applied to weekly and monthly data generated after 2021-12-22 | Backfilling for the active period of the involved indicators(all months and weeks from 2021-05-20 to 2021-12-22) is in progress           |
| Contingency tables            | Indicators (anxious_7d, depressed_7d) underestimated percentage due to a typo that missed the first option of the corresponding question.        | Pipeline fixed and applied to weekly and monthly data generated after 2021-12-23 | Backfilling for the active period of the involved indicators(all months and weeks from 2020-04-23 to 2021-12-23) is in progress           |
| Contingency tables            | Indicator (received_2_vaccine_doses ) missed the "I don't know" option as the denominator and hence slightly overestimated the percentage value        | Pipeline fixed and applied to weekly and monthly data generated after 2022-01-26 | Backfilling for the active period of the involved indicators (all months and weeks from 2021-01-06 to 2022-01-26) is in progress           |
| Daily aggregates            | Public_transit, large_event, spent_time, restaurant_bar, shop_1d, work_outside_home (indicators using question C0a_*) missed the "None of the above"(C0a_7) option as the denominator and hence significantly overestimated the percentage values       | Pipeline is fixed on 2022-02-02 (watch for the future announcement) | Backfilling for the active period of the involved indicators (all months and weeks from 2021-05-20 to 2022-01-29) is in progress           |
