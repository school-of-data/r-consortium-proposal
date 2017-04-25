## In what contexts would a journalist use R instead of Excel?

### Some resources

* https://www.r-bloggers.com/using-excel-versus-using-r/
* https://www.quora.com/Why-is-SAS-and-R-programming-used-instead-of-MS-excel
* http://blog.revolutionanalytics.com/2014/10/why-r-is-better-than-excel.html
* https://r-dir.com/blog/2013/11/r-vs-excel-for-data-analysis.html
* https://www.rforexcelusers.com/excel-vs-r-when-to-use-what/

### When Excel can not do it

* working with large volumes of data, for example: electoral data, household surveys, census data. 
* Make advanced statistical analysis.
* Create less common visualisations quickly (violon chart, slope graph) to explore the data
* keep track of the changes and allow reproducibility of the contents

### When Excel can not do it as well

* make transformations to variables: create new variables, transform variables, delete values or observations. (Even though you can do this in Excel, it’s easier to do it in R with a few lines of code)
* Create publishable data visualizations without the need of using another program after doing the analysis.  
* automate easily some processes (VBA vs R code)

## In what context would Excel make sense instead of R?

...

## Which dataset can be used to quickly guide a learner through the R vs Excel differences

* electoral data (most likely available in all countries where we want to localise the content)

## Introductory steps - phase 1

### Get

In Excel: have to download the data manually, open it, and make sure that you know where to put the data.
In R: add url to line of code.
Relevant advantage: automate easily some processes

### Verify

In Excel: creating sums of elements to check against total, etc. 
In R: ...

### Clean

...

### Analyse

...

### Visualise

## Introductory steps - phase 2

### recipe1: more advanced electoral map. 

**context**: we're going to use the same dataset, and rerun the programme until the cleaning phase.
**relevant advantage**: keep track of the changes and allow reproducibility of the contents
steps: ....

### recipe2 : analysing electoral map against other demographic data

**context**: we're going to use a functionality of R which allows you to easily merge datasets, and automate the download of two different datasets to be merged! 
**relevant advantage**:  ...

### recipe3: when something goes wrong

**context**: we're going to add another layer of information, but we'll also have to fix a mistake in the code.
**relevant advantage**: ...
