
<!-- README.md is generated from README.Rmd. Please edit that file -->
belex
=====

belex downloads historical financial time series from the Belgrade Stock Exchange. One can specify which ticker or index to download, start and end date.

The package is available on the CRAN:

<https://cran.r-project.org/web/packages/belex/index.html>

Installation
------------

Install the release version from CRAN:

``` r
install.packages("belex")
```

Example
-------

``` r
library(belex)

blx15 <- belex("belex15")
#> Download Complete!
#> 
#> Ticker: BELEX15 
#> From: 2005-10-04 
#> To: 2016-09-02 
#> No rows: 2751

niis <- belex("NIIS", "2011-01-01", "2015-12-31")
#> Download Complete!
#> 
#> Ticker: NIIS 
#> From: 2011-01-04 
#> To: 2015-12-31 
#> No rows: 1260
```

``` r
str(blx15)
#> List of 5
#>  $ ticker: chr "BELEX15"
#>  $ from  : Date[1:1], format: "2005-10-04"
#>  $ to    : Date[1:1], format: "2016-09-02"
#>  $ nrows : int 2751
#>  $ data  :'data.frame':  2751 obs. of  6 variables:
#>   ..$ Date  : Date[1:2751], format: "2005-10-04" ...
#>   ..$ Close : num [1:2751] 998 1009 1020 1028 1035 ...
#>   ..$ Open  : num [1:2751] 996 1004 1013 1027 1031 ...
#>   ..$ Low   : num [1:2751] 1004 1009 1024 1033 1035 ...
#>   ..$ High  : num [1:2751] 991 1004 1010 1024 1023 ...
#>   ..$ Volume: num [1:2751] 30413239 35757879 33084036 25669772 34803352 ...
```

``` r
head(blx15$data)
#>         Date   Close    Open     Low    High   Volume
#> 1 2005-10-04  998.50  995.59 1004.00  991.32 30413239
#> 2 2005-10-05 1009.26 1003.60 1009.26 1003.58 35757879
#> 3 2005-10-06 1019.67 1013.44 1023.95 1009.80 33084036
#> 4 2005-10-07 1028.04 1027.25 1032.81 1023.83 25669772
#> 5 2005-10-10 1034.93 1031.19 1034.93 1022.82 34803352
#> 6 2005-10-11 1033.66 1030.54 1035.41 1023.24 35395378
```
