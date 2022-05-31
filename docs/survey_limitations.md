---
layout: default
title: Survey Limitations
nav_order: 10
---

# Survey Limitations
{: .no_toc}

The Global COVID-19 Trends and Impact Survey (CTIS) is subject to several limitations, many of which are common to web surveys. Anyone using the data to make policy decisions or answer research questions should be aware of these limitations. Given these limitations, we recommend using CTIS data to:


- Track changes over time, such as to monitor sudden increases in reported symptoms or changes in reported vaccination attitudes.
- Compare changes over time across different administrative level-1 equivalent regions within countries and territories. Make comparisons between groups, such as between occupational or age groups, keeping in mind any [sample limitations](#sampling) that might affect these comparisons.
- Augment data collected from other sources, such as more rigorously controlled surveys that have high response rates and include respondents that do not have access to the internet or social media platforms.
- These comparisons should hold if a reasonable argument can be made that changes in the set of people using Facebook or responding to the survey is not shifting over time, or that changes within the Facebook users are different than changes among those not using Facebook.


We do **not** recommend using CTIS data to: 


- Make point estimates of population quantities (such as the exact percentage of people who meet a certain criterion or live in a specific area) without reference to other data sources. For reasons we discuss below, such estimates can be biased, and standard confidence intervals and hypothesis tests will be misleading.


The sections below explain these limitations in more detail.

## Table of contents
{: .no_toc .text-delta}

1. TOC
{:toc}

## Sampling  
The sample is a daily repeated cross section. Meta invites a random sample of users to take the survey every day. Facebook app users are eligible to take the survey if their account is at least 30 days old, if they indicated they are at least 18 years old in their profile, if the language they use Facebook in is one of the 57 languages that the survey is translated into, and if they live in one of the 139 countries or territories where the survey is currently conducted. The completion rate is approximately 1% in most countries or territories. 


Meta’s sampling process allows users to be invited to the survey as frequently as every month and as infrequently as every 5 months, depending on the population density of their area. Respondents are given a new unique identifier each time they complete the survey so that responses from the same user cannot be not linked across time in any way in the individual-level data. Data users must be aware that when working with responses submitted more than a month apart, some responses may be from the same users. (Note that only the first response for each unique identifier is counted so that if a respondent completes the survey multiple times at a given sampling instance, or shares their unique link with friends to take it, those responses are not included in the data files.)


Beyond the independence of observations, there are two types of selection biases data users should consider when conducting their analyses, which are detailed below. 


1. **Non-response bias**. Only a small fraction of invited users choose to take the survey when they are invited. If the decision on whether to take the survey is random, this is not a problem. However, the decision to take the survey may be correlated with other factors---such as users' level of concern about COVID-19 or their trust of academic researchers. If that is the case, the sample will disproportionately contain people with certain attitudes and beliefs. If those correlates of non-response are both correlated with the outcomes of your study and are not included in the calculations used to generate the weights, those estimates may be biased.
2. **Sampling frame coverage bias**. Not everyone in every country or territory has a Facebook app account or uses their account regularly. This is especially true for countries with low internet penetration. If those without a Facebook app account or without access to the internet differ from those who do and the ways in which they differ are both correlated with the outcomes of your study and not included in the calculations used to generate the weights, those estimates may be biased. For example, in countries where vaccination appointments are given out over the internet, the population having access to the internet is more likely to have access to vaccinations. 


Meta calculates [survey weights](https://dataforgood.facebook.com/dfg/resources/user-guide-for-ctis-weights) (see section below) that are intended to help correct these issues using information from respondents' Facebook profiles as well as information about how they use Facebook. Making adjustments using the weights helps make the sample more accurately reflect the characteristics of the target population, but these weights may not be adequate in overcoming non-response and coverage biases. Due to the design of the survey, unlike for the non-response adjustment, very few variables are used to adjust for coverage bias. We encourage individual-level data users to use the data to implement further corrections to the weights to make them better suit their study and their specific outcomes of interest. 


In collaboration with researchers at Boston Children’s Hospital (BCH), we compared respondent demographic characteristics to benchmark data from the United Nations (UN) Population Division 2019 World Population Projections. While the composition of age and gender in the weighted sample varies across countries and territories, the sample composition remains relatively stable. Given this observation, we recommend:


1. **If your research questions focus on differences between specific groups, first carefully check the composition of your sample relative to known variables of your places of interest.** For example, our partners in the Delphi Group at Carnegie Mellon University conducted analyses of weighted CTIS survey data for the US, which show that demographic characteristics in the weighted sample are relatively similar to the US population, with slightly higher levels of education; however, comparisons of self-reported vaccination rates of survey respondents with CDC US population benchmarks indicate that CTIS respondents are more likely to be vaccinated than the general population.
2. **Focus on trends, rather than point estimates.** We do expect that any nonresponse- and coverage biases will remain relatively consistent over time, allowing us to make reliable comparisons over time (such as noting an increase or decrease in COVID cases) even if the point estimates are consistently biased. This is a common issue with self-reported data. For example, surveys on illegal drug use expect under-reporting but are commonly used to make comparisons between groups or over time. 

## Weighting
It is important to [read the weights documentation](https://dataforgood.facebook.com/dfg/resources/user-guide-for-ctis-weights) (updated May 2022) to understand how Meta calculates survey weights, but there are some key limitations to emphasize:

1. **The weights are based only on attributes in Facebook profiles, not on demographics reported in response to survey questions,** because we do not receive Facebook profile data and Meta does not receive individual-level survey response data. For example, if a respondent reported being 35 years of age on their Facebook profile, but on the survey responds that they are 60 years of age, this would cause measurement error in the weights. Similarly, if a sampled user shares their Facebook account or shares their electronic device with another household member of a different age and/or gender and that household member responds to the survey, this would cause measurement error in the weights. 
2. **The non-response model used by Meta to calculate the weights prior to post-stratification ([see the documentation](https://dataforgood.facebook.com/dfg/resources/user-guide-for-ctis-weights)) only uses information available to Meta, such as profile information.** If this model is not perfect, for example, if factors not included in the model are correlated with non-response, the weights will not fully account for this non-response bias.


## Response Behavior
Survey scientists have long known that humans do not always provide complete and truthful responses to questions about their attributes, beliefs, and behaviors. There are two primary reasons why some CTIS responses may be suspect:

1. The first is social desirability bias. Survey respondents may give responses consistent with what they believe is socially desirable, because they feel pressured to fit social norms. For example, if someone lives in an area where masks are widely used and seen as essential, they may report that they wear their mask most or all of the time when in public, even if they don't. While this effect is likely smaller on an anonymous online survey than in an in-person interview, it could still be present. **There are no analytic corrections for social desirability bias, but this is an issue of which data users should be aware.**
2. The second problem is deliberate trolling. While intentional misreporting is always a possibility, it is a particular concern for a large, online survey on a controversial topic offered through a large social media platform. For overall estimates, trolling is not expected to impact results in a meaningful way. However, our partners in the Delphi Group at Carnegie Mellon University find that trolling respondents are more likely to answer that they belong to rare demographic groups in the US sample. For this reason, **we encourage individual-level data users to examine the raw data for unlikely responses or ingenuine responses to open-ended fields.** 

## Missing Data
Many survey respondents do not complete the entire survey. As a result, questions that appear later in the survey can be missing for 10-20% of survey responses. Similar to overall or what survey scientists call “unit-level” non-response, this “item-level non-response” behavior can be an issue if it does not occur at random for the questions you are analyzing. For example, if respondents who are particularly concerned about COVID-19 are more likely to take the time to finish the survey. 


**Data users should examine and report the missingness in the questions they use.** Imputation methods are an option, but individual-level data users should consider whether the assumptions of imputation models appear to be met for the data. 
Processing and Instrument Errors
While we try our best to test and validate all CTIS data products before launching them (e.g., survey questions, publicly available contingency tables, weights, etc.), due to the volume and flow of data that we oversee on a daily basis, we sometimes find errors, and we do our best to correct the errors and announce revisions and updates. Survey scientists call these types of errors “processing error” (mistakes when processing the raw responses to create individual-level data files and aggregate estimates) and “instrument errors” (mistakes made in the design or execution of the survey instrument):
1. Processing errors can include mistakes in the code used to aggregate survey responses for estimates reported on our API or in the contingency tables or mistakes in the code used to define who should receive a survey weight based on their completion of the survey. 
2. Instrument errors can include mistakes in the translations of our survey questions. 


While the time it takes to correct errors depends on the size of the problem, we will always try to notify our data users via our mailing list  and announce any changes to our survey on the [Notices and Updates](https://gisumd.github.io/COVID-19-API-Documentation/docs/notice/notice_index.html) page. To subscribe to the Microdata mailing list, click [here](https://listserv.umd.edu/cgi-bin/wa?SUBED1=COVID19-MICRODATA&A=1) and to subscribe to the Aggregate API mailing list, click [here](https://listserv.umd.edu/cgi-bin/wa?SUBED1=COVID19-API&A=1).


## Summary of Recommendations
- Focus on trends across time or differences between groups, rather than total population estimates. 
- Check the composition of the sample for your places of interest.
- Be cognizant of social desirability bias common in health surveys. 
- Examine the data for unlikely responses or ingenuine responses to open-ended fields. 
- Examine and report the rate of missing data in the questions you analyze. 
- Evaluate whether multiple imputation methods are appropriate for your analyses. 
- Consider whether additional corrections need to be made to the weights given both the representativeness of the weighted sample for your places of interest and your outcomes of interest. 
- Sign up for our mailing list and check the Notices and Updates page regularly. 

## Acknowledgement
This page is adapted from the [Survey Limitations page](https://cmu-delphi.github.io/delphi-epidata/symptom-survey/limitations.html) on the US CTIS website overseen by the [Delphi Group at Carnegie Mellon University](https://delphi.cmu.edu/).
