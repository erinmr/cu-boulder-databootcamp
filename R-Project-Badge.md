---
author: Erin Robinson
date: 8/5/2021
output:
  md_document:
    preserve_yaml: true
    variant: markdown_github
title: R Project Badge
---

# Research Question

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

I used data available from CUScholar  
Johnson, A., Caillet, R., Cantrell, M. H., & Mika, K. (2018). Data from
‘State of Open at the University of Colorado Boulder’ Report
*D**a**t**a**s**e**t*
. University Libraries, University of Colorado Boulder.
<https://doi.org/10.25810/ZNB1-3K90>

## Finding 1

-   10.20% of all articles published in 2017 by CU Boulder authors were
    published in full OA journals;

``` r
# call Tidyverse library  
library(tidyverse)

# Read in CUBoulderOAArticles2017.csv
CUBoulderOAArticles2017 <- read.csv('data/StateOfOpenCUBoulderData/CUBoulderOAArticles2017.csv')

# Each row is an Open Access article. Use nrow to count number of rows and assign to variable totaloa2017
totaloa2017 <- nrow(CUBoulderOAArticles2017)

# Write out results for total number of OA articles
cat("From the data provided, it is possible to get the total number of open access articles ->", totaloa2017,".")
```

    ## From the data provided, it is possible to get the total number of open access articles -> 506 .

``` r
# Calculate percentage based on average annually number reported in report
perctotal0a2017 <- totaloa2017/5000*100

# Write out results for percentage of total number of OA articles compared to total number of papers 
cat(" The report indicated that CU Boulder publishes around 5000 papers annually. From that statement the percent of OA papers ->", perctotal0a2017, "%. ")
```

    ##  The report indicated that CU Boulder publishes around 5000 papers annually. From that statement the percent of OA papers -> 10.12 %.

No data is provided for the overall number of publication from
CU-Boulder for 2017. There is a reference to CU publishing around 5000
papers annually and to CUBE in the text.

Note: It is possible to search the [DataCite Commons for CU-Boulder ROR,
organizational identifiers, for
2017](https://commons.datacite.org/ror.org/02ttsq026?rorid=02ttsq026&published=2017).
Here we find that there are only 52 works that utilize the ROR that are
available. If all research works utilized CU’s ROR, we would be able to
identify total number of papers published affiliated with CU and then
the OA papers/All papers would find % of work published as OA.

## Finding 2

-   *From 2013 to 2017, the Libraries OA Fund funded author fees
    totaling $163,522.40 for 116 journal articles published by CU
    Boulder authors in full OA journals;*

``` r
# call Tidyverse library  
library(tidyverse)

# Read in CUBoulderOAFund2013_2017.csv
CUBoulderOAFund2013_2017 <- data.frame(read.csv('data/StateOfOpenCUBoulderData/CUBoulderOAFund2013_2017.csv'))

# Explore data by printing a summary of the spreadsheet. This tells us there are six variables, 116 rows and all variables are character strings  
summary(CUBoulderOAFund2013_2017)
```

    ##  Date..First.Contact.    Status           Department        Journal.title     
    ##  Length:116           Length:116         Length:116         Length:116        
    ##  Class :character     Class :character   Class :character   Class :character  
    ##  Mode  :character     Mode  :character   Mode  :character   Mode  :character  
    ##   Publisher         Paid.Amount       
    ##  Length:116         Length:116        
    ##  Class :character   Class :character  
    ##  Mode  :character   Mode  :character

``` r
# For Finding 1 we need to sum the column Paid.Amount 
# First we must convert the column from character to numeric class 

# Special characters need to be removed. Remove the $ and , from the Paid.Amount column and assign new variable, Paid.Amountst  
Paid.Amountst <- stringr::str_remove_all(CUBoulderOAFund2013_2017$Paid.Amount,"[$,]")

# Convert the Paid.Amountst character string into a number using as.numeric and assign to a new variable Paid.AmountNum 
Paid.AmountNum <- as.numeric(Paid.Amountst)

# Sum the entire Paid.AmountNum column. There are some fields, so we set na.rm to True. Assign the sum to a new variable called Total.Paid
Total.Paid <- sum(Paid.AmountNum, na.rm = TRUE)

# Print Total.Paid
cat("$",Total.Paid," equals finding 2 From 2013 to 2017, the Libraries OA Fund funded author fees totaling $163,522.40.")
```

    ## $ 163522.4  equals finding 2 From 2013 to 2017, the Libraries OA Fund funded author fees totaling $163,522.40.

``` r
# Each row represents a journal article, so counting the rows with nrow should give the total number of journal articles 
totaloa2013_2017 <- nrow(CUBoulderOAFund2013_2017)
cat(totaloa2013_2017, "matches the 116 journal articles published by CU Boulder authors in full OA journals from finding 2.")
```

    ## 116 matches the 116 journal articles published by CU Boulder authors in full OA journals from finding 2.

## Finding 3

-   *As of April 2018, there were 7,732 OA items in the CU Scholar
    institutional repository run by the Libraries, and these items were
    downloaded a total of 477,695 times in 2017 alone;*

The data shared only included journal publications and data. There was
no data included to support this finding.

## Finding 4

-   *Published datasets became a reportable scholarly activity in the
    annual Faculty Report of Professional Activities in 2014, and
    faculty reported 33 data sets in 2017 (up from 12 in 2014) with 16
    of these citations including Digital Object Identifiers (DOIs).*

``` r
library(tidyverse)
# Read in CUBoulderOAFund2013_2017 and review the data. There are 7 variables and 87 rows. All variables are character strings 
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
#Identify the number of datasets in 2014 by filtering data for Year equal to 2014, counting the rows with nrow which equal number of datasets in 2014. Assign the number to a variable data14
data14 <- nrow(filter(data, Year == '2014'))

#Check data14 is correct
#data14

#Repeat process for identifying the number of datasets in 2017 as above for 2014. 
data17 <- nrow(filter(data, Year == '2017'))

#Check data17 is correct
#data17

#Number of datasets with a DOI in 2017 is found by filtering the table to just datasets from 2017 and assigning that to a variable, doi17a
doi17a <- filter(data, Year == '2017')

#doi17a is then filtered again for the variable DOI...yes.or.no equal to yes and nrow is used to count the resulting filtered rows. 
doi17b <-nrow(filter(doi17a, DOI...yes.or.no =='Yes'))

#check doi17b is correct
#doi17b

cat("Print results for Finding 4 -> Published datasets became a reportable scholarly activity in the annual Faculty Report of Professional Activities in 2014, and faculty reported", data17, "data sets in 2017 (up from", data14, "in 2014) with", doi17b," of these citations including Digital Object Identifiers (DOIs).")
```

    ## Print results for Finding 4 -> Published datasets became a reportable scholarly activity in the annual Faculty Report of Professional Activities in 2014, and faculty reported 33 data sets in 2017 (up from 12 in 2014) with 16  of these citations including Digital Object Identifiers (DOIs).

# FAIR Dataset Evaluation

This was the first time that I have tried to reproduce findings and it
was an interesting exercise. It also gave me a great opportunity to
critically look at FAIR principles with a specific dataset. This
evaluation is not meant to be at all critical of the authors of the
dataset. This report and the associated data are an excellent step
towards moving CU Boulder toward more Open Access. The evaluation is my
feedback and some suggestions to foster reuse and
[fairification](https://www.go-fair.org/fair-principles/fairification-process/)
in future reports.

**Findable:** The Data from ‘State of Open at the University of Colorado
Boulder’ Report
*D**a**t**a**s**e**t*
was findable via the citation in the report, it included a persistent
and unique digital object identifier (DOI) and using CUScholar was
available as an indexed, searchable resource. While DOIs are used, CU
may consider additional identifier links like ORCIDs for people and RORs
for organizations.

**Accessible:** Data were provided as CSV files on the DOI landing page.
CSV is an open, free and universally implementable protocol. Each year
from 2012-2017 had a CSV spreadsheet. In addition there was a
spreadseheet for the OAFund and for Open Access datasets.

The focus of this evaluation will be on the I and R of FAIR. While the
data was available, the main challenge to using this data was it’s lack
of metadata beyond the report itself.

**Interoperable:** The data was shared in a way that included ‘broadly
applicable language for knowledge representation
([I1](https://www.go-fair.org/fair-principles/i1-metadata-use-formal-accessible-shared-broadly-applicable-language-knowledge-representation/))’
for humans, but was not machine readable. All variables in the CSV were
formatted as character strings, which meant that for numbers like
variable, ‘Paid.Amount - Open Access fee paid up to \\$2000’ in the
CUBoulderOAFund2013_2017.csv file it needed to be converted to a number
and stripped of dollar sign and commas to be manipulated. Metadata
documentation should include variable type.

**Reusable:** For reuse, the FAIR principles suggest, “the data
publisher should provide not just metadata that allows discovery, but
also metadata that richly describes the context under which the data was
generated”
([R1](https://www.go-fair.org/fair-principles/r1-metadata-richly-described-plurality-accurate-relevant-attributes/)).
This would answer questions I had about how the data was collected, the
data workflow and any issues with the data.

*Variable Names:*

“Ensure that all variable names are explained or self-explanatory (i.e.,
defined in the research field’s controlled vocabulary).” -
[R1](https://www.go-fair.org/fair-principles/r1-metadata-richly-described-plurality-accurate-relevant-attributes/)
There are several references to controlled vocabulary in I and R. This
dataset

Column headings between 2012 and 2017 were consistent except for date
which was shown as
“Publication.date.OR.Publication.date.or.Presentation.Date.OR.Presentation.date.OR.Presented.date.OR.Date.awarded.OR.Date”
- Variety of different kinds of dates in single column. Format is Year
or YYYY-MM or MM/DD/YY” in all years but 2015 and 2017, where it is
“Publication.date” - Variety of different kinds of dates in single
column. Format is Year or YYYY-MM or MM/DD/YY. With this variety of
different types of date and different date formats, it would be
difficult to do anything with it. A suggested alternative might be to
include multiple date columns for each type or have a second column that
indicates type may also work. In the Readme file for this project, I
suggested what I thought the column headings might mean, but this needs
verification from the authors. Including a readme in CUScholar with the
data would be a helpful addition for Reuse.

*Rights:*

The data are copyrighted and shared via [Creative Commons BY Attribution
4.0
International](https://scholar.colorado.edu/catalog?q=http://creativecommons.org/licenses/by/4.0/&search_field=license).
This is a good way to easily share copyrighted data. The Rights are
covered in the FAIR Principles under
[R.1.1](https://www.go-fair.org/fair-principles/r1-1-metadata-released-clear-accessible-data-usage-license/).

*Community Standards:*

I am not aware of any community standards that support Open Access
reporting for organizations.

**Beyond FAIR, User Feedback**: For the file,
“CUBoulderPublishedData2014_2017.csv” each line was a dataset. I would
have also liked to see links to the DOI or landing page, name of the
dataset and reference to the paper in addition to the yes/no values
provided.

Not all data shared in the report was published. I was curious about
data from CUBES referenced in Finding 1 and data that was referenced in
Finding 3.

**To
[FAIR-ify](https://www.go-fair.org/fair-principles/fairification-process/)
the data the key things needed are:**

This dataset is partially FAIR. Through this work, I retrieved the data
and started to analyse the retrieved dataset and inspected the contents.
The license was defined and through CUScholar the dataset could be
updated and re-deployed.

1.  Determining the semantic model in a machine readable way
2.  Make the data linkable with additional identifiers
3.  Define the metadata for the dataset with richer descriptions of
    variables as well as provenance.
