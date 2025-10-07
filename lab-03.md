Lab 03 - Nobel laureates
================
Cailey Fay
10.7.25

### Load packages and data

``` r
library(tidyverse) 
```

``` r
nobel <- read_csv("data/nobel.csv")
```

## Exercises

### Exercise 1

``` r
nrow(nobel)
```

    ## [1] 935

``` r
ncol(nobel)
```

    ## [1] 26

``` r
#There are 26 variables and 935 observations. 
```

Remove this text, and add your answer for Exercise 1 here. Add code
chunks as needed. Don’t forget to label your code chunk. Do not use
spaces in code chunk labels.

### Exercise 2

``` r
nobel_living <-nobel %>%
    filter(!is.na(died_date))

nobel_living %>%
  select(died_date, gender, country)
```

    ## # A tibble: 627 × 3
    ##    died_date  gender country       
    ##    <date>     <chr>  <chr>         
    ##  1 1923-02-10 male   Germany       
    ##  2 1928-02-04 male   Netherlands   
    ##  3 1943-10-09 male   Netherlands   
    ##  4 1908-08-25 male   France        
    ##  5 1906-04-19 male   France        
    ##  6 1934-07-04 female <NA>          
    ##  7 1934-07-04 female France        
    ##  8 1919-06-30 male   United Kingdom
    ##  9 1947-05-20 male   Germany       
    ## 10 1940-08-30 male   United Kingdom
    ## # ℹ 617 more rows

``` r
#not quite what you are looking for, need to filter out the observations that arent people, and the people who arent affiliated with a country
```

``` r
new_nobel <-nobel %>%
    filter(!is.na(died_date),!is.na(gender), !is.na(country))

new_nobel%>%
  select(died_date, gender, country)
```

    ## # A tibble: 453 × 3
    ##    died_date  gender country       
    ##    <date>     <chr>  <chr>         
    ##  1 1923-02-10 male   Germany       
    ##  2 1928-02-04 male   Netherlands   
    ##  3 1943-10-09 male   Netherlands   
    ##  4 1908-08-25 male   France        
    ##  5 1906-04-19 male   France        
    ##  6 1934-07-04 female France        
    ##  7 1919-06-30 male   United Kingdom
    ##  8 1947-05-20 male   Germany       
    ##  9 1940-08-30 male   United Kingdom
    ## 10 1931-05-09 male   USA           
    ## # ℹ 443 more rows

``` r
  nrow(new_nobel)
```

    ## [1] 453

### Exercise 3

Remove this text, and add your answer for Exercise 1 here. Add code
chunks as needed. Don’t forget to label your code chunk. Do not use
spaces in code chunk labels.

### Exercise 4

…

### Exercise 5

…

### Exercise 6

…
