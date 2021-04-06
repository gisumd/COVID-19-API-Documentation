---
layout: default
title: Formula for the Mask indicator
nav_exclude: true
search_exclude: true
---

## `mask` Indicator

The `mask` indicator is calculated as such: 

**Question:** In the last 7 days, how often did you wear a mask when in public? (C5).
**Numerator:** Sum of respondents who answered all of the time (1) or most of the time (2) to C5.
**Denominator:** Sum of valid answers to C5. Valid answers are any answer to C5. Missing answers are not valid and therefore not included.

For a given location i and time t, let 

For a given location *l* and time *t*, let $M_{lt}^{mask}$ denote the number of 1 or 2 responses to C5 and let $N_{lt}$ be the total number of valid responses to C5. Our estimate for `mask` indicator is given by

`mask` = $M_{lt}^{mask} \over N_{lt}$


