---
layout: default
title: June Indicators Fixes Blog 
nav_order: 2
parent: Notices and Updates
---

# June Indicators Fixes Blog 

## Corrections to indicator calculations

As of June 11, we have made revisions to several indicators in our [aggregate data API](https://covidmap.umd.edu/api.html) either to better align with those in the CMU’s API for the US survey or to correct bugs. These revisions have been used to backfill historical data and will also apply to future data. Below is a summary of the changes and impact to estimates.

1. `modified_acceptance` <br>
We updated the denominator of this indicator to exclude respondents who answered V1 but did not answer V3. The effect of this change on estimates is overall quite small; the mean change was 0.5 percentage points. 

2. `hesitant_sideeffects` <br>
Previously, this indicator was incorrectly being calculated for all respondents to V3, rather than for only those who were vaccine-hesitant. The denominator has been updated to include only those who responded that they “probably wouldn’t” or “definitely wouldn’t” choose to get vaccinated if offered today. The effect of this change is relatively large and we recommend that you re-download data for this indicator.

3. `appointment_or_accept_covid_vaccine` and `vaccinated_appointment_or_accept` <br>
Previously, these indicators were both providing estimates of 0 for all dates and locations. They have been backfilled with corrected, non-zero estimates.

4. B1 and C0 indicators <br>
For the symptom question (B1; `symp_*` and `anosmia` indicators) and recent activities question (C0) we have revised the denominator to include any response to the overall item (that is, any yes or no response to any symptom/activity. Previously a response was defined as a yes/no to the specific symptom or activity, e.g., chills). This change makes the indicator more directly comparable to the indicators for the US instrument, which uses a check all that apply question type rather than a yes/no question type. The impact to estimates for the symptom indicators is approximately 0.1 to 0.3 percentage points; the impact to estimates of indicators for recent activities is approximately 1 to 2 percentage points.

## Smoothed estimates
You may have noticed the unavailability of smoothed estimates for several indicators in recent weeks, including `mask`, `contact`, `finance`, `anosmia`, and `vaccine_acpt`. The bug causing this issue has been fixed and smoothed estimates for these indicators are now available again.

## Planned revisions for Wave 10/11 data
We are currently working on revisions to a number of indicators to more clearly delineate between responses in Wave 10 and Wave 11. We expect these changes to land this week, and we will send a follow up email when they are complete. Planned changes include:

1. For indicators based on survey items which were removed or substantially changed in Wave 11, we will continue to fill these with Wave 10 data until Wave 10 is turned off. At that point, these indicators will remain available in the API for historical data but will not be calculated for future waves. These indicators include:

`contact`, `trust_fam`, `trust_healthcare`, `trust_who`, `trust_govt`, `trust_politicians`, `trust_doctors`, `access_wash`, `wash_hands_24h_1to2`, `wash_hands_24h_3to6`, `wash_hands_24h_7orMore`, `informed_access`, `pay_test`, `reduce_spending`, `sick_spending_time_7d`, `flu_vaccine_thisyr`, `flu_vaccine_lastyr`, `work_outside_home_1d`, `shop_1d`, `restaurant_1d`, `spent_time_1d`, `large_event_1d`, `public_transit_1d`, `ever_tested`, `appointment_have`, `vaccine_acpt`, `modified_acceptance`, `appointment_tried` 

For those indicators that were replaced due to substantial changes in the W11 instrument we have created replacement indicators:


| **Indicator for Wave 10 and earlier** | **Indicator for Wave 11 and later** |
|-|-|
| appointment_have | appointment_not_vaccinated |
| vaccine_acpt | appointment_or_accept_covid_vaccine |
| modified_acceptance | vaccinated_appointment_or_accept |
| appointment_tried | vaccine_tried |
| work_outside-home_1d | activity_work_outside_home |
| shop_1d | activity_shop |
| restaurant_1d | activity_restaurant_bar |
| spent_time_1d | activity_spent_time |
| large_event_1d | activity_large_event |
| public_transit_1d | activity_public_transit |


2. For `covid`, `flu`, `anosmia` and `symp_*` indicators, we will backfill with data for Wave 10 only through 6/7/2021. These indicators will be calculated with Wave 11 data only beginning on 6/8/2021.

3. `cli_w11` and `ili_w11` will only include data from Wave 11 between 5/20/2021 and 6/7/2021. They will no longer be used after 6/7/2021 given that we have reverted the survey instrument for the symptom items as per previous communications.

4. For all other indicators, starting on 5/20/2021 we will backfill with data for Wave 11 only.  Wave 10 data will be used for these indicators through 5/19/2021. This will facilitate clearer separation of data between waves.



