Outline:

* Data import
* Descriptive Stata
* Loops

### Data import

`sysuse auto.dta, clear` Loading Stata system data

`use mydata.dta, clear` Loading data from current directory

`webuse set "linkofwebpage"` Loading data from the web

`import excel "Nameofspreadsheet.xlsx", sheet("Sheet1")` Importing from excel

`import delimited "Nameofspreadsheet.csv"` Importing from csv

### Descriptive Statistics

`browse` Open data viewer

`describe [varlist]` Display variable type, format, value/variable labels

`codebook [varlist]` Overview of variable type, stats, number of missing/unique values

`list [varlist]` All observations are printed in output window

`summarize [varlist]` Print summary statistics (mean, stdev, min, max) for variables

`tabulate varname` Show frequencies of all unique values (oneway table)

`tabulate varname1 varname2` Show frequencies of all unique values (twoway tables)

`tab1 varname1 varname2` for multiple oneway tables 多个变量，分别画出频次表
 
`isid varname` checks whether the named variable uniquely identifies observations in the data

`display varname[x]` displays the xth observation of variable

`bysort varname:`
