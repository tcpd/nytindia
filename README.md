
<!-- README.md is generated from README.Rmd. Please edit that file -->

# nytindia - Prepare and visualize India-tagged data from the NYT Article Search API

<!-- badges: start -->
<!-- badges: end -->

This package includes functions to query the Article Search API of The
New York Times for articles with an India location keyword. It includes
functions to prepare this data to be ready for analysis and
visualization. It includes a shiny app to interact with the output
datasets.

## Installation

The impetus to re-structure what was a data analysis project as a
package was: - to simplify updating the dataset over time - to learn how
to make a package.

Accordingly, this is mostly an internal package, but it can be installed
from GitHub:

``` r
install.packages("devtools")
devtools::install_github("seanangio/nytindia")
```

## Query Data

To query all articles with an India location keyword from the NYT
Article Search API between two dates, run the following in the top level
folder of a new RStudio project.

``` r
library(nytindia)
nyt_get_data(begin_date = "YYY-MM-DD", 
             end_date = "YYY-MM-DD")
```

You’ll need environmental variables called “NYTIMES\_KEY” and
“NYT\_USER\_AGENT”.

Leaving `begin_date` empty will default to 1855 (the earliest available
date). Leaving `end_date` empty will default to the current date.

It queries up to the closest completed month.

## Prepare Data

Once you have your data from the API, there is a pipeline of functions
available to prepare the data.

You’ll still need to render `README.Rmd` regularly, to keep `README.md`
up-to-date. `devtools::build_readme()` is handy for this. You could also
use GitHub Actions to re-render `README.Rmd` every time you push. An
example workflow can be found here:
<https://github.com/r-lib/actions/tree/master/examples>.

You can also embed plots, for example:

<img src="man/figures/README-pressure-1.png" width="100%" />

In that case, don’t forget to commit and push the resulting figure
files, so they display on GitHub and CRAN.
