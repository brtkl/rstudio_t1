---
title: "title test"
author: "bs"
date: "2024-01-08"
output:
  html_document:
    keep_md: true
---

```r
library(tidyverse)
```

```
## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
## ✔ dplyr     1.1.2     ✔ readr     2.1.4
## ✔ forcats   1.0.0     ✔ stringr   1.5.0
## ✔ ggplot2   3.4.2     ✔ tibble    3.2.1
## ✔ lubridate 1.9.2     ✔ tidyr     1.3.0
## ✔ purrr     1.0.1     
## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
## ✖ dplyr::filter() masks stats::filter()
## ✖ dplyr::lag()    masks stats::lag()
## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors
```

```r
library(nycflights13)
```

```
## Warning: pakiet 'nycflights13' został zbudowany w wersji R 4.3.2
```

```r
flights |> group_by(origin, dest) |> 
  summarize(mdd=mean(dep_delay, na.rm=TRUE), nrows=n()) |> arrange(desc(mdd))
```

```
## `summarise()` has grouped output by 'origin'. You can override using the
## `.groups` argument.
```

```
## # A tibble: 224 × 4
## # Groups:   origin [3]
##    origin dest    mdd nrows
##    <chr>  <chr> <dbl> <int>
##  1 EWR    TYS    41.8   323
##  2 EWR    CAE    36.3   104
##  3 EWR    TUL    34.9   315
##  4 LGA    SBN    31.3     6
##  5 EWR    OKC    30.6   346
##  6 LGA    BHM    29.8   296
##  7 LGA    CAE    29.5    12
##  8 EWR    DSM    29.3   411
##  9 EWR    JAC    28.7    23
## 10 EWR    ROC    27.9   513
## # ℹ 214 more rows
```

