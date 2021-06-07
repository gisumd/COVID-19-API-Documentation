---
layout: default
title: Wave 10 and 11 cli Trend Break Blog 
nav_order: 2
parent: Notices and Updates
---
# Wave 10 and 11 cli Trend Break Blog 
<!-- 
On May 20, 2021 we launched a major revision to the global survey instrument, our 11th wave of the survey (“Wave 11”). A primary goal of the revision was to harmonize our global instrument with the instrument being used by Carnegie Mellon University (CMU) for the US survey. This harmonization effort required changes to both the global and US instruments. In advance of, and shortly after, launching the instrument, we notified data users and posted a detailed change summary ([here](https://covidmap.umd.edu/document/[For%20Data%20Users][CSS]%20W11%20Change%20Summary.xlsx)) on covidmap.umd.edu. In this blog post, we outline the motivation for the revisions made to the instrument and discuss their effects on analyses of trends using the data before and after the launch of Wave 11.  -->

<!-- ## Motivation for the Wave 11 Revisions

The primary goals of the Wave 11 revision were to increase comparability between the global and US instruments as well as to ask new questions about additional topics related to COVID knowledge, attitudes, and practices (KAP). The secondary goal of the Wave 11 revision was to reduce the length of the survey in order to decrease burden on our respondents and improve response rates. As part of the revision, we cut some items, added some items, revised some items, and restructured the survey to use a modular structure to cover more topics without increasing the length of the instrument. The new structure includes a core set of items asked of everyone and two modules that are each shown to 50% of the respondents, with half of respondents randomly assigned to “Module A” and half of respondents randomly assigned to “Module B.” 

Among the revisions made to the global instrument were minor changes to the individual and community symptoms questions. No changes were made to this section of the survey in the US instrument. In the global instrument, we reordered the individual and community symptoms questions, and we added a transition statement between the two measures. These changes are summarized in Table 1 below. The purpose of these changes was to harmonize the instrument with the US survey while maintaining high response rates in order to increase the fraction of respondents who continue on in the survey and respond to other important questions, including those in the vaccination section. 

## Trend Breaks in COVID-Like Illness

While we did not anticipate these changes the the symptoms section of the questionnaire would create a significant trend break in responses, we do observe a trend break in estimates of both COVID-like illness (CLI) and influenza-like illness (ILI) between Wave 10 and Wave 11, which use the personal symptoms question. Though we did not anticipate these specific trend breaks, we did expect trend breaks in other sections of the instrument given the magnitude of changes that were made. Because of this, we proactively designed the wave changeover with an overlap period. Starting on May 20, 2021, 80% of respondents were given the new Wave 11 survey, while 20% of respondents were given the Wave 10 survey. This overlap was designed with the goal of detecting such trend breaks. The overlap period was scheduled to be 2 weeks, after which we would analyze the overlapped data and provide findings to the data users quantifying any trend breaks we noted. 

After noticing this trend break in CLI and ILI we investigated several possible non-survey causes for the discrepancy, but ruled out these possible sources of error, including errors in the pipeline that processes the survey responses, the pipeline that feeds the processed data to the API and microdata repository, and errors in the programming of the Qualtrics instrument itself, including its translations. 

Focusing on CLI specifically, we compared the Wave 10 estimate for the overlap period to the Wave 11 estimate for the same period (May 20 - 31, 2021). We found that the difference between Wave 10 and Wave 11 CLI estimates was statistically significant in 49 out of the 85 countries and territories in which there was enough data to report aggregates (n > 100); Wave 11 estimates of CLI were nearly uniformly higher than Wave 10 estimates for this time period. There were only 6 countries and territories where the CLI estimates from Wave 11 were lower than Wave 10 estimates for this time period, but none of these differences were statistically significant: Afghanistan; Kazakhstan; Puerto Rico (US); Russia; South Korea; and Ukraine.

Below, we list the countries in which we observed statistically significant differences in CLI estimates between Waves 10 and 11 of the survey, along with those countries that did not have statistically significant differences, and those countries that had an inadequate number of responses in the Wave 10 overlap for reporting aggregates.



One of the countries where the CLI trend break was first identified was Brazil. The daily CLI estimate for Brazil on 5/19/2021 (Wave 10) was 2.41% [2.07%, 2.75%]. The daily estimate of CLI for Brazil on 5/20/2021 with combined Wave 10 and Wave 11 data was 4.18% [3.71%, 4.66%]. However, our analysis suggests that COVID-like symptoms have not actually increased significantly in Brazil over this time period, but instead there is something in the Wave 11 survey instrument that is leading to more reports of covid-like symptoms compared to the Wave 10 survey instrument. When we compare the smoothed estimate of CLI from 5/19/2021 (2.47% [2.33%, 2.61%]) with the smoothed CLI estimate from the Wave 10 overlap data (2.87% [2.48%, 3.25%]), we see no significant difference (t = 1.92, p = 0.054). This indicates that, using responses to the original symptom question design in the Wave 10 instrument, there is no significant difference in CLI in Brazil between those time periods. 

## Differences in Personal Symptoms Question Response Rates

As noted above, an important goal in the instrument redesign was to increase response rates and decrease the number of respondents leaving the survey midway through. As a part of our analysis, we looked at response rates to the first section of the survey as well as a couple questions that follow the symptoms section (Table 3). In this table we look at the response rates in survey order, with B1 as the first symptoms item in Wave 10 and B3 the first symptoms item in Wave 11. We see that the Wave 11 instrument has fewer respondents breaking off after the first two symptom items. Moving forward in the survey, we also see slightly higher item response rates for testing and vaccine items in Wave 11, indicating that perhaps the cuts to the front section of the instrument may have had the intended effect of reducing breakoff across the instrument. However, these comparisons are insufficient evidence to conclude that the specific changes made to the symptoms section improve response rates because we don’t have a way to distinguish between the effects of symptom section changes and other changes that were made (such as differences in the testing items)

## What’s next?
Trend breaks are expected with a major revision to a survey instrument. While we did not anticipate these changes to have such an effect on CLI, there is a clear trend break. In response to this observed trend break, we are:

- **Encouraging data users (especially API users) to** [sign up for our listserv](https://listserv.umd.edu/cgi-bin/wa?SUBED1=COVID19-API&A=1) for up-to-date information on survey instruments and data changes.
- **Reverting back to the Wave 10 version of the symptom section questions.** Since there is no empirical evidence that one version of this section is more accurate than the other, and since these questions are used for both academic forecasting and dashboarding for decision-makers, we will revert back to the Wave 10 instrument to prevent continued discontinuity in their responses. 
- **Increasing the overlap period between Wave 10 and Wave 11 to at least one month (instead of two weeks) ending on June 17, 2021** to allow for more data in which to analyze potential trend breaks in these and other signals. 
- **Creating two new API indicators, `cli_w11` and `ili_w11`.** These indicators will be calculated similarly to the existing `covid` and `flu` indicators. Once these indicators are created, and all indicators are backfilled, the existing `covid` and `flu` indicators will contain estimates from the Wave 10 portion of the overlap, while the `cli_w11` and `ili_w11` indicators will reflect the Wave 11 portion of the data. This will allow direct comparison of the CLI and ILI values for the same time period from the two different instruments. We will inform all data users when these indicators are available.
- **Continuing to monitor the data and analyze trend breaks for other indicators.** -->


### TABLE 1. Symptoms instrument section wording and flow.
| Wave 10             | Wave 11            |
|:--------------------|:------------------|
|B1: In the last 24 hours, have you had any of the following? [list of symptoms]|B3: Do you personally know anyone in your local community who is sick with a fever and either a cough or difficulty breathing?|
|B1b: Are any of these symptoms unusual for you? [list of positive symptoms from B1]|B1: The rest of the survey will go into more detail about your personal experience. In the past 24 hours, have you personally experienced any of the following symptoms? [list of symptoms]|
|B3: Do you personally know anyone in your local community who is sick with a fever and either a cough or difficulty breathing?|B1b: Are any of these symptoms unusual for you? [list of positive symptoms from B1]|

### TABLE 2. Countries and territories with and without significant differences in CLI between Wave 10 and Wave 11 for the same period (May 20 - 31, 2021). 

| With statistically significant differences in CLI| Without statistically significant differences in CLI|With inadequate overlap data (n < 100)|
|:--------------------|:------------------|:------------------|
|Algeria<br>Argentina<br>Australia<br>Austria<br>Bangladesh<br>Belgium<br>Bolivia<br>Brazil<br>Chile<br>Colombia<br>Czech Republic<br>Ecuador<br>Egypt<br>El Salvador<br>France<br>Guatemala<br>Honduras<br>Hong Kong<br>India<br>Indonesia<br>Iraq<br>Ireland<br>Jordan<br>Kenya<br>Libya<br>Malaysia<br>Mexico<br>Morocco<br>Myanmar<br>Nepal<br>Netherlands<br>Nicaragua<br>Norway<br>Pakistan<br>Panama<br>Peru<br>Philippines<br>Portugal<br>Romania<br>Saudi Arabia<br>Singapore<br>Sri Lanka<br>Sudan<br>Sweden<br>Switzerland<br>Taiwan<br>United Arab Emirates<br>United Kingdom<br>Vietnam|Afghanistan<br>Belarus<br>Bulgaria<br>Canada<br>Costa Rica<br>Croatia<br>Denmark<br>Dominican Republic<br>Ethiopia<br>Finland<br>Germany<br>Ghana<br>Greece<br>Hungary<br>Israel<br>Italy<br>Japan<br>Kazakhstan<br>New Zealand<br>Nigeria<br>Paraguay<br>Poland<br>Puerto Rico, U.S.<br>Russia<br>Serbia<br>Slovakia<br>Slovenia<br>South Africa
<br>South Korea<br>Spain<br>Thailand<br>Tunisia<br>Turkey<br>Ukraine<br>Uruguay<br>Venezuela
|Albania<br>Angola<br>Armenia<br>Azerbaijan<br>Benin<br>Bosnia and Herzegovina<br>Burkina Faso<br>Cambodia<br>Cameroon
<br>Democratic Republic of the Congo<br>Guinea<br>Haiti<br>Kuwait<br>Kyrgyzstan<br>Laos<br>Lebanon<br>Madagascar<br>Mali<br>Mauritania<br>Moldova<br>Mozambique<br>Oman<br>Palestine<br>Qatar<br>Senegal<br>Tanzania<br>Uzbekistan<br>Yemen|

### TABLE 3: Response Rates to Key Early Questionnaire Items
||Raw|MICRODATA (Full weights)|
|:--------------------|:------------------|:------------------|
|First Symptoms Item|||
|W10 - B1 (personal symptoms)|94.6%|99.2%|
|W11 - B3 (community symptoms)|98.1%|99.6%|
|Second Symptoms Item|||
|W10 - B3 (community symptoms)|88.2%|93.8%|
|W11 - B1 (personal symptoms)|90.8%|98.4%|
|Unusual symptoms (B1b) - for those with positive symptoms|||
|W10|46.3%|49.8%|
|W11|43.7%|48.1%|
|First Testing Question|||
|W10 (ever been tested)|86.3%|91.7%|
|W11 (tested last 14 days)|88.8%|94.6%|
|Vaccine Uptake (V1)|||
|W10|85.7%|90.8%|
|W11|87.8%|93.3%|
NOTE: The denominator for all cells is the number of people answering the country question at the very start of the instrument.

