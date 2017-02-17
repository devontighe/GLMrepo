
<!-- README.md is generated from README.Rmd. Please edit that file -->
[![Build Status](https://travis-ci.org/stephlocke/ReproducibleGLM-step1.svg?branch=master)](https://travis-ci.org/stephlocke/ReproducibleGLM-step1)

This is a project configured to allow us to start building reproducible models and associated documentation. This stage in the project contains everything up to sampling.

Bits and pieces in use in this project:

-   Packrat
-   Git
-   Travis-CI
-   Makefile

Lets use Titanic data!

-   Install PASWR package from CRAN
-   Install RSQLite package from CRAN
-   Make a titanic db in `data-raw`

``` r
library(DBI)
library(RSQLite)
titanicdb<-dbConnect(SQLite(),dbname="data-raw/titanic.sqlite")
```

-   Add titanic data to the db

``` r
library(PASWR)
dbWriteTable(titanicdb, "titanic", titanic3, overwrite=TRUE)
```

Data steps
----------

-   Get data
-   Clean it
-   Sample it
