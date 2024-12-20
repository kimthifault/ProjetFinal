Projet final - Kim Thifault et Laurie Labonté
================
20 décembre 2024

## Introduction

## Données

Pour trouver les deux villes avec le plus haut taux de criminalité, nous
avons élaboré un graphique avec le jeu de donnée « hate_crime.csv ». Il
présente des informations sur la criminalité des États_unis depuis 1991,
spécifiquement sur les États du pays. Ce jeu de donnée est constitué de
28 colonnes et 209 442 lignes. Grâce à celui-ci, nous avons pu constater
que ce n’était pas Texas, mais plutôt la Californie qui contenait le
plus de crimes comptabilisés. Nous prendrons donc nos données sur la
plus grande ville de cet état, soit Los Angeles. Pour ce qui est du
deuxième état le plus criminalisé, il s’agissait de New York. Selon le
même raisonnement, nous allons prendre des données sur la ville de New
York. Il était donc primordial de trouver deux jeux de donnée pour
entamer notre analyse. Le premier jeu de donnée est pour la ville de New
York et se nomme « final_data.csv ». Il contient 13 colonnes et 1 038
051 lignes. Le deuxième est donc pour la ville de Los Angeles et se
nomme « crimes_all_cleaned.csv ». Celui-ci est constitué de 26 colonnes
et 7 747 417 lignes. Les jeux de donnée proviennent du site de base de
donné «Kaggle».

## Analyse des données

#### Première étape:

Tout d’abord, nous allons limiter notre base de donnée sur les crimes
ayant eu lieu entre 2010 et 2019.

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

Maintenant, faisons le top 10 des états les plus criminelles des
États-Unis durant cette période.

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
sont les deux états ayant le taux de crime le plus élevé des États-Unis
depuis 2010. Après avoir trouvé des bases de données appropriées pour
chacune des villes, nous limiterons encore une fois notre sélection sur
les crimes ayant eu lieu entre 2010 et 2019.

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

En premier lieu, nous trouvions intéressant de savoir la date exacte où
il y a eu le plus de criminalité.

| occured_date |   n |
|:-------------|----:|
| 2010-01-01   | 741 |

| day | month | year |    n |
|----:|------:|-----:|-----:|
|   1 |     1 | 2010 | 2481 |

Comme on le constate

En deuxième lieu, nous voulions analyser, dans la ville de Los Angeles,
les heures les plus criminelles en moyenne dans une journée. Ensuite,
selon ces heures, nous voulions savoir quelle serait l’arme utilisée et
quel serait le crime comis.

| occured_time |     n |
|:-------------|------:|
| 12:00:00     | 18213 |
| 20:00:00     | 13984 |
| 18:00:00     | 13903 |
| 21:00:00     | 13435 |
| 22:00:00     | 13351 |
| 19:00:00     | 12787 |
| 17:00:00     | 12567 |
| 16:00:00     | 12359 |
| 15:00:00     | 12142 |
| 23:00:00     | 11922 |

| occured_time | weapon                                         |     n |
|:-------------|:-----------------------------------------------|------:|
| 12:00:00     | STRONG-ARM (HANDS, FIST, FEET OR BODILY FORCE) | 12389 |
| 20:00:00     | STRONG-ARM (HANDS, FIST, FEET OR BODILY FORCE) |  8859 |
| 18:00:00     | STRONG-ARM (HANDS, FIST, FEET OR BODILY FORCE) |  8764 |
| 22:00:00     | STRONG-ARM (HANDS, FIST, FEET OR BODILY FORCE) |  8512 |
| 21:00:00     | STRONG-ARM (HANDS, FIST, FEET OR BODILY FORCE) |  8500 |
| 19:00:00     | STRONG-ARM (HANDS, FIST, FEET OR BODILY FORCE) |  7831 |
| 17:00:00     | STRONG-ARM (HANDS, FIST, FEET OR BODILY FORCE) |  7779 |
| 23:00:00     | STRONG-ARM (HANDS, FIST, FEET OR BODILY FORCE) |  7777 |
| 16:00:00     | STRONG-ARM (HANDS, FIST, FEET OR BODILY FORCE) |  7760 |
| 15:00:00     | STRONG-ARM (HANDS, FIST, FEET OR BODILY FORCE) |  7672 |

| occured_time | crime                    |    n |
|:-------------|:-------------------------|-----:|
| 18:00:00     | BATTERY - SIMPLE ASSAULT | 3577 |
| 12:00:00     | BATTERY - SIMPLE ASSAULT | 3564 |
| 20:00:00     | BATTERY - SIMPLE ASSAULT | 3440 |
| 15:00:00     | BATTERY - SIMPLE ASSAULT | 3394 |
| 16:00:00     | BATTERY - SIMPLE ASSAULT | 3390 |
| 17:00:00     | BATTERY - SIMPLE ASSAULT | 3345 |
| 19:00:00     | BATTERY - SIMPLE ASSAULT | 3266 |
| 21:00:00     | BATTERY - SIMPLE ASSAULT | 3254 |
| 14:00:00     | BATTERY - SIMPLE ASSAULT | 3209 |
| 22:00:00     | BATTERY - SIMPLE ASSAULT | 3055 |

Nous pouvons constater que 12pm, 8pm ainsi que 6pm sont les trois heures
les plus criminelles à Los Angeles. Pour ce qui est des armes, ce sont
plutôt des crimes faits avec la force corporelles. Il est donc évident
que les crimes commis sont de simple combat sans arme.

Dans la même ordre d’idée, nous avons analysé l’heure la plus criminelle
de la ville de New York. Selon ces heures, nous avons voulu analyser le
lieu de ces crimes ainsi que la description de ceux-ci.

| hour |      n |
|-----:|-------:|
|   15 | 288710 |
|   18 | 284995 |
|   17 | 282476 |
|   16 | 281060 |
|   19 | 271500 |
|   12 | 267991 |
|   20 | 267438 |
|   14 | 257759 |
|   21 | 241024 |
|    0 | 230859 |

| hour | PREM_TYP_DESC |     n |
|-----:|:--------------|------:|
|   20 | STREET        | 93577 |
|   19 | STREET        | 90967 |
|   18 | STREET        | 90894 |
|   21 | STREET        | 89958 |
|   22 | STREET        | 89799 |
|   17 | STREET        | 85053 |
|   23 | STREET        | 83320 |
|   15 | STREET        | 82578 |
|   16 | STREET        | 82184 |
|    0 | STREET        | 76431 |

| hour | OFNS_DESC |      n |
|-----:|:----------|-------:|
|   12 | PROPERTY  | 147676 |
|   15 | PROPERTY  | 146065 |
|   18 | PROPERTY  | 143470 |
|   17 | PROPERTY  | 143411 |
|   16 | PROPERTY  | 143257 |
|   14 | PROPERTY  | 130492 |
|   19 | PROPERTY  | 130201 |
|   20 | PROPERTY  | 123259 |
|   13 | PROPERTY  | 117409 |
|    0 | PROPERTY  | 112908 |

| saison    |       n |
|:----------|--------:|
| Été       | 1280824 |
| Printemps | 1237142 |
| Automne   | 1177300 |
| Hiver     | 1122444 |

| BORO_NM       |       n |
|:--------------|--------:|
| BROOKLYN      | 1440200 |
| MANHATTAN     | 1150842 |
| BRONX         | 1048342 |
| QUEENS        |  955653 |
| STATEN ISLAND |  220579 |
| UNKNOWN       |    2094 |

![](ProjetFinal_files/figure-gfm/unnamed-chunk-11-1.png)<!-- -->

    ## # A tibble: 3,314,353 × 3
    ##    VIC_AGE_GROUP BORO_NM   month
    ##    <chr>         <chr>     <dbl>
    ##  1 25-44         QUEENS       12
    ##  2 25-44         QUEENS       12
    ##  3 18-24         BRONX        12
    ##  4 45-64         MANHATTAN    12
    ##  5 25-44         MANHATTAN    12
    ##  6 <18           BRONX        12
    ##  7 18-24         BRONX        12
    ##  8 65+           BROOKLYN     12
    ##  9 25-44         BRONX        12
    ## 10 <18           BRONX        12
    ## # ℹ 3,314,343 more rows

![](ProjetFinal_files/figure-gfm/unnamed-chunk-12-1.png)<!-- -->

| area        |     n |
|:------------|------:|
| 77th Street | 68433 |
| Southeast   | 58084 |
| Southwest   | 54348 |
| Newton      | 43437 |
| Central     | 40482 |
| Rampart     | 38959 |
| Olympic     | 36987 |
| Hollywood   | 33000 |
| Mission     | 32598 |
| Hollenbeck  | 29979 |

![](ProjetFinal_files/figure-gfm/unnamed-chunk-13-1.png)<!-- -->

    ## # A tibble: 293,605 × 3
    ##    area        victim_sex victim_age
    ##    <chr>       <chr>           <dbl>
    ##  1 77th Street F                  30
    ##  2 Southwest   M                  49
    ##  3 Hollywood   F                  47
    ##  4 Southwest   M                  52
    ##  5 Central     F                  47
    ##  6 Central     M                  51
    ##  7 Central     M                  30
    ##  8 Central     F                  38
    ##  9 Central     M                  40
    ## 10 Central     F                  29
    ## # ℹ 293,595 more rows

![](ProjetFinal_files/figure-gfm/unnamed-chunk-14-1.png)<!-- -->

Maintenat, testons si l’âge moyen des victimes de la est de 33 ans (Nous
utiliserons un niveau de signification de 0,05)

    ## Response: victim_age (numeric)
    ## Null Hypothesis: point
    ## # A tibble: 500 × 2
    ##    replicate  stat
    ##        <int> <dbl>
    ##  1         1  33.0
    ##  2         2  33.0
    ##  3         3  33.0
    ##  4         4  33.0
    ##  5         5  33.0
    ##  6         6  33.0
    ##  7         7  33.0
    ##  8         8  33.0
    ##  9         9  33.0
    ## 10        10  33.0
    ## # ℹ 490 more rows

    ## Response: victim_age (numeric)
    ## # A tibble: 1 × 1
    ##    stat
    ##   <dbl>
    ## 1  33.0

![](ProjetFinal_files/figure-gfm/unnamed-chunk-16-1.png)<!-- -->

    ## # A tibble: 1 × 1
    ##   p_value
    ##     <dbl>
    ## 1    0.74

    ## # A tibble: 1 × 2
    ##   lower_ci upper_ci
    ##      <dbl>    <dbl>
    ## 1     33.0     33.0

![](ProjetFinal_files/figure-gfm/unnamed-chunk-17-1.png)<!-- -->

## Bibliographie
