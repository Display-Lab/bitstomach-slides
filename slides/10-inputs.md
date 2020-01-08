---
author: Display Lab
title: Bitstomach
date: 2019-12-20
---

# Inputs
- Spek: Specification of data columns, measures, and performers
- Data: Performance data
- Annotations: Functions for processing data to attributes.

## Spek
Graph describing the situation for performance feedback in json-ld format.
```json
{
  "measures": [
   ... info about measures
  ],
  "table_schema": [
   ... info about the data
  ]
}
```

- Names of the measures or what the goal is for a measure.
- Titles of the data columns and what the data column is used for.

## Data
Tabular data of performance for each performer

```csv
id,    date,       rate
alice, 2019-10-01, 0.90
alice, 2019-11-01, 0.95
bob,   2019-10-01, 0.90
bob,   2019-11-01, 0.80
```

## Annotations
Functions that operate on the data and determine if an attribute is present.

```R
annotate_gap <- function(data, spek){
  data %>%
    dplyr::filter(date == max(date)) %>%
    group_by(id) %>%
    summarize(positive_gap = (rate > 0.85))
}
```

