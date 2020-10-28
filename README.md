# covidseir <img src='man/figures/covidseir-logo.png' align="right" height="139" />

> Bayesian SEIR Modelling for Multivariate COVID-19 Case Data

<!-- badges: start -->
[![Travis build status](https://travis-ci.org/seananderson/covidseir.svg?branch=master)](https://travis-ci.org/seananderson/covidseir)
[![Lifecycle: experimental](https://img.shields.io/badge/lifecycle-experimental-orange.svg)](https://www.tidyverse.org/lifecycle/#experimental)
<!-- badges: end -->

## Overview

**covidseir** fits a Bayesian SEIR (Susceptible, Exposed, Infectious, Recovered)
model to daily COVID-19 case data. The package focuses on estimating the
fraction of the usual contact rate for individuals participating in physical
distancing (social distancing). The model is coded in
[**Stan**](https://mc-stan.org/). The model can accommodate multiple types of
case data at once (e.g., reported cases, hospitalizations, ICU admissions) and
accounts for delays between symptom onset and case appearance.

The model is a continuation of the model described in the preprints:

Anderson, S. C., Edwards, A. M., Yerlanov, M., Mulberry, N., Stockdale, J., Iyaniwura, S. A., Falcao, R. C., Otterstatter, M. C., Irvine, M. A., Janjua, N. Z., Coombs, D., & Colijn, C. (2020). Estimating the impact of COVID-19 control measures using a Bayesian model of physical distancing. medRxiv, 2020.04.17.20070086. https://doi.org/10.1101/2020.04.17.20070086

Anderson, S. C., Mulberry, N., Edwards, A. M., Stockdale, J. E., Iyaniwura, S. A., Falcao, R. C., Otterstatter, M. C., Janjua, N. Z., Coombs, D., and Colijn, C. (2020). How much leeway is there to relax COVID-19 control measures? medRxiv 2020.06.12.20129833. https://doi.org/10.1101/2020.06.12.20129833

[Illustration for logo by Alissa Eckert, MSMI; Dan Higgins, MAMS](https://phil.cdc.gov/Details.aspx?pid=23311).

*This package is a work in progress: arguments and output format may still change and not all functionality has been tested.*

## Installation

Before installation, you will need a C++ compiler installed to compile the Stan model. If you are on a Mac or Linux, follow [these instructions](https://github.com/stan-dev/rstan/wiki/RStan-Getting-Started). If you are on Windows, follow the 'Configuration' section [here](https://github.com/stan-dev/rstan/wiki/Installing-RStan-from-source-on-Windows) (you do not need to follow the rest of the instructions from that page to install rstan itself from source).

The following must return `TRUE` before continuing:

```r
# install.packages("pkgbuild")
pkgbuild::has_build_tools(debug = TRUE)
```

Then, install the covidseir package with:

```r
# install.packages("remotes")
remotes::install_github("seananderson/covidseir")
```

See the examples in `?fit_seir` and `?project_seir` and the [vignette](https://seananderson.github.io/covidseir/articles/fitting-case-data.html).

To install the package with the vignette:

```r
remotes::install_github("seananderson/covidseir", build_vignettes = TRUE)
```

and run:

```r
browseVignettes("covidseir")
```
