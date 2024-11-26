Projet final
================
12/16/2024

``` r
library(tidyverse) 
```

``` r
hate_crime <- read_csv("data/hate_crime.csv")
```

    ## Rows: 209442 Columns: 28
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr (19): ORI, PUB_AGENCY_NAME, PUB_AGENCY_UNIT, AGENCY_TYPE_NAME, STATE_ABB...
    ## dbl  (9): INCIDENT_ID, DATA_YEAR, ADULT_VICTIM_COUNT, JUVENILE_VICTIM_COUNT,...
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
crime <- hate_crime %>%
  select(DATA_YEAR, STATE_NAME) %>%
  filter(DATA_YEAR >= "2000")
crime
```

    ## # A tibble: 143,931 × 2
    ##    DATA_YEAR STATE_NAME
    ##        <dbl> <chr>     
    ##  1      2000 Alaska    
    ##  2      2000 Alaska    
    ##  3      2000 Alaska    
    ##  4      2000 Alaska    
    ##  5      2000 Arkansas  
    ##  6      2000 Arkansas  
    ##  7      2000 Arkansas  
    ##  8      2000 Arizona   
    ##  9      2000 Arizona   
    ## 10      2000 Arizona   
    ## # ℹ 143,921 more rows
