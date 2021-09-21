Homework1
================
Catherine Seymour

source: https://www.fhwa.dot.gov/bridge/nbi/ascii1992.cfm
github: https://github.com/caseymour/homework_1

<!-- end list -->

``` r
library(dplyr)
```

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

``` r
library(ggplot2)
library(tidyverse)
```

    ## ── Attaching packages ───────────────────────────────────────────────────────────────── tidyverse 1.3.0 ──

    ## ✓ tibble  3.0.3     ✓ purrr   0.3.4
    ## ✓ tidyr   1.1.2     ✓ stringr 1.4.0
    ## ✓ readr   1.3.1     ✓ forcats 0.5.0

    ## ── Conflicts ──────────────────────────────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
X <- read.csv('2020HwyBridgesDelimitedAllStates.csv')
```

``` r
Bridges_data = X %>%
  select("BRIDGE_CONDITION", "YEAR_BUILT_027", "COUNTY_CODE_003", "ADT_029", "STRUCTURE_NUMBER_008", "FUTURE_ADT_114") %>%
  drop_na()
```

``` r
Bridges_data_head = Bridges_data[1:100,]

ggplot(Bridges_data_head, aes(ADT_029, FUTURE_ADT_114, color = YEAR_BUILT_027)) + geom_point() + scale_y_discrete(breaks = seq(0, 10000, 1000))
```

![](README_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->
