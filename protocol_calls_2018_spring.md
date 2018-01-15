# 15.01.2018

### Who takes responsibility of what? 
- Heidi will still be involved (keep maintaining the technical documentation) but cannot be doing all the organisation any longer.
- General coordination (organising calls, writing reports, clarifying timeline, ...): ScoDa can handle this, someone might be recruited (probably end of January). 

### How to finish the recipes and skills lessons?
- Stick to the naming guidelines for [recipes](https://github.com/school-of-data/r-consortium-proposal/blob/master/r-package/inst/tutorials/en-recipe-template/en-recipe-template.Rmd#naming-conventions) and [skills lessons](https://github.com/school-of-data/r-consortium-proposal/blob/master/r-package/inst/tutorials/en-skills-template/en-skills-template.Rmd#naming-conventions). 
- Please use no capital letters, no spaces and no special characters in names of files.
- Add RData-version of all raw data [here](https://github.com/school-of-data/r-consortium-proposal/tree/master/r-package/data). For learnr to work without problems, we need this. Also we only "pretend" to load the actual data in whatever format it is, but really only load the RData files (this makes everything MUCH faster). For an example check the [intro](https://github.com/school-of-data/r-consortium-proposal/blob/master/r-package/inst/tutorials/en-introduction/en-introduction.Rmd). You can also ask Peter or Heidi for help.
    
### How do we organize the testing phase?
- Testing will first focus on individual recipes.
- The [info for contributors](https://github.com/school-of-data/r-consortium-proposal/blob/master/CONTRIBUTING.md#beta-testing) explains what to do as a tester.
- The [issue templates](https://github.com/school-of-data/r-consortium-proposal/issues/new) help with getting the feedback in an ordered way. To change the template, edit [this document](https://github.com/school-of-data/r-consortium-proposal/blob/master/ISSUE_TEMPLATE.md).
:::info 
💡 [shinyapps.io](https://www.shinyapps.io) should easily host learnr tutorials. 
More info: https://rstudio.github.io/learnr/publishing.html#shiny_server
:::

- TODO: update the info for contributors so that people understand what types of people we are looking for.
  - Basic R users (who can already run a bit of R code).
  - People who have R + RStudio installed.
  - We can get feedback from beginners later when we have it on a website.
  - Note: we have different languages, say which tutorial is in which language.
- TODO: update the issue template with the question "what is your R skills level so far"?
- TODO schedule call for "*How to get learnr tutorial to work in the R package*" with Camila and Gibran.



