---
author: Display Lab
title: Bitstomach
date: 2019-12-20
---

# Walkthrough
1. Read Spek
2. Read Data
3. Run Annotations

# 1. Read spek
- Find out about the measures
- Find out about the data format

## Find out about measures
- the measure is "documentation rate"
- the comparator is a goal of 0.85

## Find out about input data format
- **identifier column** is "id"
- **performance column** is "rate"
- **timepoint column** is "date"

# 2. Read data
Get the performance of each performer.
```
# A tibble: 4 x 1
  $id   $date      $rate
  <fct> <date>     <dbl>
  alice 2019-10-01  0.9
  alice 2019-11-01  0.95
  bob   2019-10-01  0.9
  bob   2019-11-01  0.8
```
Nothing fancy.  Just reading tabular data.

# 3. Run Annotations
For a each performer, with each measure, get results of annotations.

## Example `annotate_gap` function
```R
annotate_gap <- function(data, spek){
  data %>%
    dplyr::filter(date == max(date)) %>%
    group_by(id) %>%
    summarize(positive_gap = (rate > 0.85))
}
```

##
```R
dplyr::filter(date == max(date)
```

Filter the data to only rows where the date equals the maximum (most recent) date

```
  $id   $date      $rate
  alice 2019-11-01  0.95
  bob   2019-11-01  0.8
```

##
```
group_by(id)
```
Marks the id column values as what to use for subsequent aggregations using.

##
```R
    summarize(positive_gap = (rate > 0.85))
```

Aggregate to create a new column `positive_gap`.

Fill it with the result of:  `rate > 0.85`
```
  $id   $positive_gap
  alice TRUE
  bob   FALSE
```






