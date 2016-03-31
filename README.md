# Dashboard Data Format

Experiments with data formats for publication in dashboards.

Contains sample data file and schema for validation.

We use and recommend [jsonschemavalidator.net](http://www.jsonschemavalidator.net/)


### PRE-ALPHA EXPERIMENTAL

Here be  :dragon_face:


Schema expects an array of `measurements` and defines a basic `numeric` measurement type and a `percentage` type.

```
{
  "name":           "costs-saved-transaction",
  "recorded_at":    "2016-01-01T01:01:01.111Z",  
  "value":          0.99,
  "units":          "dollars",
  "type":           "numeric",
  "tags":           ["blah", "vtha"]
},
```

Required fields for a numeric measurement: `["name", "recorded_at", "value", "units", "type"]`

### Premise

Service publishes data in this format into a dashboard that can provide an overview and amalgamated display.

The dashboard is responsible for presentation.


### Questions

 - [ ] Does this even work as an idea?
 - [ ] Should we just use timestamp integers rather than JSON format dates?
 - [ ] Do we need `channel`? 
 - [ ] Could this be a tag, and we break data by tag with some sane default views that use tags in useful ways?
 - [ ] How do we map from data to presentation?
 - [ ] Should minimal presentation information be added as an  meta description?
 - [ ] Could the units be split out into a meta description?

Meta Description would be optional and be used to provide labels and basic information for presenting the data in the dashboard.
Fallback to a sane default if not present.
