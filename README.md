# SNAP Participation and Structural Cost Burdens Across U.S. Counties

This repository contains the dataset, R script, analytical report, and presentation slides for the *IA650: Data Mining* project conducted as part of the Master of Science in Applied Data Science program at Clarkson University.  
The project investigates how **SNAP (Supplemental Nutrition Assistance Program)** participation correlates with **county-level cost-of-living structures** across the United States, using statistical and unsupervised learning methods.

---

## 1. Project Overview

The primary research question guiding this analysis is whether SNAP participation rates reflect or reshape local cost-of-living structures.  
The study uses county-level data incorporating SNAP participation rates, median income, metro status, and disaggregated cost shares for categories such as housing, childcare, transportation, food, and healthcare.

By applying dimensionality reduction and clustering methods, the project identifies latent structures in county cost patterns and evaluates how these structures relate to SNAP participation intensity.

---

## 2. Repository Structure

SNAP/
│
├── data/
│   └── data.csv
│
├── code/
│   └── food_final.Rmd
│
├── reports/
│   ├── SNAP_analysis_on_costs.pdf
│   └── Group_7_Mutsa_Mungoshi_Presentation.pdf
│
├── README.md
└── .gitignore      (optional, to exclude unnecessary files)
 
---

## 3. Analytical Workflow

All analysis was conducted in R (version 4.3 or later) using reproducible R Markdown scripting. The workflow includes the following key stages:

### 3.1 Data Preparation
- Imported and cleaned county-level cost, income, and SNAP datasets.
- Merged multiple data sources by county FIPS code.
- Computed cost shares and standardized variables for comparability.
- Handled missing values and applied log-transformations where appropriate.

### 3.2 Dimensionality Reduction
- Applied **Principal Component Analysis (PCA)** to cost-share variables to identify the main underlying dimensions of county cost structures.
- Interpreted PCA loadings to group counties by dominant cost categories (e.g., housing-intensive vs. service-intensive regions).

### 3.3 Regression Modeling
- Conducted multiple linear regression with SNAP participation rate as the dependent variable.
- Used PCA components as predictors to evaluate associations between cost structure composition and SNAP reliance.
- Assessed residual diagnostics, adjusted R², and variance inflation factors (VIFs).

### 3.4 Clustering and Typology
- Implemented **k-means clustering** on PCA-transformed data to classify counties into distinct cost-structure typologies.
- Compared SNAP participation averages across clusters.
- Validated clusters using silhouette scores and within-cluster variance metrics.

### 3.5 Visualization and Interpretation
- Produced biplots, cluster maps, and regression diagnostic plots using `ggplot2` and `factoextra`.
- Interpreted results in the context of socioeconomic cost burdens and regional variation.

---

## 4. Results Summary

- PCA reduced cost-share variability into three dominant components:  
  1. **Housing–Childcare tradeoff**  
  2. **Food–Transportation balance**  
  3. **Healthcare cost differentiation**

- Regression analysis found statistically significant associations between SNAP participation and the first two components, indicating that counties with higher SNAP participation often exhibit higher proportions of essential-cost expenditures.

- Clustering revealed identifiable regional patterns in cost structures, suggesting distinct "cost burden profiles" among urban and rural counties.

---

## 5. Requirements

This project requires R (version 4.3 or higher) and the following R packages:

```r
install.packages(c("tidyverse", "ggplot2", "factoextra", "cluster", "readr", "dplyr"))
