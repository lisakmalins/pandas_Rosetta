pandas (R)osetta: R
================
Lisa Malins

- [I/O](#io)
  - [Create dataframe from scratch](#create-dataframe-from-scratch)
  - [Write](#write)
  - [Read](#read)

 

This is a demonstration of basic data wrangling operations in base R.

Sister notebooks demonstrate the exact same operations in Tidyverse R
and the Pandas library in Python, just like the Rosetta Stone.

## I/O

### Create dataframe from scratch

``` r
df <- data.frame(
  letter = c("a", "b", "c", "d", "e"),
  number = c(1:5),
  fruit = c("apple", "banana", "coconut", "date", "elderberry"),
  vegetable = c("arugula", "beet", "carrot", "daikon", "eggplant"),
  name = c("Alice", "Bob", "Carol", "Dan", "Eve")
)
df
```

    ##   letter number      fruit vegetable  name
    ## 1      a      1      apple   arugula Alice
    ## 2      b      2     banana      beet   Bob
    ## 3      c      3    coconut    carrot Carol
    ## 4      d      4       date    daikon   Dan
    ## 5      e      5 elderberry  eggplant   Eve

### Write

``` r
write.csv(df, "data/R_letters.csv", row.names=FALSE)
write.table(df, "data/R_letters.tsv", sep="\t", row.names=FALSE)
```

### Read

``` r
read.csv("data/R_letters.csv")
```

    ##   letter number      fruit vegetable  name
    ## 1      a      1      apple   arugula Alice
    ## 2      b      2     banana      beet   Bob
    ## 3      c      3    coconut    carrot Carol
    ## 4      d      4       date    daikon   Dan
    ## 5      e      5 elderberry  eggplant   Eve

``` r
read.delim("data/R_letters.tsv")
```

    ##   letter number      fruit vegetable  name
    ## 1      a      1      apple   arugula Alice
    ## 2      b      2     banana      beet   Bob
    ## 3      c      3    coconut    carrot Carol
    ## 4      d      4       date    daikon   Dan
    ## 5      e      5 elderberry  eggplant   Eve
