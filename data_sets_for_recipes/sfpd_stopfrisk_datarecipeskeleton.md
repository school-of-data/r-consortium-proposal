# Stop, Question, and Frisk data for the NYPD from 2003 - 2016
## Data recipe skeleton

This link contains various zipped CSV's of data records from the New York Police Department Stop, Question, and Frisk database. Each year is in its own zip file.
- http://www1.nyc.gov/site/nypd/stats/reports-analysis/stopfrisk.page
- Just 1 year can be used, or multiple years can be downloaded and joined to look at trends across years.
- `sqf-2016.csv` is also in this folder, in case the website goes down or changes URL.

The 2016 CSV is a quick download, and unzipped it's a CSV of just under 4 MB. A very manageable size with only ~12,000 rows. I suspect the other ones are small as well.

This website also contains an XLSX file that has the database file specifications. Here you can find what each of the columns in the database dump stand for.

## Ask
So many questions! I have not validated whether or not all of these present some interesting findings, but they're things to look into.
- Under what scenarios do police officers *not* explain a reason for stopping a suspect?
- Are suspects more likely to be frisked or searched if there was a summons?
- Can we predict whether a suspect is likely to be frisked or searched based on their sex? Race? Age? A Combination of these factors?
- Is there a zip code that stops are more likely to happen in?

## Find
- http://www1.nyc.gov/site/nypd/stats/reports-analysis/stopfrisk.page

## Get
- Download and unzip file. Only one CSV.
`sqf_data_raw <- read.csv('sqf-2016.csv',header=T,na.strings=c(""))`
- Will probably do the trick. These files have headers and empty fields

## Verify
- Show the names of the columns
- Trim columns that we might not need, like any column with location data that isn't a zipcode, or all of the "reason for stop"/"reason for frisk" etc. columns
- Summary to briefly review suspect information (age, sex, height, etc)
- Columns with too many empties? `sapply(sqf_data_raw,function(x) sum(is.na(x)))`

## Clean
- ??

## Analyze
- Linear, logistic, or poisson regressions!!
- http://www.statmethods.net/advstats/glm.html
- If that's too advanced,
  - Graphing something like suspect gender x frisk or no frisk
  - Histogram of the zipcodes where stops happen in

## Present
- Linear/logistic regressions can show scatterplots w/ lines of best fit over.
- Histograms can have prettified axes etc.
