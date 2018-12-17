---
layout: post
title: R Highlights
---

Generally, R is not as popular as Python. But in statistic computing world, R is the most commonly used programming language.  

### Data Types and Data Structures
The three most common data structures in R are vector, list and data frame.

**Vectors**   
A vector contains only one type of data, such as *logical*, *integer*, *real*, *complex*, *string* (or *character*) and *raw*. The type of the data in a vector is usually called the `mode` of the vector.  Example:
```
a <- c(10, 20, 25, 30)     # a numeric vector
a[2]          # get the second element of the vector
a[2:4]        # get the second to fourth elements of the vector
```
*Note: subsetting a vector returns a vector*

**Lists**  
A list can contain different types of data. We use [[]] to identify elements of a list. Example:
```
mylist <- list(first_name = 'Gilbert', last_name = 'Lei', Grade = 95)  
mylist[[2]]         # get the value of the second component
mylist[['Grade']]   # get the value of the component named 'Grade'
mylist[2]           # get the 2nd component of the list as a new list
str(mylist)         # get the structure of mylist

poll <- list(numbers=c(3,1,2))
poll$numbers[c(3,1)]  # result is a vector c(2, 3)
poll[["numbers"]][c(3,1)]  # result is a vector c(2, 3)
poll['numbers']       # this is the same as poll
poll['numbers'][['numbers']]  # get the value of the component named 'numbers'
poll[1][['numbers']]    # get the value of the first component

```


**Matrices**  
Matrices can only have two dimensions. All columns in a matrix must have the same mode(numeric, character, etc.) and the same length. Example:
```
cells <- c(20, 10, 30, 80, 66, 77, 99, 25)  
rnames <- c('R1', 'R2')
cnames <- c('C1', 'C2', 'C3', 'C4')
mymatrix <- matrix(cells, nrows=4, ncol=2, byrow=TRUE, dimnames=list(rnames, cnames))  

mymatrix[, 2]    # retrieve the 2nd column of the matrix  
mymatrix[3, ]    # retrieve the 3rd row of the matrix  
```


**Arrays**  
Arrays are similar to matrices but can have more than two dimensions.  

**Data Frame**
A data frame is more general than a matrix in that different columns can have different modes (numeric, character, factor, etc.). Example:
```
a <- c(1, 2, 3)
b <- c('United States', 'Canada', 'Mexico')
c <- c(FALSE, TRUE, TRUE)
mydf <- data.frame(a, b, c)  
names(mydf) <- c('ID', 'Country', 'Passed')  # define variable names

mydf$ID       # get all values in column 'ID'
mydf$ID[[2]]  # get the second elment in colun 'ID'  
mydf['ID']    # get the column 'ID' as a list  
mydf[1]       # get the first column as a list  
mydf[c('ID', 'Country')]    # get the columns 'ID' and 'Country' as lists
```


**How to check the object type?**  
- class(object)          # what kind of object is it (high level)
- typeof(object)         # what is the object's data type (low level)
- is.numeric(object)

**We can coerce object to take on a different form:**
- as.numeric("5.6") ** 2


### Operators
R has below arithmetic operators:  
- \+
- \-
- \*
- /
- %/%      # 整除, 82 %/% 10 = 8
- %%      # 取余，82 %% 10 = 2
- floor() # 向下取整，floor(8.9) = 8
- ceiling() # 向上取整，ceiling(8.9) = 9
- round()    # 四舍五入取整，round(8.6) = 9  
- **      # 幂/次方
- ^       # 幂/次方


R has below comparison operators:  
- x == y  
- x != y  
- x > y  
- x >= y  
- x < y  
- x <= y  


### Vectorization
a <- c(2, 4, 8, 10)
a <- a*2
a <- a * (1:n)   # the ith element will multiply by i
a > 0     # result is c(TRUE, TRUE, TRUE, TRUE)  
a[1:n] <- 1:2   # result is c(1, 2, 1, 2)


### Control Flow
The most common types of control flow:
- if-elif-else
- while
- for


### Environments

```
# show the global environment object
globalenv()       

# list all variables and functions in current environment
ls()

# return a list of all bindings of a package
ls(“package:package_name”)

# find where a name is defined, returns the environment in which it is located
where(name, env = parent.frame())

# Return the current environment (execution environment)
environment()	    

# Return the parent environment of an environment
parent.env(environment())	  

# Return the list of all environment in search path
search()	       

# ??????
with()

# Attach an object to the search path, so that you can directly call the properties of this object
attach(name)

```


### Unit Tests
test_that
