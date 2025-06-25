---
title: "pandas (R)osetta: Tidyverse R"
subtitle: "Intro to R and Tidyverse for Pandas users and vice versa."
author: "Lisa Malins"
knit: (function(inputFile, encoding) {
    rmarkdown::render(
      inputFile,
      encoding = encoding,
      output_dir = "output",
      output_format = "all")
    })
output:
  html_document:
    toc: true
    df_print: paged
    keep_md: TRUE
  pdf_document:
    toc: true
    toc_depth: 4
    df_print: "tibble"
---

&nbsp;

This is a demonstration of basic data wrangling operations in Tidyverse R.

Sister notebooks demonstrate the exact same operations in base R and the Pandas library in Python, just like the Rosetta Stone.

## I/O
### Create dataframe from scratch

``` r
suppressPackageStartupMessages(library("dplyr"))
tbl <- tibble(
  letter = c("a", "b", "c", "d", "e"),
  number = c(1:5),
  fruit = c("apple", "banana", "coconut", "date", "elderberry"),
  vegetable = c("arugula", "beet", "carrot", "daikon", "eggplant"),
  name = c("Alice", "Bob", "Carol", "Dan", "Eve")
)
tbl
```

<div data-pagedtable="false">
  <script data-pagedtable-source type="application/json">
{"columns":[{"label":["letter"],"name":[1],"type":["chr"],"align":["left"]},{"label":["number"],"name":[2],"type":["int"],"align":["right"]},{"label":["fruit"],"name":[3],"type":["chr"],"align":["left"]},{"label":["vegetable"],"name":[4],"type":["chr"],"align":["left"]},{"label":["name"],"name":[5],"type":["chr"],"align":["left"]}],"data":[{"1":"a","2":"1","3":"apple","4":"arugula","5":"Alice"},{"1":"b","2":"2","3":"banana","4":"beet","5":"Bob"},{"1":"c","2":"3","3":"coconut","4":"carrot","5":"Carol"},{"1":"d","2":"4","3":"date","4":"daikon","5":"Dan"},{"1":"e","2":"5","3":"elderberry","4":"eggplant","5":"Eve"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>
</div>

### Write

``` r
library("readr")
write_csv(tbl, "data/tidy_letters.csv")
write_tsv(tbl, "data/tidy_letters.tsv")
```

### Read

``` r
library("readr")
read_csv("data/tidy_letters.csv")
```

```
## Rows: 5 Columns: 5
## ── Column specification ────────────────────────────────────────────────────────
## Delimiter: ","
## chr (4): letter, fruit, vegetable, name
## dbl (1): number
## 
## ℹ Use `spec()` to retrieve the full column specification for this data.
## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
```

<div data-pagedtable="false">
  <script data-pagedtable-source type="application/json">
{"columns":[{"label":["letter"],"name":[1],"type":["chr"],"align":["left"]},{"label":["number"],"name":[2],"type":["dbl"],"align":["right"]},{"label":["fruit"],"name":[3],"type":["chr"],"align":["left"]},{"label":["vegetable"],"name":[4],"type":["chr"],"align":["left"]},{"label":["name"],"name":[5],"type":["chr"],"align":["left"]}],"data":[{"1":"a","2":"1","3":"apple","4":"arugula","5":"Alice"},{"1":"b","2":"2","3":"banana","4":"beet","5":"Bob"},{"1":"c","2":"3","3":"coconut","4":"carrot","5":"Carol"},{"1":"d","2":"4","3":"date","4":"daikon","5":"Dan"},{"1":"e","2":"5","3":"elderberry","4":"eggplant","5":"Eve"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>
</div>

``` r
read_tsv("data/tidy_letters.tsv")
```

```
## Rows: 5 Columns: 5
## ── Column specification ────────────────────────────────────────────────────────
## Delimiter: "\t"
## chr (4): letter, fruit, vegetable, name
## dbl (1): number
## 
## ℹ Use `spec()` to retrieve the full column specification for this data.
## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
```

<div data-pagedtable="false">
  <script data-pagedtable-source type="application/json">
{"columns":[{"label":["letter"],"name":[1],"type":["chr"],"align":["left"]},{"label":["number"],"name":[2],"type":["dbl"],"align":["right"]},{"label":["fruit"],"name":[3],"type":["chr"],"align":["left"]},{"label":["vegetable"],"name":[4],"type":["chr"],"align":["left"]},{"label":["name"],"name":[5],"type":["chr"],"align":["left"]}],"data":[{"1":"a","2":"1","3":"apple","4":"arugula","5":"Alice"},{"1":"b","2":"2","3":"banana","4":"beet","5":"Bob"},{"1":"c","2":"3","3":"coconut","4":"carrot","5":"Carol"},{"1":"d","2":"4","3":"date","4":"daikon","5":"Dan"},{"1":"e","2":"5","3":"elderberry","4":"eggplant","5":"Eve"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[10],"max":[10]},"pages":{}}}
  </script>
</div>
