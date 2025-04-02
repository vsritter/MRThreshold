
<!-- README.md is generated from README.Rmd. Please edit that file -->

# MRThreshold

<!-- badges: start -->
<!-- badges: end -->

The goal of MRThreshold is to simulate microrandomized trials subject to
a capacity constrain.

## Installation

You can install the development version of MRThreshold from
[GitHub](https://github.com/) with:

``` r
# install.packages("pak")
pak::pak("vsritter/MRThreshold")
```

## Example

To simulate the trajectory of 100 patients subject to a capacity of 5
(see the example of a model specification for the *4T Sustainnability
Microrandomized* Trial in the package website)

``` r
library(MRThreshold)

RNGkind("L'Ecuyer-CMRG")
set.seed(365342)

sim_list <- sim_microrand(N = 100, capacity = 5)
sim_list
#> $lmer_reg
#> # A tibble: 43 × 13
#>    sample_size set       b3 up_to_time n_clust n_obs effect term     estimate
#>          <dbl> <chr>  <dbl>      <dbl>   <int> <int> <chr>  <chr>       <dbl>
#>  1         100 A1    0.005          16      14    19 fixed  time:trt 0.00815 
#>  2         100 A2    0.0025         16      15    21 fixed  time:trt 0.000673
#>  3         100 A3    0.001          16      14    22 fixed  time:trt 0.000123
#>  4         100 A4    0.0005         16      10    19 fixed  time:trt 0.00214 
#>  5         100 A5    0.0001         16      11    19 fixed  time:trt 0.00211 
#>  6         100 B5    0.0001         16       6     9 fixed  time:trt 0.00497 
#>  7         100 C1    0              16      10    14 fixed  time:trt 0.00373 
#>  8         100 A1    0.005          24      41    72 fixed  time:trt 0.00600 
#>  9         100 A2    0.0025         24      47    80 fixed  time:trt 0.00298 
#> 10         100 A3    0.001          24      42    85 fixed  time:trt 0.000937
#> # ℹ 33 more rows
#> # ℹ 4 more variables: std.error <dbl>, statistic <dbl>, df <dbl>, p.value <dbl>
#> 
#> $summary
#> # A tibble: 345 × 6
#>    sample_size set    time Addon Default atRisk
#>          <dbl> <chr> <dbl> <dbl>   <dbl>  <dbl>
#>  1         100 A1        6     1       0      1
#>  2         100 A1       10     1       1      2
#>  3         100 A1       11     0       2      2
#>  4         100 A1       12     0       1      1
#>  5         100 A1       13     1       2      3
#>  6         100 A1       14     1       1      2
#>  7         100 A1       15     5       2      7
#>  8         100 A1       16     1       0      1
#>  9         100 A1       17     3       2      5
#> 10         100 A1       18     2       2      4
#> # ℹ 335 more rows
```
