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
  





















