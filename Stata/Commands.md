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

### Dropping Observations or Variables

`drop varlist` Dropping variables (i.e. columnns)

`keep varlist` Keep specified variables, drop remaining

Drop with conditions

`drop if age > 18` Drop all observations with age > 18

`drop if age > 18 & age !=.` Missing values are treated as +∞

### Generating Variables

`generate newvar = exp[if]` [Syntax: generate new variable]

Examples:

`generate lnx = log(x)`

`generate x2 = x^2`

`generate rootx = sqrt(x)`

`generate diff = x2-x1`

* Create new variable of e.g. means in a subset of variable:

`egen newvar = function (varname)`

Example: Generating a variable containing the number of children in a household:

```js
sort cluster household, stable
generate count = 1 if current_age !=.
by cluster household: gen number_child = sum(count)
```

```js
Alternative in 1 step:
bysort cluster household: egen number_child = 
```

Example: Generating a varibale containing the total number of children in a household:

```
egen child_total = rowtotal(birth1 birth2 birth3).
```
Example: Oldest child in the data:

```
egen child_oldest = rowmax(agechild1 agechild2 agechild3)
```





