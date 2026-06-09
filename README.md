# CAHOOTS Analysis
## EPD's Shifting Burden After CAHOOTS Stopped Services in Eugene

### Overview
This project analyzes how call volumes and proportions changed for the 
Eugene Police Department (EPD) after CAHOOTS stopped 
services in April 2025, using Springfield as a
control through multiple different forms of analysis.

### Dependencies
R packages required:
- tidyverse (includes dplyr, ggplot2, tidyr, stringr, lubridate, purrr, readr)
- readxl
- scales

Install with:
install.packages(c("tidyverse", "readxl", "scales"))

### Data
Place the following files in the working directory:
- Eugene_CAD_data_noloc/ (folder containing yearly CSV files)
- 2015-2025 SPD Calls for Service.xlsx
- MCSLC.xlsx

All scripts should be ran in an R Markdown file for best results.
Make sure the R Markdown file is saved in the same folder as the 
data files.

Data was provided by Dr. Rohlfs through the DSiA course at the 
University of Oregon, originally sourced from EPD, SPD, and MCSLC.

### Scripts 

Run in this order:

1. **Cleaning.Rmd** — Loads and merges all three datasets, removes 
   duplicates, handles missing values, converts datetime variables, 
   labels agencies, adds period and year-month columns, aggregates 
   monthly call counts, and calculates within-city proportions. 
   Saves four .rds files used by the analysis script.

2. **Analysis.Rmd** — Loads the cleaned data and performs all 
   analytical steps: descriptive time-series visualization, 
   difference-in-differences estimation, parallel trends testing,
   EPD volume stability analysis, call-type absorption analysis
   with per-type DiD and t-tests, and call-type decrease comparisons
   between Eugene and Springfield.

### Key Dates
- April 8, 2025: CAHOOTS stops services in Eugene (treatment date)
- January 2023: Excluded due to CAHOOTS labor action
- April 2025: Excluded as a partial month
- Matched window: April–December 2024 vs. May–December 2025

### Author
Alex Gollier — DSCI 410, University of Oregon
