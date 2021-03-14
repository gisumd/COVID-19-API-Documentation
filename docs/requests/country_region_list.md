---
layout: default
title: Retrieve country and region lists
nav_order: 1
parent: Requests
---
Coming soon
{: .label .label-yellow }

## Retrieve the country list or region list for survey responses
To retrive the list of available countries:

`https://covidmap.umd.edu/api/country`

```
{"data":
	[
		{
			"country": "Afghanistan"
		},
		{
			"country": "Albania"
		},
		...
		{
			"country": "Mexico"
		},
		{
			"country": "Moldova"
		},
		...
	]
}
```

To retrive the list of available regions:

`https://covidmap.umd.edu/api/country`

```
{"data":
	[	...
		{"country": "Argentina", "region":"Buenos Aires"},
		{"country":"Argentina","region":"Chaco"},
		...
		{"country": "Philippines", "region":"Central Luzon"},
		{"country":"Philippines","region":"Central Visayas"},
		...
		{"country": "Dominican Republic", "region":"Distrito Nacional"},
		{"country":"Dominican Republic","region":"Santiago"},
		...
	]
}
```