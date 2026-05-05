# CAHOOTS Analysis

## Overview
This project analyzes how call volumes and proportions changed when CAHOOTS 
stopped services in Eugene in April 2025, using Springfield as a control city.

## Dependencies
The following R packages are required:
- tidyverse
- ggplot2
- readxl
- lubridate

Install all packages with:
install.packages(c("tidyverse", "ggplot2", "readxl", "lubridate"))

## Data
Place the following files in the same directory as the scripts:
- Eugene_CAD_data_noloc/ (folder containing 11 yearly CSV files)
- 2015-2025 SPD Calls for Service.xlsx
- MCSLC.xlsx

Data was provided via the DSiA course at the University of Oregon and is not 
publicly available.

## Scripts
Run in this order:

1. cleaning.Rmd — loads and merges all three datasets, removes duplicates, 
   handles missing values, converts datetime variables, labels agencies, 
   adds period and year_month columns, and selects relevant columns.

2. analysis.Rmd — performs monthly aggregation, proportion calculation, 
   time series visualizations, and before/after bar charts comparing 
   call volumes and proportions across agencies before and after 
   April 8, 2025.

## Notes
- cleaning.Rmd must be run before analysis.Rmd
- April 8, 2025 is used as the cutoff date for the before/after period 
  variable, as this was the date CAHOOTS stopped services in Eugene
