## Introductory steps - phase 1

The introductory steps are a guided process through which:

* we spell out clearly how R can be used for a basic data story
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

A referendum in your country is over and you are tasked to do a post-election analysis. You have data about the number of votes, demographics and geographic distribution of the votes.  In order to see what would make a good story, you decide to analyse and visualise the data.
Even though you normally work with spreadsheets, you want to try R.  Here are a few reasons why:

Excel | R 
--- | ---
It's a "point and click program" | You write a functions directly in the R interface and R does all the magic
If you want to repeat a process you have to do it every time | R allows for automation of processes that have to be repeated.  rite once, reuse several times: Not only you can update your code easily, but you can easily share it with other projects.
Only allows some types of files | Can load different kinds of files that can be complicated or impossible to work with in Excel
.... | .....

> **Wait, what?**
>   
> how do I even know how write R code? I'm not a programmer! 
>    
> Well you don't need to: as long as you understand what you want to do, you will probably find an answer in the [documentation](), [tutorials]() or [existing projects]().

We are going to guide you in each step, don't worry, it won't be that hard. Let's start with getting the data.

### Getting the data

You stretch your arms, grab a coffee, and off you go! First, you have to find the electoral data. For this example, we are going to analyze the Brexit Referendum Results.  The results data, compiled by the Electoral Comission are available [here](https://github.com/school-of-data/r-consortium-proposal/blob/master/material/lessons/results.csv) 
in .csv format 

You also want to align it with a dataset which gives various demographic information about regions, in order to try various analyses. We are going to use 2 files: a .dta file (a filetype that you can not open in Excel) that is available [here](https://github.com/school-of-data/r-consortium-proposal/blob/master/material/lessons/demographics2.dta)  and a .xlsx file available [here](https://github.com/school-of-data/r-consortium-proposal/blob/master/material/lessons/demographics1.xlsx). 

Let's download those 3 files and store them in a folder called `electoral-data`.
Your must have 2 files in your folder:  
`results.cvs`
`demographics1.xlsx`
`demographics2.dta`

Now let's try reading in the data:
1. Open your R editor (e.g. RStudio)
2. Set your working directory to `electoral-data`. To do this enter
```{r, eval=FALSE}
setwd("/PATH/electoral-data")
```
in the console.
Then, we are going to need two specialised packages to read .dta and .xlsx files into R: `xlsx` and `foreign`.
To install the packages run
```{r, eval=FALSE}
install.packages("xlsx")
install.packages("foreign")
```
To load the packages run
```{r}
library("xlsx") 
library("foreign") 
```
Now we can read the data: 
```{r}
results <- read.csv("results.csv", header = TRUE)
demographic1 <- read.xlsx(Path = "<Path to file>", sheetIndex = 1)
demographic2 <- read.dta("<Path to file>")

```

See? That was easy! Now you have your data loaded into the program and can start working.  
Are you seeing the magic yet? 
* A simple line of code can replace cumbersome manual operations that you have to do in Excel to import the data
* R loads all sort of file formats, and doesn't complain
* Write once, reuse several times: Not only you can update your code easily, but you can easily share it with other projects.
* Your stagiaire doesn't know where to find the relevant data? no problem, the links are all in the R code!

> **Let's review the commands we learned in this step:**
>
> set your folder `setwd()` 
> Install Packages `install.packages()`
> Load Libraries `library()`
> Read files `read.csv` `read.xlsx` `read.dta`


> **Want to learn what other types of data can be imported into R**
>   
> [Check this!](https://www.datacamp.com/community/tutorials/r-data-import-tutorial#gs.oZSkvFo)
>    

Now let's move on with the analysis!

### Verifying the data
Now that you have imported your data into R, it's time to start exploring it.  Here are some useful commands:

- `names()` shows the collumn names of the data frame
```{r}
names(results)
names(demographic1)
names(demographic2)
```
- `str()` shows the type of each variable (here `num` for numeric and `chr` for character) and the
first few values
```{r}
str()
```
Now that you know the variables of your databases is time to start with the cleaning part.
    

### Cleaning the data
Before you can start your analysis, you need a clean database with all the information.  Nevertheless you have the information scattered in 3 different data.frames, which you would like to combine.  
To merge two or more datasets we need a common variable.  In the previous step, where we explored the data you can see that the three databases have the variable: area_code.  What we want to do is to add the demographic variables `median_age` `prof_ocu_1` `prof_ocu_2` `born_uk` `no_educ` and `higher_educ` to the results database.
To do this we are going to use the `merge` function.
Simply type:


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
