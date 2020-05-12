
<!-- README.md is generated from README.Rmd. Please edit that file -->

## Introduction

In this lab, you will continue writing functions to implement simple
linear regression, multiple linear regression, and ridge regression.

Formulas for calculating coefficients of these regressions can be found
in this week’s course materials.

This repository is structured like a package (`regress431`), but you
**do not** have to do any package creation or management tasks. You only
need to edit the body of the functions in the `.R` files to perform the
correct calculations.

If you did not access this file from GitHub Classroom, clone the
repository to your account to begin.

## Guidelines

  - You **should not** alter any of the function names, inputs, or
    outputs that I have provided for you. This is very important - we
    cannot test your work if you change these things\!

  - You **should not** alter the package name, for the same reasons.

  - You **should not** alter the unit tests that are already written,
    for the same reasons. You **may** write more unit tests if this is
    helpful to you, but you are not required to.

  - You **may** (probably should) write helper functions beyond those
    provided. If you do, you do **not** have to carefully document them
    or test them; although you might find this helpful to your coding
    process.

  - You **may** alter the code I provided for you, if you wish, so long
    as the function inputs do not change and outputs (where specified)
    do not change.

  - You **may not** rely on any existing functions designed
    *specifically* for regression; including, but not limited to `lm`,
    `lm.ridge`, and `predict`. Instead, you should do the necessary
    matrix calculations directly from the data. (You may, however, use
    these functions to check or test the output of the ones you write.)

  - You **may** use the `qr` functions included in this week’s course
    materials.

  - You **must** implement gradient descent yourself from the
    expressions in this week’s course materials.

  - You **may** rely on existing functions and external packages
    designed for *faster general computation*, such as `data.table` or
    `furrr`.  
    If you use an external package, don’t forget to include it in your
    package dependencies by running
    e.g. `usethis::use_package("data.table")`, and to either use the
    `::` in your code or add an `@import` line in the documentation.

## Tasks

### 1\. Simple Linear Regression

In `linear_regression.R`, edit the unfinished section of the
`simple_linear_regression` function to properly compute the slope and
intercept of the regression line.

Load your new code (`Ctrl-Shift-L`) and then run the unit tests
(`Ctrl-Shift-T`) to confirm that your function performs as expected.

### 2\. Multiple Regression

In `linear_regression.R`, edit the body of the
`multiple_linear_regression` function to properly compute all the
required coefficients.

Note that this function assumes that you want to include *every column*
of the supplied data frame in your regression, except the specified
response.

Load your new code and then run the unit tests to confirm that your
function performs as expected.

### 3\. Prediction

In `predict_from_coefs.R`, edit the `predict_from_coefs` function to
calculate predicted values of the response variable.

Note that the input types have been chosen for you, but that the output
format is up to you.

No unit test is written for you for this function, since the output
format is not known. You are not required to write one, but you may find
it useful.

### 4\. Turn it in

By **Friday**, you should have finished Tasks 1-3.

Open the file `Showcase.Rmd` and knit it. You should see the source code
for all but your `ridge_regression.R` functions.

Upload this html to Canvas. You will receive Peer Review feedback.

When you are finished, make sure all your changes are pushed to GitHub.
Then, submit the link to your repository on Canvas.

## Challenge

This week, there is no additional Challenge. Instead, your code will be
tested for speed.

I will be loading your finished packages, and running something like the
following:

``` r
library(regress431)

tic()

  simple_linear_regression(mtcars, mpg, cyl)

toc()

  multiple_linear_regression(mtcars, mpg)
  
toc()
```

However I will run this code on different datasets than this example, of
varying sizes.

Bonus Points will be given for:

  - **+5** for fastest `simple_linear_regression`

  - **+5** for fastest `multiple_linear_regression`

  - **+10** for top 3 in overall total speed

  - **+5** for top 4-10 in overall total speed
