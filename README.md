---
output: github_document
---
<!-- rmarkdown v1 -->

# SWATplusR <img src="man/figures/swatr_hex.svg" align="right" />



[![lifecycle](https://img.shields.io/badge/lifecycle-maturing-blue.svg)](https://www.tidyverse.org/lifecycle/#maturing)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.3373859.svg)](https://doi.org/10.5281/zenodo.3373859)

The `SWATplusR` package provides tools to link existing SWAT2012 and SWAT+ models with your modeling workflows in R. `SWATplusR` enables you to execute SWAT simulations and to control all relevant parameters of a SWAT simulation, such as changes in model parameters, the simulation periods and time steps, or the simulated variables that should be returned to R. The central goal of `SWATplusR` is to return simulation results in a *tidy* format to facilitate an easy implementation of SWAT simulations, together with other R packages into clean and efficient R programming workflows. To efficiently handle large SWAT projects with large numbers of model evaluations and/or large simulation outputs, `SWATplusR` provides parallel computation and incremental saving and selective loading of simulation results into and from SQLite data bases.

## Installation

`SWATplusR` is still under development and will be constantly updated (particularly to keep up with the newest revisions of SWAT+). You can install the current version of `SWATplusR` from the default branch of the package's GitHub repository:


```r
# If you do not have the package devtools installed
install.packages("devtools")

devtools::install_github("chrisschuerz/SWATplusR")
```

The most recent developments of `SWATplusR` are available from the *development* branch of the package's GitHub repository. See the package's [Changelog](https://chrisschuerz.github.io/SWATplusR/news/index.html) for updates available in the development version. You can install the development version of `SWATplusR` available from the *dev* branch as follows:


```r
devtools::install_github("chrisschuerz/SWATplusR", ref = "dev")
```



<!---You can install the released version of SWATplusR from [CRAN](https://CRAN.R-project.org) with:

``` r
install.packages("SWATplusR")
```
--->



## Functionality and workflow

The functionality of `SWATplusR` is reduced to a few essential functions that maintain the link between the SWAT project on the local hard drive and the R environment. With `load_demo()` you can retrieve demo data sets of SWAT projects, calibration data, and shape files of the demo catchment. To keep `SWATplusR` lightweight demo date sets are hosted in the separate package [`SWATdata`](https://github.com/chrisschuerz/SWATdata#swatdata-). With `run_swat2012()` and `run_swat2012()` you can run a SWAT model located in a local project folder and return simulation outputs to R that were defined with `define_output()`. Simulation results can be saved incrementally to an SQLite data base when a `save_file` is defined in `run_swat*()`. With `load_swat_run()` all or selected parts of the simulation results stored in the data base can be loaded back to R. `scan_swat_run()` scans the content of saved simulations and returns meta data on the saved content.



<img src="man/figures/package_workflow.svg" title="plot of chunk workflowfig" alt="plot of chunk workflowfig" width="60%" style="display: block; margin: auto;" />


## Getting started with `SWATplusR`

You can explore the basic functionality of `SWATplusR` in the [Get started](https://chrisschuerz.github.io/SWATplusR/articles/SWATplusR.html#loading-demos) section. There you can learn the following basics:

- Loading demo data [>>](https://chrisschuerz.github.io/SWATplusR/articles/SWATplusR.html#figures)
    * SWAT projects [>>](https://chrisschuerz.github.io/SWATplusR/articles/SWATplusR.htmll#swat-projects)
    * Observation data [>>](https://chrisschuerz.github.io/SWATplusR/articles/SWATplusR.html#observation-data)
    * Spatial catchment data [>>](https://chrisschuerz.github.io/SWATplusR/articles/SWATplusR.html#spatial-data)


- Performing first SWAT model runs from R [>>](https://chrisschuerz.github.io/SWATplusR/articles/SWATplusR.html#first-swat-model-runs)
    * Output definition [>>](https://chrisschuerz.github.io/SWATplusR/articles/SWATplusR.html#output-definition)
    * Exploring the first simulation results [>>](https://chrisschuerz.github.io/SWATplusR/articles/SWATplusR.html#exploring-a-simulation)

- Defining parameter modifications for a SWAT run [>>](https://chrisschuerz.github.io/SWATplusR/articles/SWATplusR.html#model-parameter-alteration)
    * Simulation with a single parameter set [>>](https://chrisschuerz.github.io/SWATplusR/articles/SWATplusR.html#simulation-with-a-single-parameter-set)
    * Simulations with many parameter sets [>>](https://chrisschuerz.github.io/SWATplusR/articles/SWATplusR.html#simulations-with-many-parameter-sets)
    * Exploring the outputs when the parameter were modified [>>](https://chrisschuerz.github.io/SWATplusR/articles/SWATplusR.html#exploring-simulations-with-parameter-alterations)

- Saving and loading SWAT simulations [>>](https://chrisschuerz.github.io/SWATplusR/articles/SWATplusR.html#saving-and-loading-simulations)
- Further input arguments of `SWATplusR` [>>](https://chrisschuerz.github.io/SWATplusR/articles/SWATplusR.html#further-swatplusr-input-arguments)

The [Articles](https://chrisschuerz.github.io/SWATplusR/articles/) section is a collection of tutorials for typical topics on SWAT modeling. Here you can learn how to use `SWATplusR` in combination with other R packages to perform tasks such as:

- Parameter sensitivity analysis [>>](https://chrisschuerz.github.io/SWATplusR/articles/par_sensitivity.html)
- Model parameter optimization [>>](https://chrisschuerz.github.io/SWATplusR/articles/par_optim.html)
- Parameter sampling and model calibration [>>](https://chrisschuerz.github.io/SWATplusR/articles/par_sampl_calib.html)
- Visualization >>

The Articles section will be updated in the future with further topics that can be relevant for any modeling workflow with `SWATplusR`.
