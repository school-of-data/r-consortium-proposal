# R course for data journalists from the school of data

In this project we want to create an online R course for journalists and data journalists. We focus on people who are used to working with spreadsheets (e.g. excel). The course will be available in the languages Spanish, French, German and English.

We think R is great for journalists all over the world because it is free, open source and helps cleaning data, analysing data and creating beautiful graphs and reports. So far resources for journalists to learn R are very limited and we want to help make R one of journalists' favorite tools :tada:


So far we created...

- The [proposal](https://github.com/school-of-data/r-consortium-proposal/blob/master/proposal.md) 
we wrote for the R Consortium
- Templates for [data recipes](https://github.com/school-of-data/r-consortium-proposal/tree/master/r-package/inst/tutorials/en-recipe-template)
and [skills lessons](https://github.com/school-of-data/r-consortium-proposal/tree/master/r-package/inst/tutorials/en-skills-template). You can also check them out in R via
```
devtools::install_github("school-of-data/r-consortium-proposal", 
                         subdir="r-package")
learnr::run_tutorial("en-recipe-template", package = "ddj")
learnr::run_tutorial("en-skills-template", package = "ddj")
```
- The [intro lesson](https://github.com/school-of-data/r-consortium-proposal/blob/master/material/lessons/Introduction.Rmd)
- A [data journalists view on R](https://github.com/school-of-data/r-consortium-proposal/blob/master/material/lessons/why_use_R.md) by Timo Grossenbacher
- The following data recipes
    + [Switzerland dual use goods](https://github.com/school-of-data/r-consortium-proposal/blob/master/material/lessons/switzerland-dual-use/recipe_switzerland-dual-use.Rmd)
- The following skills lessons 
    + NA
  
 But there is much more work to do and we need help!
 
 
 ### Wanna get involved?
 
We are very thankful for any contributions. You don't need to be an R specialist or know R at all. Come talk to us to find out how you could possibly help :cake: :smiley: :clap:
 
Send an email to heidi@schoolofdata.ch (Heidi is very friendly and will help you figure out how you can best contribute to the project) or join the #r-projects channel on the School of Data slack chat.
 
We currently need help with:
 
 - Creating tutorials (data recipes and skills lessons)
 - Translation (no R knowledge required)
 - Beta testing (no R knowledge required): go through the existing material and point out 
 things you don't understand or points where you get stuck.
 - Planning of the website
