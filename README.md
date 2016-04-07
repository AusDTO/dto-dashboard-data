# Dashboard Data Format

Experiments with data formats for publication in dashboards.

Contains sample data file `data.json` and schema for validation.

We use and recommend [jsonschemavalidator.net](http://www.jsonschemavalidator.net/)

A test endpoint will be provided as part of the Performance Dashboard Alpha project.


### Premise

Service publish data in this format, the performance dashboard will consume the data and provide an overview and amalgamated display.

The dashboard is responsible for presentation and collation.


### ALPHA and EXPERIMENTAL

The Dashboard Schema expects an array of `metrics` for display.

The order of metrics in the array defines the order of display on the dashboard.

All historic data for display should be provided in the metric data.

At the moment the only supported metric type is a bar chart.

A bar chart metric is defined as an array of label/value pairs.

```
{
  "name":           "user-satisfaction",
  "description":    "% of users reporting satisfaction",
  "recorded_at":    "2016-01-01T01:01:01.111Z",
  "type":           "bar",
  "period":         "monthly",
  "data": [
      {"label": "Dec 2015", "value": "50%"},
      {"label": "Jan 2016", "value": "20%"},
      {"label": "Feb 2016", "value": "30%"},
      {"label": "Mar 2016", "value": "40%"}
  ]
},
```

Required fields for a numeric measurement: `["name", "recorded_at", "type",  "data"]`
