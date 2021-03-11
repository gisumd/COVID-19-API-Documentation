# Survey Aggregates

To get aggregates you need to make a call to the following url:

`https://covidmap.umd.edu/api/resources?indicator={indicator}&type={type}&country={country}&date={date}`

## An open API from the University of Maryland

| Parameter    | Description                                       | Example |
|:-------------|:--------------------------------------------------|:--------|
| indicator    | Aggregate data to query                           | `covid`, `mask`, `vaccine_acpt`    |
| type         | Aggregate data type to use                        | `daily` or `smoothed`    |
| country      | Country to query aggregates for                   | `Italy`, `Colombia`, `Autralia`     |
| region       | Region to query aggregates for                    | (optional) `Piemonte`, `Santander`, `New South Wales`    |
| date         | Used to query aggregate data for a specific day   | `20210101`    |
| daterange    | Used to query aggregates data within a time range | (optional) `20210101-20210115`    |

