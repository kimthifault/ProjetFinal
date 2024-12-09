Projet final - Kim Thifault et Laurie Labonté
================
16 décembre 2024

## Introduction

## Données

## Analyse des données

#### Première étape:

Tout d’abord,

    ## # A tibble: 65,863 × 2
    ##    DATA_YEAR STATE_ABBR
    ##        <dbl> <chr>     
    ##  1      2010 AK        
    ##  2      2010 AK        
    ##  3      2010 AK        
    ##  4      2010 AK        
    ##  5      2010 AK        
    ##  6      2010 AK        
    ##  7      2010 AK        
    ##  8      2010 AL        
    ##  9      2010 AL        
    ## 10      2010 AL        
    ## # ℹ 65,853 more rows

Maintenant,

| STATE_ABBR |    n |
|:-----------|-----:|
| CA         | 9600 |
| NY         | 5910 |
| NJ         | 4956 |
| MI         | 4009 |
| MA         | 3699 |
| WA         | 3561 |
| OH         | 3554 |
| TX         | 2239 |
| AZ         | 2206 |
| KY         | 2035 |

![](ProjetFinal_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

Comme nous pouvons le constater, l’état de la Californie et de New York
ont tous deux le taux de crime le plus élevé des États-Unis depuis 2010

Sélection des crimes entre 2010 et 2019 dans chacune des bases de
données

    ## # A tibble: 4,817,710 × 26
    ##    CMPLNT_NUM  year month   day weekday    hour Latitude Longitude COMPLETED
    ##         <dbl> <dbl> <dbl> <dbl> <chr>     <dbl>    <dbl>     <dbl> <chr>    
    ##  1  394506329  2019    12    31 Tuesday      17     40.8     -73.9 COMPLETED
    ##  2  968873685  2019    12    29 Sunday       16     40.9     -73.9 COMPLETED
    ##  3  509837549  2019    12    15 Sunday       18     40.8     -73.8 COMPLETED
    ##  4  352454313  2019    12    28 Saturday      1     40.9     -73.9 COMPLETED
    ##  5  293718737  2019    12    27 Friday       22     40.7     -74   ATTEMPTED
    ##  6  552685226  2019    12    27 Friday       20     40.7     -73.9 COMPLETED
    ##  7  134037758  2019    12    26 Thursday     20     40.6     -73.8 COMPLETED
    ##  8  855385879  2019    12    26 Thursday     19     40.8     -73.9 COMPLETED
    ##  9  241602326  2019    12    25 Wednesday    23     40.8     -74   COMPLETED
    ## 10  585574881  2019    12    24 Tuesday      16     40.8     -74   COMPLETED
    ## # ℹ 4,817,700 more rows
    ## # ℹ 17 more variables: OFNS_DESC <chr>, ADDR_PCT_CD <dbl>, CRIME_CLASS <chr>,
    ## #   BORO_NM <chr>, PREM_TYP_DESC <chr>, OCCURENCE <chr>, JURIS_DESC <chr>,
    ## #   JURISDICTION_CODE <dbl>, IN_PARK <dbl>, IN_PUBLIC_HOUSING <dbl>,
    ## #   IN_STATION <dbl>, SUSP_AGE_GROUP <chr>, SUSP_RACE <chr>, SUSP_SEX <chr>,
    ## #   VIC_AGE_GROUP <chr>, VIC_RACE <chr>, VIC_SEX <chr>

    ## # A tibble: 713,976 × 13
    ##       record report_date occured_date occured_time area        crime  victim_age
    ##        <dbl> <date>      <date>       <time>       <chr>       <chr>       <dbl>
    ##  1   1208575 2013-03-14  2013-03-11   18:00        77th Street INTIM…         30
    ##  2  20305364 2019-01-22  2019-01-16   21:00        Southwest   INTIM…         49
    ##  3  90631215 2010-01-05  2010-01-05   01:50        Hollywood   VIOLA…         47
    ##  4  91231932 2011-05-14  2011-05-14   03:30        Southwest   ASSAU…         52
    ##  5 100100501 2010-01-03  2010-01-02   21:00        Central     RAPE,…         47
    ##  6 100100509 2010-01-09  2010-01-08   21:00        Central     ASSAU…         51
    ##  7 100100510 2010-01-09  2010-01-09   02:30        Central     ASSAU…         30
    ##  8 100100521 2010-01-14  2010-01-14   14:45        Central     BATTE…         38
    ##  9 100100522 2010-01-15  2010-01-14   20:00        Central     ROBBE…         40
    ## 10 100100529 2010-01-16  2010-01-15   17:45        Central     BOMB …         29
    ## # ℹ 713,966 more rows
    ## # ℹ 6 more variables: victim_sex <chr>, victim_descent <chr>, weapon <chr>,
    ## #   status <chr>, lat <dbl>, lon <dbl>

| BORO_NM       |       n |
|:--------------|--------:|
| BROOKLYN      | 1440200 |
| MANHATTAN     | 1150842 |
| BRONX         | 1048342 |
| QUEENS        |  955653 |
| STATEN ISLAND |  220579 |
| UNKNOWN       |    2094 |

![](ProjetFinal_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->
