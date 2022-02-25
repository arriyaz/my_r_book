# Dataframe Manipulation


## Sorting

### Sort a vector
Let's create a vector and sort it by `sort()` function.

```R
# Make up a randomly ordered vector
v <- sample(101:110)

# Sort the vector
sort(v)

# Reverse sort
sort(v, decreasing=TRUE)
```


**Code Explanation**: Here,
- `sample()` takes a sample of the specified size from the elements of object using either with or without replacement. For example, in the above code, sample takes value in between 101 to 110, but in random order, without replacement.

- `sort()` fuction order them from smaller to larger

- To order the vector from larger to smaller, we can use decreasing=TRUE option in `sort()` function.


### Sort a DataFrame
Firs, let's create a dataframe

```R
df <- data.frame (id=1:4,
            weight=c(20,27,24,22),
            size=c("small", "large", "medium", "large"))
```
Now to sort the rows of this dataframe we can either use a built in function or `arrange()` function from `plyr` package.

```R
# Sort by weight column. These have the same result.
# Use built-in R functions
df[order(df$weight), ] 

# Use arrange from plyr package
library(plyr)
arrange(df, weight)
```
**Code Explanation**: Here,
- `order()` function can be used inside dataframe. In the above code we rearraged the rows based on the value of weight column.
- In the `arrange()` function first give the name of the dataframe, and then the column name which you want to sort.
 
We can sort more than one column one after another.
```R
# Sort by size, then by weight

df[ order(df$size, df$weight), ]  # Use built-in R functions

arrange(df, size, weight)         # Use arrange from plyr package
```

### Reverse Sort
The overall order of the sort can be reversed with the argument `decreasing=TRUE`.

To reverse the direction of a particular column, the method depends on the data type:

- **Numbers**: put a `-` in front of the variable name, e.g. `df[ order(-df$weight), ]`.
- **Factors**: convert to integer and put a `-` in front of the variable name, e.g. `df[ order(-xtfrm(df$size)), ]`.

- **Characters**: there isn’t a simple way to do this. One method is to convert to a factor first and then sort as above.

```R
# Reverse sort by weight column. These all have the same effect:
arrange(df, -weight)                      # Use arrange from plyr package
df[ order(df$weight, decreasing=TRUE), ]  # Use built-in R functions
df[ order(-df$weight), ]                  # Use built-in R functions
```

```R
# Sort by size (increasing), then by weight (decreasing)
arrange(df, size, -weight)         # Use arrange from plyr package
df[ order(df$size, -df$weight), ]  # Use built-in R functions
```
```R
# Sort by size (decreasing), then by weight (increasing)
# The call to xtfrm() is needed for factors
arrange(df, -xtfrm(size), weight)         # Use arrange from plyr package
df[ order(-xtfrm(df$size), df$weight), ]  # Use built-in R functions
```
Here,

- `xtfrm()` function gives a numeric value for each text element of a vector and produces a numeric vector.




















