---
author: Erin Robinson
date: 8/5/2021
output:
  md_document:
    preserve_yaml: true
    variant: markdown_github
title: Dataset Eval
---

# FAIR Dataset Evaluation

This was the first time that I have tried to reproduce findings and it
was an interesting exercise. It also gave me a great opportunity to
critically look at FAIR principles with a specific dataset. This
evaluation is not meant to be at all critical of the authors of the
dataset. This report and the associated data are an excellent step
towards moving CU Boulder toward more Open Access. The evaluation is my
feedback and some suggestions to foster reuse and fairification in
future reports.

## Findable:

The Data from ‘State of Open at the University of Colorado Boulder’
Report
*D**a**t**a**s**e**t*
was findable via the citation in the report, it included a persistent
and unique digital object identifier (DOI) and using CUScholar was
available as an indexed, searchable resource. While DOIs are used, CU
may consider additional identifier links like ORCIDs for people and RORs
for organizations.

## Accessible:

Data were provided as CSV files on the DOI landing page. CSV is an open,
free and universally implementable protocol. Each year from 2012-2017
had a CSV spreadsheet. In addition there was a spreadseheet for the
OAFund and for Open Access datasets.

The focus of this evaluation will be on the I and R of FAIR. While the
data was available, the main challenge to using this data was it’s lack
of metadata beyond the report itself.

## Interoperable:

The data was shared in a way that included ‘broadly applicable language
for knowledge representation (I1)’ for humans, but was not machine
readable. All variables in the CSV were formatted as character strings,
which meant that for numbers like variable, ‘Paid.Amount - Open Access
fee paid up to $2000’ in the CUBoulderOAFund2013_2017.csv file it needed
to be converted to a number and stripped of dollar sign and commas to be
manipulated. Metadata documentation should include variable type.

## Reusable:

For reuse, the FAIR principles suggest, “the data publisher should
provide not just metadata that allows discovery, but also metadata that
richly describes the context under which the data was generated” (R1).
This would answer questions I had about how the data was collected, the
data workflow and any issues with the data.

*Variable Names:*

“Ensure that all variable names are explained or self-explanatory (i.e.,
defined in the research field’s controlled vocabulary).” - R1 There are
several references to controlled vocabulary in I and R. This dataset

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

The data are copyrighted and shared via Creative Commons BY Attribution
4.0 International. This is a good way to easily share copyrighted data.
The Rights are covered in the FAIR Principles under R.1.1.

*Community Standards:*

I am not aware of any community standards that support Open Access
reporting for organizations.

## Beyond FAIR, User Feedback:

For the file, “CUBoulderPublishedData2014_2017.csv” each line was a
dataset. I would have also liked to see links to the DOI or landing
page, name of the dataset and reference to the paper in addition to the
yes/no values provided.

Not all data shared in the report was published. I was curious about
data from CUBES referenced in Finding 1 and data that was referenced in
Finding 3.

## Suggestions to FAIR-ify the data:

From the evaluation above, this dataset is partially FAIR. Through this
project, I retrieved the data and started to analyse the retrieved
dataset and inspected the contents. The license was defined and through
CUScholar the dataset could be updated and re-deployed.

Determining the semantic model in a machine readable way

Make the data linkable with additional identifiers

Define the metadata for the dataset with richer descriptions of
variables as well as provenance.
