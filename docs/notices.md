---
layout: default
title: Notices and Updates
nav_order: 3
---

# Notices and Updates
<div style="background-color: #ec9696; padding: 10px 30px; font-size:15px; margin-left: 25px; margin-right: 25px;">
    For updates, including data corrections, new aggregates, and any other changes to the API, we encourage you to <a href="https://listserv.umd.edu/cgi-bin/wa?SUBED1=COVID19-API&A=1" target='_blank'>subscribe</a> to our COVID-19 API mailing list.
</div>

| Date                | Notice            |
|:--------------------|:------------------|
| 3/9/2021            | We have changed the naming for all the `hes` and `hesitant` indicators, **except** for the `hesitant_sideeffects` indicator. We have replaced `hes` and `hesitant` with `barrier_reason`. This change was implemented to better describe what the indicators represent. |
| 3/5/2021            | New aggregate indicators for [survey version 10](https://covidmap.umd.edu/document/COVID19_symptom_survey_intl_V10.pdf) are available now. These include indicators for barrier reasons for why respondents don't think they need a COVID-19 vaccine, how informed respondents are about the COVID-19 vaccine, and indicators on vaccine appointment information. Please refer to the survey instrument documentation for more information on the questions used for these indicators.  | 
| 2/6/2021            | New aggregate indicators for survey version 9 are available now. These include indicators for barrier reasons for vaccine acceptance from V5 question in [survey version 9](https://covidmap.umd.edu/document/COVID19_symptom_survey_intl_V9.pdf). The `trust_healthcare` indicator will be discontinued as of 2/14/2021. As of 2/6/2021, the `trust_doctors` indicator is being be populated. Question `V4_2`, which was used for the `trust_healthcare` indicator, has been discontinued in survey version 9. Question `V4_6` replaces question `V4_2` in survey version 9. Question `V4_6` is used in the `trust_doctors` indicator. Please refer to the survey documentation for more information on the question differences.     |
| 1/21/2021           | We have implemented an updated definition for some of the aggregate indicators in the UMD Open Data API. This definition change impacts the following indicators: `mask-wearing`, `financial worry`, `social distancing`, and `vaccine acceptance`. We are implementing this change to make our estimates more directly comparable to those in [Carnegie Mellon University Delphi research group’s COVIDcast API](https://cmu-delphi.github.io/delphi-epidata/api/covidcast-signals/fb-survey.html), which uses data from the US version of the COVID-19 Symptom Survey. Find a more detailed description under the release log section [here](https://covidmap.umd.edu/methodology.html).|
| 12/6/2020           | We released an update to our API. Before this update, the definition of COVID-like illness(CLI) and influenza-like illness (ILI) had been inadvertently switched in the API data. We have implemented a fix that corrects both historic and future data. This issue does not affect individual-level survey responses that are provided to entities who have signed a microdata use agreement. It also does not affect the US data which has been collected and distributed by Carnegie Mellon University. US estimates in the UMD and Facebook maps are also unaffected. Click [here](https://covidmap.umd.edu/api_fix_summary.html) to read a detailed summary of the issue and fix. |

