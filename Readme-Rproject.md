---
author: Erin Robinson
date: 8/5/2021
output:
  md_document:
    preserve_yaml: true
    variant: markdown_github
title: Data Readme
---

## General Information

The readme is based on [this
example](https://drive.google.com/file/d/1h_iBgq3HY0yXyJXDwWpi80GMC2Z4fO9U/view)
shared during out bootcamp.

1\. Title of Dataset: Data from “State of Open at the University of
Colorado Boulder” Report

2\. Authors:

-   Caillet, Ryan

-   Johnson, Andrew

-   Mika, Katie

-   Cantrell, Melissa H.

3\. Contact information: None given

4\. Date of data collection:

-   issued data: 2018-01-01

-   Uploaded date: 2019-12-19

## Sharing/Access Information

1\. Licenses/restrictions placed on the data:

in Copyright and [Creative Commons BY Attribution 4.0
International](https://scholar.colorado.edu/catalog?q=http://creativecommons.org/licenses/by/4.0/&search_field=license)

2\. Links to publications that cite or use the data:

“State of Open At the University of Colorado Boulder: A Baseline
Analysis of Open Access Practices from 2012 to 2018” can be found here:
<https://doi.org/10.25810/vprn-v113.>

3\. Links to other publicly accessible locations of the data:

<https://scholar.colorado.edu/concern/datasets/df65v878g>

4\. Recommended citation for the data:

Johnson, A., Caillet, R., Cantrell, M. H., & Mika, K. (2018). Data from
‘State of Open at the University of Colorado Boulder’ Report
*D**a**t**a**s**e**t*
. University Libraries, University of Colorado Boulder.
<https://doi.org/10.25810/ZNB1-3K90>

## Data & File Overview

1.  File List:

    1.  Filename: CUBoulderOAArticles2012

    2.  Filename: CUBoulderOAArticles2013

    3.  Filename: CUBoulderOAArticles2014

    4.  Filename: CUBoulderOAArticles2015

    5.  Filename: CUBoulderOAArticles2016

    6.  Filename: CUBoulderOAArticles2017

    7.  Filename: CUBoulderOAFund2013_2017

    8.  Filename: CUBoulderPublishedData2014_2017

2\. Relationship between files:

No relationship specified

## Methodological Information

``` r
#library(tidyverse)
# Sample code to read in  files below and review the data Commented out because it doesn't need to run for the readme. For each file below the string can be updated for the file name
# data <- read.csv('data/StateOfOpenCUBoulderData/CUBoulderPublishedData2014_2017.csv')
# Extract column (variable) names
# colnames(data)
# Print summary of each variable
# summary(data)
```

### DATA-SPECIFIC INFORMATION FOR:CUBoulderOAArticles2012

1\. Number of variables:

17

2\. Number of cases/rows:

496

3\. Variable List: Descriptions added by E. Robinson

-   
    1
    “Department” - Department at CU-Boulder

-   
    2
    “DOI” - Digital Object Identifier

-   
    3
    “eISSN” - Electronic International Standard Serial Number

-   
    4
    “ISSN” - International Standard Serial Number

-   
    5
    “Issue” - Journal Issue

-   
    6
    “Title.of.Journal”

-   
    7
    “Language” - Language of publication. Generally English or eng

-   
    8
    “Pagination..start.page.” - Article start page

-   
    9
    “Pagination..end.page.” - Article end page

-   
    10
    “Pagination..page.count.” - Article number of pages

-   
    11
    “Publication.date.OR.Publication.date.or.Presentation.Date.OR.Presentation.date.OR.Presented.date.OR.Date.awarded.OR.Date” -
    Variety of different kinds of dates in single column. Format is Year
    or YYYY-MM or MM/DD/YY

-   
    12
    “Publisher”

-   
    13
    “Title” - Title of Article

-   
    14
    “Volume”

-   
    15
    “Indexed.in.DOAJ” Is the article indexed in the Directory of Open
    Access Journals

-   
    16
    “DOAJ.CC.Licence” Indicates if the article has a CC license with
    type CC BY, CC BY-NC-SA, CC BY-NC - ND

-   
    17
    “Romeo.colour” ??

4\. Data codes (e.g., N/A = Not applicable):Unknown are blank

### DATA-SPECIFIC INFORMATION FOR:CUBoulderOAArticles2013

1\. Number of variables:

17

2\. Number of cases/rows:

555

3\. Variable List: Descriptions added by E. Robinson

-   
    1
    “Department” - Department at CU-Boulder

-   
    2
    “DOI” - Digital Object Identifier

-   
    3
    “eISSN” - Electronic International Standard Serial Number

-   
    4
    “ISSN” - International Standard Serial Number

-   
    5
    “Issue” - Journal Issue

-   
    6
    “Title.of.Journal”

-   
    7
    “Language” - Language of publication. Generally English or eng

-   
    8
    “Pagination..start.page.” - Article start page

-   
    9
    “Pagination..end.page.” - Article end page

-   
    10
    “Pagination..page.count.” - Article number of pages

-   
    11
    “Publication.date.OR.Publication.date.or.Presentation.Date.OR.Presentation.date.OR.Presented.date.OR.Date.awarded.OR.Date” -
    Variety of different kinds of dates in single column. Format is Year
    or YYYY-MM or MM/DD/YY

-   
    12
    “Publisher”

-   
    13
    “Title” - Title of Article

-   
    14
    “Volume”

-   
    15
    “Indexed.in.DOAJ” Is the article indexed in the Directory of Open
    Access Journals

-   
    16
    “DOAJ.CC.Licence” Indicates if the article has a CC license with
    type CC BY, CC BY-NC-SA, CC BY-NC - ND

-   
    17
    “Romeo.colour” ??

4\. Data codes (e.g., N/A = Not applicable):Unknown are blank

### DATA-SPECIFIC INFORMATION FOR:CUBoulderOAArticles2014

1\. Number of variables:

17

2\. Number of cases/rows:

577

3\. Variable List: Descriptions added by E. Robinson

-   
    1
    “Department” - Department at CU-Boulder

-   
    2
    “DOI” - Digital Object Identifier

-   
    3
    “eISSN” - Electronic International Standard Serial Number

-   
    4
    “ISSN” - International Standard Serial Number

-   
    5
    “Issue” - Journal Issue

-   
    6
    “Title.of.Journal”

-   
    7
    “Language” - Language of publication. Generally English or eng

-   
    8
    “Pagination..start.page.” - Article start page

-   
    9
    “Pagination..end.page.” - Article end page

-   
    10
    “Pagination..page.count.” - Article number of pages

-   
    11
    “Publication.date.OR.Publication.date.or.Presentation.Date.OR.Presentation.date.OR.Presented.date.OR.Date.awarded.OR.Date” -
    Variety of different kinds of dates in single column. Format is Year
    or YYYY-MM or MM/DD/YY

-   
    12
    “Publisher”

-   
    13
    “Title” - Title of Article

-   
    14
    “Volume”

-   
    15
    “Indexed.in.DOAJ” Is the article indexed in the Directory of Open
    Access Journals

-   
    16
    “DOAJ.CC.Licence” Indicates if the article has a CC license with
    type CC BY, CC BY-NC-SA, CC BY-NC - ND

-   
    17
    “Romeo.colour” ??

4\. Data codes (e.g., N/A = Not applicable):Unknown are blank

### DATA-SPECIFIC INFORMATION FOR:CUBoulderOAArticles2015

1\. Number of variables:

17

2\. Number of cases/rows:

624

3\. Variable List: Descriptions added by E. Robinson (NOTE Publication
date was simplified in 2015)

-   
    1
    “Department” - Department at CU-Boulder

-   
    2
    “DOI” - Digital Object Identifier

-   
    3
    “eISSN” - Electronic International Standard Serial Number

-   
    4
    “ISSN” - International Standard Serial Number

-   
    5
    “Issue” - Journal Issue

-   
    6
    “Title.of.Journal”

-   
    7
    “Language” - Language of publication. Generally English or eng

-   
    8
    “Pagination..start.page.” - Article start page

-   
    9
    “Pagination..end.page.” - Article end page

-   
    10
    “Pagination..page.count.” - Article number of pages

-   
    11
    “Publication.date” - Variety of different kinds of dates in single
    column. Format is Year or YYYY-MM or MM/DD/YY

-   
    12
    “Publisher”

-   
    13
    “Title” - Title of Article

-   
    14
    “Volume”

-   
    15
    “Indexed.in.DOAJ” Is the article indexed in the Directory of Open
    Access Journals

-   
    16
    “DOAJ.CC.Licence” Indicates if the article has a CC license with
    type CC BY, CC BY-NC-SA, CC BY-NC - ND

-   
    17
    “Romeo.colour” ??

4\. Data codes (e.g., N/A = Not applicable):Unknown are blank

### DATA-SPECIFIC INFORMATION FOR:CUBoulderOAArticles2016

1\. Number of variables:

17

2\. Number of cases/rows:

591

3\. Variable List: Descriptions added by E. Robinson (NOTE Publication
date changes back to 2012 variables)

-   
    1
    “Department” - Department at CU-Boulder

-   
    2
    “DOI” - Digital Object Identifier

-   
    3
    “eISSN” - Electronic International Standard Serial Number

-   
    4
    “ISSN” - International Standard Serial Number

-   
    5
    “Issue” - Journal Issue

-   
    6
    “Title.of.Journal”

-   
    7
    “Language” - Language of publication. Generally English or eng

-   
    8
    “Pagination..start.page.” - Article start page

-   
    9
    “Pagination..end.page.” - Article end page

-   
    10
    “Pagination..page.count.” - Article number of pages

-   
    11
    “Publication.date.OR.Publication.date.or.Presentation.Date.OR.Presentation.date.OR.Presented.date.OR.Date.awarded.OR.Date” -
    Variety of different kinds of dates in single column. Format is Year
    or YYYY-MM or MM/DD/YY”

-   
    12
    “Publisher”

-   
    13
    “Title” - Title of Article

-   
    14
    “Volume”

-   
    15
    “Indexed.in.DOAJ” Is the article indexed in the Directory of Open
    Access Journals

-   
    16
    “DOAJ.CC.Licence” Indicates if the article has a CC license with
    type CC BY, CC BY-NC-SA, CC BY-NC - ND

-   
    17
    “Romeo.colour” ??

4\. Data codes (e.g., N/A = Not applicable):Unknown are blank

### DATA-SPECIFIC INFORMATION FOR:CUBoulderOAArticles2017

1\. Number of variables:

17

2\. Number of cases/rows:

506

3\. Variable List: Descriptions added by E. Robinson (NOTE Publication
date was simplified again in 2017)

-   
    1
    “Department” - Department at CU-Boulder

-   
    2
    “DOI” - Digital Object Identifier

-   
    3
    “eISSN” - Electronic International Standard Serial Number

-   
    4
    “ISSN” - International Standard Serial Number

-   
    5
    “Issue” - Journal Issue

-   
    6
    “Title.of.Journal”

-   
    7
    “Language” - Language of publication. Generally English or eng

-   
    8
    “Pagination..start.page.” - Article start page

-   
    9
    “Pagination..end.page.” - Article end page

-   
    10
    “Pagination..page.count.” - Article number of pages

-   
    11
    “Publication.date” - Variety of different kinds of dates in single
    column. Format is Year or YYYY-MM or MM/DD/YY

-   
    12
    “Publisher”

-   
    13
    “Title” - Title of Article

-   
    14
    “Volume”

-   
    15
    “Indexed.in.DOAJ” Is the article indexed in the Directory of Open
    Access Journals

-   
    16
    “DOAJ.CC.Licence” Indicates if the article has a CC license with
    type CC BY, CC BY-NC-SA, CC BY-NC - ND

-   
    17
    “Romeo.colour” ??

4\. Data codes (e.g., N/A = Not applicable):Unknown are blank

### DATA-SPECIFIC INFORMATION FOR: CUBoulderOAFund2013_2017.csv

1\. Number of variables: 6

2\. Number of cases/rows: 116

3\. Variable List:

    A. Date..First.Contact. - ???

    B. Status - Career status

    C. Department - CU Boulder Department

    D. Journal.title

    E. Publisher

    F. Paid.Amount - Open Access fee paid up to \$2000

4\. Data codes (e.g., N/A = Not applicable): Unknown are blank

### DATA-SPECIFIC INFORMATION FOR: CUBoulderPublishedData2014_2017.csv

1\. Number of variables: 7

2\. Number of cases/rows: 87

3\. Variable List:

    \[1\] "Year"

    \[2\] "Dept" - CU Boulder Department

    \[3\] "DOI...yes.or.no"

    \[4\] "URL...yes.or.no"

    \[5\] "Repository"

    \[6\] "References..paper..other.data....yes.or.no"

    \[7\] "License"

4\. Data codes (e.g., N/A = Not applicable): Unknown are blank
