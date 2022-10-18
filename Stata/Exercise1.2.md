# Exercise 1.2

1. Download dataset Data_BA1.dta into one of your new folders (generated in exerices 1.1)

2. Start new do-file and open the data-set.

```js
clear all

global mydata "/Users/Sarakael/Downloads/21UZH/Stata/data/S1"

cd "$mydata"
```

3. Assign meaningful variable names and labels, such as:

    v001 cluster 

    v002 household 

    v003 respondent 

    b1 month of birth of the child 

    b4 gender of the child
    
```js
use Data_BA1.dta, clear
rename v001 cluster
rename v002 household
rename v003 respondent
rename b1 month_birth
rename b4 gender_child
label variable month_birth "month of birth"
lab var gender_child "gender of child"

```

4. Familiarize yourself with the data using descriptive statistics etc.

```js
describe
codebook
summarize
```

5. How many unique value does the variable year_birth have?

```js
levelsof year_birth
```


