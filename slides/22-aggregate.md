---
author: Display Lab
title: Bitstomach
date: 2019-12-20
---

# Aggregate results
For each measure, produce a table of performers and the annotations about that measure.

## Multiple annotations assessed
- positive performance gap
- negative performance gap
- positive performance trend
- negative performance trend

## Multiple Tables
Each annotation function produces it's own table.
```
  $id   $positive_gap
  alice TRUE
  bob   FALSE
```
```
  $id   $negative_gap
  alice FALSE
  bob   TRUE
```

## Annotations condensed into a single table
```
  $id   $positive_gap $negative_gap $positive_trend ...
  alice TRUE          FALSE         TRUE            ...
  bob   FALSE         TRUE          FALSE           ...
```

