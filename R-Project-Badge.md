---
author: Erin Robinson
date: 8/5/2021
output:
  md_document:
    preserve_yaml: true
    variant: markdown_github
title: R Project Badge
---

## Research Question

My research question is ‘Can I reproduce the findings in the Executive
Summary of the [State of Open At University of Colorado Baseline
Report?](https://scholar.colorado.edu/concern/articles/mw22v6063)’

The findings were:

-   *10.20% of all articles published in 2017 by CU Boulder authors were
    published in full OA journals;*

-   *From 2013 to 2017, the Libraries OA Fund funded author fees
    totalling $163,522.40 for 116 journal articles published by CU
    Boulder authors in full OA journals;*

-   *As of April 2018, there were 7,732 OA items in the CU Scholar
    institutional repository run by the Libraries, and these items were
    downloaded a total of 477,695 times in 2017 alone;*

-   *Published data sets became a reportable scholarly activity in the
    annual Faculty Report of Professional Activities in 2014, and
    faculty reported 33 data sets in 2017 (up from 12 in 2014) with 16
    of these citations including Digital Object Identifiers (DOIs).*

I used data available from CUScholar:  
  
Johnson, A., Caillet, R., Cantrell, M. H., & Mika, K. (2018). Data from
‘State of Open at the University of Colorado Boulder’ Report
*D**a**t**a**s**e**t*
. University Libraries, University of Colorado Boulder.
<https://doi.org/10.25810/ZNB1-3K90>

## Finding 1

-   10.20% of all articles published in 2017 by CU Boulder authors were
    published in full OA journals;

1.  I read in the CUBoulderOAArticles2017.csv file

2.  I count the rows using the nrow function and assign it a variable,
    totaloa2017

3.  I print the variable, totaloa2017

``` r
library(ggstatsplot)
CUBoulderOAArticles2017 <- read.csv('data/StateOfOpenCUBoulderData/CUBoulderOAArticles2017.csv')
totaloa2017 <- nrow(CUBoulderOAArticles2017)
totaloa2017
```

    ## [1] 506

From the data provided, it is only possible to get the total number of
open access articles. No data is provided for the overall number of
publication from CU-Boulder for 2017. There is a reference to CUBE in
the text.

It is possible to search the[DataCite Commons for CU-Boulder ROR for
2017](https://commons.datacite.org/ror.org/02ttsq026?rorid=02ttsq026&published=2017).
Here we find that there are only 52 works that utilize the ROR that are
available. If all research works utilized CU’s ROR, we would be able to
identify total number of papers.

## Finding 2

-   *From 2013 to 2017, the Libraries OA Fund funded author fees
    totalling $163,522.40 for 116 journal articles published by CU
    Boulder authors in full OA journals;*

I read in the CUBoulderOAFund2013_2017.csv file and print col names

``` r
library(ggstatsplot)
# Read in CUBoulderOAFund2013_2017
CUBoulderOAFund2013_2017 <- data.frame(read.csv('data/StateOfOpenCUBoulderData/CUBoulderOAFund2013_2017.csv'))
colnames(CUBoulderOAFund2013_2017)
```

    ## [1] "Date..First.Contact." "Status"               "Department"          
    ## [4] "Journal.title"        "Publisher"            "Paid.Amount"

``` r
Paid.Amountst <- stringr::str_remove_all(CUBoulderOAFund2013_2017$Paid.Amount,"[$,]")
Paid.AmountNum <- as.numeric(Paid.Amountst)
#Paid.AmountNum
Total.Paid <- sum(Paid.AmountNum, na.rm = TRUE)
Total.Paid
```

    ## [1] 163522.4

``` r
totaloa2013_2017 <- nrow(CUBoulderOAFund2013_2017)
totaloa2013_2017
```

    ## [1] 116

## Finding 3

-   *As of April 2018, there were 7,732 OA items in the CU Scholar
    institutional repository run by the Libraries, and these items were
    downloaded a total of 477,695 times in 2017 alone;*

There was no data included to support this finding.

## Finding 4

-   *Published datasets became a reportable scholarly activity in the
    annual Faculty Report of Professional Activities in 2014, and
    faculty reported 33 data sets in 2017 (up from 12 in 2014) with 16
    of these citations including Digital Object Identifiers (DOIs).*

``` r
library(tidyverse)
# Read in CUBoulderOAFund2013_2017 and review the data 
data <- read.csv('data/StateOfOpenCUBoulderData/CUBoulderPublishedData2014_2017.csv')
colnames(data)
```

    ## [1] "Year"                                      
    ## [2] "Dept"                                      
    ## [3] "DOI...yes.or.no"                           
    ## [4] "URL...yes.or.no"                           
    ## [5] "Repository"                                
    ## [6] "References..paper..other.data....yes.or.no"
    ## [7] "License"

``` r
summary(data)
```

    ##       Year          Dept           DOI...yes.or.no    URL...yes.or.no   
    ##  Min.   :2014   Length:87          Length:87          Length:87         
    ##  1st Qu.:2015   Class :character   Class :character   Class :character  
    ##  Median :2016   Mode  :character   Mode  :character   Mode  :character  
    ##  Mean   :2016                                                           
    ##  3rd Qu.:2017                                                           
    ##  Max.   :2017                                                           
    ##   Repository        References..paper..other.data....yes.or.no
    ##  Length:87          Length:87                                 
    ##  Class :character   Class :character                          
    ##  Mode  :character   Mode  :character                          
    ##                                                               
    ##                                                               
    ##                                                               
    ##    License         
    ##  Length:87         
    ##  Class :character  
    ##  Mode  :character  
    ##                    
    ##                    
    ## 

``` r
#Number of citations in 2014
data14 <- nrow(filter(data, Year == '2014'))
data14
```

    ## [1] 12

``` r
#Number of citations in 2017
data17 <- nrow(filter(data, Year == '2017'))
data17
```

    ## [1] 33

``` r
#Number of citations with a DOI in 2017

doi17a <- filter(data, Year == '2017')
#view(doi17a)
doi17b <-nrow(filter(doi17a, DOI...yes.or.no =='Yes'))
doi17b
```

    ## [1] 16

``` r
#Extra analysis not needed 
#length(data) # number of elements or components
#str(data)    # structure of an object
#class(data)  # class or type of an object
#names(data)  # column names

#view(CUBoulderPublishedData2014_2017)
#colnames(CUBoulderPublishedData2014_2017)
#totaloadata2014_2017 <- nrow(CUBoulderPublishedData2014_2017)
#data_2017 <- filter(CUBoulderPublishedData2014_2017, year == 2017)
#data_2017
```
