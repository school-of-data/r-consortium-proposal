We are a group of people excited about data literacy and/or R. We want to teach journalists how to use R for their work.

### Want to help?
Awesome! We need lots of help!
We are very thankful for any contribution. You don't need to be an R specialist or know R at all. 
Come talk to us to find out how you could possibly help :cake: :smiley: :clap:
 
Send an email to heidi@schoolofdata.ch (Heidi is very friendly and will help you figure out how you 
can best contribute to the project) or join our [gitter chat](https://gitter.im/school-of-data/r-consortium-proposal).
 
We currently need help with:
 
 - Creating tutorials (data recipes and skills lessons)
 - Translation (no R knowledge required)
 - Beta testing (no R knowledge required): go through the existing material and point out 
 things you don't understand or points where you get stuck.
 - Planning of the website
 
 ### Creating tutorials
 If you want to add a data recipe or skills lesson, please use the templates to get started:
 
- [data recipes](https://github.com/school-of-data/r-consortium-proposal/tree/master/r-package/inst/tutorials/en-recipe-template)
- [skills lessons](https://github.com/school-of-data/r-consortium-proposal/tree/master/r-package/inst/tutorials/en-skills-template)

You can look at the end-result in R via:
```
devtools::install_github("school-of-data/r-consortium-proposal", 
                         subdir="r-package")
learnr::run_tutorial("en-recipe-template", package = "ddj")
learnr::run_tutorial("en-skills-template", package = "ddj")
```

#### Process of creating a data recipe

1. Find an interesting story for journalists based on a dataset. Note: The dataset should be publicly available data. Datasets containing personal information will not be accepted.
2. Clone to the repo or simply copy the Rmarkdown file
3. Following the data pipeline described in the template, create your recipe with: one section of your recipe = one section of the data pipeline. Note: the recipe should be self-contained: readers should not have to look up external material to complete it.
4. Create a pull request on Github in order for your recipe to be reviewed and added to the list. Alternatively, send an email to heidi [at] schoolofdata [dot] ch

