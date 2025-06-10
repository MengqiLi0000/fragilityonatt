# fragilityonatt

This repository contains the code and output for the empirical section in the paper *Fragility in Average Treatment Effect on the Treated
under Limited Covariate Support*.
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.15630597.svg)](https://doi.org/10.5281/zenodo.15630597)

## Overview

This analysis demonstrates how estimates of the Average Treatment Effect on the Treated (ATT) vary under different identification-valid designs. Using the LaLonde dataset, we estimate ATT through propensity score matching in three conditions:
- Full sample,
- Support region based on covariate overlap,
- Trimmed sample with estimated propensity score in [0.1, 0.9].

All results reproduce tables and figures reported in Section 4 of the paper.

## Environment and Dependencies

This project is written in R and uses the following core packages:

- `MatchIt`: for propensity score matching,
- `qte`: to access LaLonde and CPS datasets,
- `dplyr`, `tibble`, `ggplot2`: for data wrangling and visualization.

To ensure reproducibility, package versions are locked via [`renv`](https://rstudio.github.io/renv/). We recommend using the included `renv.lock` file to restore the original environment.

### Setup Instructions

To recreate the environment:

```r
install.packages("renv")
renv::restore()
```

Alternatively, install the required packages manually if you prefer not to use `renv`.

## Repository Contents

- `lalonde_analysis.Rmd`: The primary R Notebook reproducing results.
- `renv.lock`: Dependency lockfile capturing exact package versions.
- `figures/`: Contains generated plots used in the manuscript.
## Data

The analysis uses datasets from the `qte` package:

- `lalonde`: Experimental treatment group from NSW.
- `cps1`: Non-experimental comparison group.

No raw data is redistributed. See the original sources below for access and documentation:

- LaLonde, R. (1986). Evaluating the Econometric Evaluations of Training Programs. *American Economic Review*.
- Dehejia, R., & Wahba, S. (1999, 2002). NBER Working Paper No. 6955. [https://users.nber.org/~rdehejia/nswdata2.html](https://users.nber.org/~rdehejia/nswdata2.html)

## Reproducibility

To reproduce results:

1. Clone this repository.
2. Open `lalonde_analysis.Rmd` in RStudio or your preferred IDE.
3. Knit the notebook or run all chunks.

Generated tables and figures will match those reported in the manuscript. ATT estimates are printed at the end of the notebook.

## Citation

If you use or build upon this code, please cite:

> [Mengqi Li]. (2025). *Fragility in Average Treatment Effect on the Treated under Limited Covariate Support*. Working paper.

---

Last updated: June 2025
