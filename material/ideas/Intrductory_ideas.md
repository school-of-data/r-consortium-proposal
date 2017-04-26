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
* 

## Introductory steps - phase 1

The introductory steps are a guided process through which:

* we spell out clearly how R can be used for a basic data story
* we show how Excel compares, for each step
* we introduce the reader to the basics of R, iterating on each notion learned in the previous step
* we contextualise the step within a data-driven story writing workflow.

### Main intro
_interactive quiz used as a way to start engaging the visitor right away, and to get statistics from various populations_

Are you a journalist?      
-> Yes -> No      

|____(if no) this tutorial is delibarately, intensely, exclusively focused on journalists. If you want to continue you'll have to pretend to be a journalist and, believe us, it's not pleasant. Do you still want to continue?

____ -> Yes -> No     

     |     
     |____ (if yes) Have you ever heard about this thing we call R?     

     ____-> Yes -> No   
         |     
         |____ (if no) Well, despite its mysterious and concise name, R is an open source programming 
         language and environment for statistical computing, widely used among data analysts, statisticians, 
         programmers and more recently, by data journalists.   Our mission today will be to convince you
         that R is worth your precious time and will help you improve your work in the newsroom. 
         
         |     
         |____ (if yes) Do you already use R your work?     

          ____-> Yes -> No   

                |    
                |____________ (if yes) What follows is a beginner tutorial for R-newbies. 
                You could jump directly to [our list of R recipes]() or still follow the introduction tutorial 
                to steal ideas for your own R trainings (we know who you are!).

                |     
                |____________ (if no) So an R atheist? Or maybe agnostic? 
                Our mission will be to convice you to actually start using R in your workflow. 
                If we fail, we allow you the privilege to send us an angry tweet.

      --------------------     
     | Challenge accepted |    
      --------------------    

### The context
_Here we set up the story that will be used to contextualise all actions in the tutorial_

The presidential election is over, you are tasked to do a post-election analysis. Geographic distribution of the votes, demographics of the vote, many angles are possible. In order to see what would make a godo story, you decide to analyse and visualise the data.

### Getting the data

You stretch your arms, grab a coffee, and off you go. First, the data. The ministry of the interior publishes the detailed election data, in xml format (?){what is XML?}. Ugh, Excel doesn't read that easily.

You also want to align it with a dataset which gives various information about regions, in order to try various analyses. The file you use is published by the National Statistics Institute in CSV format. Excel reads those. Good.

Now let's get to work:

Step | Excel | R 
--- | --- | ---
1 | You download the two data files from their respective websites | You write a function directly in the R interface which downloads and loads the data, allowing you to only change the URL to update this part of the process next year.
2 | You opt to convert the XML data using an XML converter. The result is not perfect, but you can work with it now. |
3 | You load the files in your Excel workbook, within two different spreadsheets. | 

Step saved using R: 2. Winner? R!

* A simple line of code can replace cumbersome manual operations
* R loads all sort of file formats, and doesn't complain
* Write once, reuse several times: Not only you can update your code easily, but you can easily share it with other projects.
* Your stagiaire doesn't know where to find the relevant data? no problem, the links are all in the R code!

> **Wait, what?**
>   
> how do I even know how write this code? I'm not a programmer! 
>    
> Well you don't need to: as long as you understand what you want to do, you will probably find an answer in the [documentation](), [tutoriels]() or [existing projects]().

**Are you convinced yet that R is worth your time?**     
____ not really    
____ hmmm, I need to see more to decide     
____ yes, R won my heart     

### Verifying the data

In Excel: creating sums of elements to check against total, etc.     
In R: ...    

### Cleaning the data

...

#### Analysing the data

...

### Showing analysis to your colleagues

(in order to choose one or several angles, for example).

### Try various visualisations

...

### Edit the visualisations based on feedback from your editor

...

### Send the final visualisation and article to the online editor

...

### Send another version of the visualisation to the print editor

...

This was the last step! Are you convinced yet? If not, check out [other scenarios]() or [send us an angry tweet]()

## Introductory steps - phase 2

### recipe1: more advanced electoral map. 

**context**: we're going to use the same dataset, and rerun the programme until the cleaning phase.    
**relevant advantage**: keep track of the changes and allow reproducibility of the contents    
steps: ....

### recipe2 : analysing electoral map against other demographic data

**context**: we're going to use a functionality of R which allows you to easily merge datasets, and automate the download of two different datasets to be merged!     
**relevant advantage**:  ...

### recipe3: when something goes wrong

**context**: we're going to add another layer of information and use R code from your colleague, but we'll also have to fix a mistake in the code.    
**relevant advantage**: ...
