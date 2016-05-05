# Dashboard Data Format
## ALPHA and EXPERIMENTAL

Experiments with data formats for publication in dashboards.

Contains sample data file `data.json` and `dashboard.json` and schemas for validation.

We use and recommend [jsonschemavalidator.net](http://www.jsonschemavalidator.net/)

Test and validation endpoints will be provided as part of the DTO Dashboard Project.


## Premise

Services publish data and a description of how to represent that data as a dashboard.

The Performance Dashboard consumes the information and publishes a dashboard.  

The dashboard is responsible for presentation and collation.


## Data

The Data Schema expects an array of `metrics` for display.

Each metric requires a unique identifier, which is then used when defining charts and layout.
IDs should be alpha-numeric. Dashes are permitted.

All historic data for display should be provided in the metric data.


```
{
  "id":           "browser-usage-chrome",
  "recorded_at":  "2016-04-19T01:01:01.111Z",
  "units":        "%",
  "data": [
      {"label": "2016-01", "value": 40.15},
      {"label": "2016-02", "value": 41.70},
      {"label": "2016-03", "value": 41.15}
  ],
  "benchmark": {
    "effective_at": "2016-04-19T01:01:01.111Z",
    "value": 99
  },
  "annotations": [
    { "label": "Upgraded the thing", "value": 88 }
  ]
}
```

Required fields for a numeric measurement: `["id", "recorded_at", "data", "units"]`


## Dashboard

A dashboard is represented as an nested array of widgets.
A widget is mapped to one or more datasets by ID.
