# allotalot

Parallel assignment in R

[travis]: https://travis-ci.org/nteetor/allotalot.svg?branch=master "lots o' building"
[appveyor]: https://ci.appveyor.com/api/projects/status/github/nteetor/allotalot?branch=master&svg=true "lots o' 'veyors"
[coverage]: https://codecov.io/gh/nteetor/allotalot/branch/master/graph/badge.svg "lots o' coverage"
[cran]: https://www.r-pkg.org/badges/version/allotalot "getting there"

![alt text][travis] ![alt text][appveyor] ![alt text][coverage] ![alt text][cran]

## Getting Started

A first example,

```R
library(allotalot)

a: b %<-% c(0, 1)
a
#> 0
b
#> 1

{c: d} %<-% list('first', 'second')
c
#> "first"
d
#> "second"
```

A few interesting or more demonstrative examples,

```R
# assign more than 2 values
{one: two: three: four} %<-% list(1, 2, 3, 4)
one 
#> 1
two
#> 2
three
#> 3
four
#> 4

# combine extra values
{one: ...rest} %<-% list(1, 2, 3, 4)
one
#> 1
rest
#> list(2, 3, 4)

# use nested braces
{a: {c: d}: b} %<-% list('hello', list('goodnight', 'moon'), 'world')
a
#> "hello"
b
#> "world"
c
#> "goodnight"
d
#> "moon"

# unpack the dimensions of an object
nrows: ncols %<-% dim(mtcars)
nrows
#> 32
ncols
#> 11

# swap values without using a temporary variable
{nrows: ncols} %<-% list(ncols, nrows)
nrows
#> 11
ncols
#> 32
```

## Installation

allotalot can be installed using devtools:
```R
# install.packages('devtools')
devtools::install_github('nteetor/allotalot')
```

## Vignette

For more about how to use *allotalot* checkout the [introductory vignette](vignettes/intro-to-allotalot.Rmd).

---

Inspiration for this package goes to Paul Teetor. Without his encouragement nothing would have gotten off the ground. Enjoy alloting a lot of values!
