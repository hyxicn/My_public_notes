# Loops in Stata

Outline

* `local` and `macro`
* foreach
* forvalue
* while

### `local` and `macro` variable
  
  We need to use a very special quote if we want to quote a `local` in stata: `'
  
  * Two different ways to define a local
  
    ``` js
    local one 3+2 // string
    local one = 3+2 // number
    ```
  * ++[--] operators
    
    We can use `local --i` for `local i = 'i' -1`. We can use  `local ++1` for `local i = 'i' + 1`.
  
  * local can make regression shorter
  
  ```js
  local controlVars age sex occupation location maritalStatus hasChildren \\ put all control variables together
  reg income education `controlVars'
  logit employed education `controlVars'
  
  ```
    


### `foreach` loops
  
  `foreach` is more general (not only for values) than `forvalue`
  
  * Variable substitution
  
    ```js
    //Exercise 3.1
    //Write a loop to replace the value 97 by a missing value "." in variables cooking_fuel, floor_material, type_toilet.
    
    use "Data_BA_assets.dta", clear
    
    foreach var of varlist cooking_fuel floor_material type_toilet {
    replace `var' = . if `var' == 97 
    }
    
    ```
  * `word of` is an extended macro function
  
    ```js
    local direction south west east 

    local description " noon" " evening" " morning"

    local i=1

    foreach dir of local direction {
    local time: word `i' of `description' //冒号用于提取变量标签
    display "The sun is in the `dir' when it is `time' .
    local ++i // local i = `i'+1
    }
    ```

### `forvalue` loops

  faster for values.

  * 分类回归

    ```js
    sysuse auto.dta, clear 
    //使用系统数据集auto
   
    forvalues i = 1(1)5 {
    reg price weight foreign if rep78 == `i'
    est sto m`i'     
    }
    //定义暂元i，引用时需要添加`'进行引用，取值从1到5步长为1；分5类回归；分5类储存结果
    
    esttab m1 m2 m3 m4 m5, nogap r2 label 
    //展示回归结果。调整R方的选项是r2_a
    
    ```
   
  * 循环嵌套
   
    执行顺序：外层循环一次，内层全部循环一次，内层循环全部执行完后再进行外层循环一次
    
    Nested Loops:
    
    * 2 forvalue
    * foreach, forvalues
    
    ```js
    //Example: 2 forvalue
    //You have a panel data with several countries (N =10, country1, country2,..., country10) 
    //and several years(1970-2000).
    //You want to summarize GDP.
    
    forvalue year = 1970(5)2000{
            forvalues = i = 1/10 {
                    sum gdp_country`i'_year`year'
            } //注意这半个括号不要漏
    }
    ```
   
    
    ```js
    //Example: 1*foreach & 1*forvalues
    //If the variable name contains the country name (e.g. gdp_US_1970, gdp_DE_1970
    
    local country US DE FR UK
    
    foreach cname of local country{
            forvalues year = 1970(5)2000 {
                    summarize gdp_`cname'_`year'
            }
    }
    ```

### `while` loops

  * `while` v.s. `foreach` and `forvalues`
    
    Example: print out 1 to 3 using loops
    
    While loops continue until a condition is no longer met.
    
    ```js
    local i 1
    while `i' < 3 {
            display "`i ++ '"
    }
    ```
    
    foreach and forvalues are useful if you have a defined set of values over which to iterate.
    
    ```js
    forval i i = 1/3 {
             display "`i'"
    }
    ```
    
    **Exercise 3.2**
    
    Write 3 loops using forvalues, foreach and while, respectively, that display the number from 1 to 10.
    
    ```js
    forvalues i = 1/10 {
	  display `i'
    }
    
    foreach i of numlist 1/10 {
	  display `i'
    }

    local i = 1
    while `i'  < = 10 {
	  display `i'
    local  ++i
    }
    
    ```
   

### Reference
* [Stata local and macro](https://www.lianxh.cn/news/523000c83ce1f.html)
* [Stata local and macro连享会翻译](https://www.lianxh.cn/news/4d57e771feba7.html)
* [连享会全部推文](https://www.jianguoyun.com/p/DXgO9zoQtKiFCBj6tPED)
