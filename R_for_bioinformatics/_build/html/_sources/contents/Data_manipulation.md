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
