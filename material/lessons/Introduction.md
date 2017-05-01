# Introductory steps - phase 1

The introductory steps are a guided process through which:

* we spell out clearly how R can be used for a basic data story
* we introduce the reader to the basics of R, iterating on each notion learned in the previous step
* we contextualise the step within a data-driven story writing workflow.

## Main intro
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

## The context
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

## Getting the data

You stretch your arms, grab a coffee, and off you go! First, you have to find the electoral data. For this example, we are going to analyze the Brexit Referendum Results.  The results data, compiled by the Electoral Comission are available [here](https://github.com/school-of-data/r-consortium-proposal/blob/master/material/lessons/results.csv) 
in .csv format 

You also want to align it with a dataset which gives various demographic information about regions, in order to try various analyses. We are going to use 2 files: a .dta file (a filetype that you can not open in Excel) that is available [here](https://github.com/school-of-data/r-consortium-proposal/blob/master/material/lessons/demographics2.dta)  and a .xlsx file available [here](https://github.com/school-of-data/r-consortium-proposal/blob/master/material/lessons/demographics1.xlsx). 

Metadata: 

_Results_

- `id` Unique id
- `Region_Code` Region Code
- `Region` Region Name                 
- `area_code` Unique area code
- `Area` Area Name
- `Electorate` Number of registered voters             
- `ExpectedBallots` Expected ballots
- `VerifiedBallotPapers` Verified Ballots
- `Pct_Turnout` Percentage of voter turnout.  VerifiedBallotPapers/Electorate
- `Votes_Cast` Casted Votes
- `Valid_Votes` Number of Valid votes
- `Remain` Number of "Remain" votes                
- `Leave` Number of "Leave" votes                   
- `Rejected_Ballots` Number of rejected ballots

_Demographics1_
- `new_id` unique Id
- `area_code` Unique area code
- `area_name` Area Name
- `median_age` Median age of residents
- `prof_ocu_1`  Percentage of residents with higher and intermediate professional occupations 
- `prof_ocu_2`  Percentage of residents with junior professional occupations 

_Demographics2_
- `new_id` unique Id
- `area_code` Unique area code
- `area_name` Area Name
- `born_uk` Percentage of residents born in the UK
- `no_educ` Percentage of residents with no formal education
- `higher_educ` Percentage of residents with higher education

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
- set your folder `setwd()` 
- Install Packages `install.packages()`
- Load Libraries `library()`
- Read files `read.csv` `read.xlsx` `read.dta`


> **Want to learn what other types of data can be imported into R**
>   
> [Check this!](https://www.datacamp.com/community/tutorials/r-data-import-tutorial#gs.oZSkvFo)
>    

Now let's move on with the analysis!

## Verifying the data
Now that you have imported your data into R, it's time to start exploring it.  Here are some useful commands:

- `view()` shows your dataframe with all the variables and observations

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
    

## Cleaning the data
Before you can start your analysis, you need a clean database with all the information.  Nevertheless you have the information scattered in 3 different data.frames, which you would like to combine.  

Our objective is to add the demographic variables `median_age` `prof_ocu_1` `prof_ocu_2` `born_uk` `no_educ` and `higher_educ` to the results database.  But in order to do this, we need a common variable in all the datasets.  In the previous step, where we explored the data you can see that the three databases have the variable: `area_code`.  

That common variable will allow us to merge the databases using the `merge` function.

Simply type:
```{r}
mydata <- merge(results, demographic1 by=c("area_code"))
mydata <- merge(mydata, demographic2 by=c("area_code"))
```
You now have a new dataframe `mydata` with the electoral and the demographic information.  Nevertheless we need to further clean the database.  

First, we are going to delete the variables that we don't need.  To do this we just type the name of our dataframe followed by $ and the variable we want to delete, like this: `mydata$variable <- NULL`.

```{r}
##Let's list all the variables first
names(mydata)

##Delete the variables we don't need
mydata$new_id.x <- NULL
mydata$area_name.x <- NULL
mydata$new_id.y <- NULL
mydata$area_name.y <- NULL
```
To analyze the data we also need the percentage of Remain, Leave and Rejected votes for each area.  We are going to create those three variables:
```{r}
mydata$perc_remain <- (mydata$Remain / mydata$Valid_Votes)*100
mydata$perc_leave <- (mydata$Leave / mydata$Valid_Votes)*100
mydata$perc_rejected <- (mydata$Rejected_Ballots / mydata$Votes_Cast)*100
```
Also we want to sum `prof_ocu_1` and `prof_ocu_2` to create a new variable that contains the percentage of residents in each area with professional occupations:
```{r}
mydata$prof_ocu <- mydata$prof_ocu_1 + mydata$prof_ocu_2
```
We can also create a new categorical variable `Result` that shows which areas voted to leave and which voted to remain.  to do this we are going to use the `ifelse()` function:
```{r} 
##This fuction creates a new variable that asigns the value 1 if the remain percentage is less than 50, 
and 0 otherwise

mydata$result <- ifelse(mydata$perc_remain<50, 1, 0)
```
Now we can add labels to the variable `Result`
```{r} 
mydata$result <- factor(mydata$result,
                    levels = c(1,0),
                    labels = c("leave", "remain"))
```

We can also create a new categorical variable that allows to group the Remain vote in different categories:

```{r} 
mydata$Remain_cat[mydata$perc_remain<25]<- 1
mydata$Remain_cat[mydata$perc_remain>=25 & mydata$perc_remain<50]<- 2
mydata$Remain_cat[mydata$perc_remain>=50 & mydata$perc_remain<75]<- 3
mydata$Remain_cat[mydata$perc_remain>=75]<- 4
```
Now we can add labels to the variable `Remain_cat`
```{r} 
mydata$Remain_cat <- factor(mydata$Remain_cat,
                    levels = c(1,2, 3, 4),
                    labels = c("very low", "low", "high", "very high"))
```

We are almost done, don't give up just yet!  Now to finish we want to aggregate regional data in new varaibles, in order the see the voting results by region.  

```{r} 
HELP Heidi: What I want to do is to generate new variables that sums all the observations 
of a variable by region in Stata the command would be for example: 
egen newvar = total(Valid_Votes), by(Region_Code), 
this would generate a new variable that has all the Valid votes for each region.
The new variables would be:
valid_region  Valid votes by region
leave_region  leave votes by region
remain_region remain votes by region

##Calculate the percentages
mydata$perc_remain_region <- (mydata$remain_region / mydata$valid_region)*100
mydata$perc_leave_region <- (mydata$leave_region/ mydata$valid_region)*100
```
_Heidi: Do you think we can do somehing else here in cleaning, to introduce a package, maybe filter data?_

Now that you have cleaned your data, you're ready to start the analysis! 

**Are you convinced yet that R is worth your time?**     
____ not really    
____ hmmm, I need to see more to decide     
____ yes, R won my heart  

**Let's list some advantages of R so far:** 
* With simple lines of code you can rearrange your data, create new variables, delete observations
* Something went wrong? Don't worry, just fix your code, run it and the error goes away easily
* You can keep your original datafiles in the workspace if you need to review them.  

> **Let's review what we learned in this step:**
>
- Merge datasets `merge()` 
- Create new variables
- Delete variables
- Create new categorical variables and asign labels


## Analyze
Let's start with the fun part.  You need to write a story based on those electoral results, and you already have some questions 
you want to answer:
- Which areas voted to remain or to leave?
- Which regions? 
- Which were the more divided regions?
- How does some demographic variables correlate with the leave and remain percentage of votes?

First we need to tabulate the data:
```{r}
##How many areas voted to Remain or leave
table(mydata$result)
prop.table((table(mydata$result)))
   leave    remain 
0.6902887 0.3097113 
```
You can see that 69% of the areas voted to leave the European Union.  Now let's see how are they are distributed by Region creating a two frequency table that shows row percentages.  To do that we are going to use the `CrossTab()` function in the `gmodels` package:
```{r}
install.packages("gmodels")
library("gmodels") 
CrossTable(mydata$Region, mydata$result, digits=3, max.width = 5, expected=FALSE, 
prop.r=TRUE, prop.c=FALSE, prop.t=FALSE, prop.chisq=FALSE)

##See that we set the prop.r = TRUE in order to show row percetages.  If we wanted for instance to show column percentages
we can set prop.c=TRUE 
Total Observations in Table:  381 
                         | mydata$result 
           mydata$Region |     leave |    remain | Row Total | 
-------------------------|-----------|-----------|-----------|
                    East |        42 |         5 |        47 | 
                         |     0.894 |     0.106 |     0.123 | 
-------------------------|-----------|-----------|-----------|
           East Midlands |        38 |         2 |        40 | 
                         |     0.950 |     0.050 |     0.105 | 
-------------------------|-----------|-----------|-----------|
                  London |         5 |        28 |        33 | 
                         |     0.152 |     0.848 |     0.087 | 
-------------------------|-----------|-----------|-----------|
              North East |        11 |         1 |        12 | 
                         |     0.917 |     0.083 |     0.031 | 
-------------------------|-----------|-----------|-----------|
              North West |        32 |         7 |        39 | 
                         |     0.821 |     0.179 |     0.102 | 
-------------------------|-----------|-----------|-----------|
        Northern Ireland |         0 |         1 |         1 | 
                         |     0.000 |     1.000 |     0.003 | 
-------------------------|-----------|-----------|-----------|
                Scotland |         0 |        32 |        32 | 
                         |     0.000 |     1.000 |     0.084 | 
-------------------------|-----------|-----------|-----------|
              South East |        43 |        24 |        67 | 
                         |     0.642 |     0.358 |     0.176 | 
-------------------------|-----------|-----------|-----------|
              South West |        28 |         9 |        37 | 
                         |     0.757 |     0.243 |     0.097 | 
-------------------------|-----------|-----------|-----------|
                   Wales |        17 |         5 |        22 | 
                         |     0.773 |     0.227 |     0.058 | 
-------------------------|-----------|-----------|-----------|
           West Midlands |        29 |         1 |        30 | 
                         |     0.967 |     0.033 |     0.079 | 
-------------------------|-----------|-----------|-----------|
Yorkshire and The Humber |        18 |         3 |        21 | 
                         |     0.857 |     0.143 |     0.055 | 
-------------------------|-----------|-----------|-----------|
            Column Total |       263 |       118 |       381 | 
-------------------------|-----------|-----------|-----------|
```
With that table you can see that the only regions in wich the majority of areas voted to remain in the EU are located in London, Scotland
and Northern Ireland.  This could be interesting for your story!

We can also calculate some summary statistics for the `perc_remain` variable:
```{r}
summary(mydata$perc_remain)
table(mydata$Remain_cat)
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
  24.44   39.65   45.73   46.88   52.85   78.62 
  
  very low       low      high very high 
        1       262       112         6 
```
You can see that only one area had a very low vote to Remain with 24.4% of the vote.

We can also tabulate the 10 areas with the highest Leave vote:
```{r}
CODE
```
So far you have answered some of your questions: the majority of areas in the UK voted to leave the EU.  London, Scotland and Northern Ireland voted by majority to Remain.  

So it's time to go deeper in the analysis.  We can calculate some correlations between the leave vote and some of the demographic variables.  The hyphotesis is that the regions with older population, less educated residents and less diverse voted to Leave the EU.  

Now let's calculate some correlations.  To calculate a correlation between two variables just use the fuction `cor()` and plot it using `plot(x, y)`:
```{r}
cor(mydata$perc_leave, mydata$no_educ)
plot(mydata$perc_leave, mydata$no_educ)
```
To see if our correlation is statistically significant we can use the `rcorr()` function in the `Hmsc` package, that shows the pvalue:
```{r}
install.packages("Hmsc")
library("Hmsc")
rcorr(mydata$perc_leave, mydata$no_educ)
```
To calculate a correlation matrix, let's create a new dataframe only with the varaibles we need and then use the `cor()` function again:
```{r}
datacor <- data.frame(mydata$perc_leave, mydata$perc_remain, mydata$median_age, mydata$born_uk, 
mydata$no_educ, mydata$higher_educ, mydata$prof_ocu)
cor(datacor)
                   mydata.perc_leave mydata.perc_remain mydata.median_age mydata.born_uk mydata.no_educ mydata.higher_educ mydata.prof_ocu
mydata.perc_leave          1.0000000         -1.0000000         0.3344219      0.4781973      0.5563877         -0.7708179      -0.5849986
mydata.perc_remain        -1.0000000          1.0000000        -0.3344219     -0.4781973     -0.5563877          0.7708179       0.5849986
mydata.median_age          0.3344219         -0.3344219         1.0000000      0.7368753      0.1892295         -0.2176862      -0.1497925
mydata.born_uk             0.4781973         -0.4781973         0.7368753      1.0000000      0.4524213         -0.5447494      -0.4035716
mydata.no_educ             0.5563877         -0.5563877         0.1892295      0.4524213      1.0000000         -0.8812980      -0.9095549
mydata.higher_educ        -0.7708179          0.7708179        -0.2176862     -0.5447494     -0.8812980          1.0000000       0.8868166
mydata.prof_ocu           -0.5849986          0.5849986        -0.1497925     -0.4035716     -0.9095549          0.8868166       1.0000000
```
You can see that there's a high negative correlation between the leave vote and the areas with a high number of residents with higher education and professional occupations.  

But wait, we can understand better the data if we plot a correlation matrix. To do this..... 



...



## Visualize

...

##

...

...

This was the last step! Are you convinced yet? If not, check out [other scenarios]() or [send us an angry tweet]()

## Introductory steps - Recipes

