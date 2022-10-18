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

# Exercise 1.3

Continue with your do-file created in exercise 1.2 using Data_BA1.dta.

1. Check data for inconsist（note: survey was conducted in 2003) in year_birth, child_alive current_age and age_at_death.


2. Correct errors in data.

There are 3 errors in the data set

* Error1: one observation with year of birth 1003, two with 2004

* Error2: children are still alive, but have a positive value of age at death

* Error3: current age and year of birth mismatch in some instances

3. Generate a unique ID for every child (cluster, household and reespondent together uniquely identify an observation).

    A simple approach would be:

```
des cluster household

tostring cluster, gen(sv001)
tostring household, gen(sv002)
tostring respondent, gen(sv003)

gen joint_id = sv001 + sv002 + sv003
```

However, this does not actually create unique IDs and faces potential issues due to the string variables varying in length.
    
A more complete approach to avoid issues for sv002 would be:
    
```
gen str3 sv002 = string(household, "%03.0f")

tostring member, gen(sv004)
replace sv004 = "01" if sv004 == "1"
...
replace sv004 = "09" if sv004 == "9"

gen unique_id = sv001 + sv002 + sv003 + sv004
```

The above method to add zeros with replace is a bit clumsy and can be improved with a loop (we will cover loops in a future lecture).

4. Calculate the mean age in every household.

```
bysort cluster household: egen mean_age_hh = mean(current_age)

```

5. Save data file using: save "filename.dta" [,replace]

```
cd $data
save Data_BA1_cleaned.dta, replace

cd $junk
save Data_BA1_cleaned.dta, replace

```
