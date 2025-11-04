SNAP Participation and Structural Cost Burdens Across U.S. Counties
Author: Mutsa Mungoshi
Program: M.S. in Applied Data Science, Clarkson University
Course: IA650 – Data Mining
Date: July 31, 2025
Abstract
This study examines whether participation in the Supplemental Nutrition Assistance Program (SNAP) reflects deeper structural affordability burdens at the county level across the United States. Beyond household poverty, SNAP participation is analyzed as a potential indicator of regional cost pressures in housing, childcare, and other essential services.
Using county-level data from over 3,000 U.S. counties, the analysis integrates cost-of-living estimates from the Economic Policy Institute with SNAP participation rates, median income, and metro classifications. Employing Principal Component Analysis (PCA), multivariate regression, and unsupervised clustering, the study identifies consistent associations between SNAP participation and regional cost structures. Results show that SNAP rates are systematically higher in counties with elevated housing and caregiving costs, even after controlling for income and geography.
By positioning SNAP as a diagnostic signal of structural economic burden, the research provides a new perspective for understanding spatial inequality and for designing geographically responsive policy interventions.
Repository Structure
SNAP_PROJECT/
│
├── code/ — R Markdown analysis script
│   └── food_final.Rmd
│
├── data/ — Cleaned dataset (county-level variables)
│   └── snap_data.csv
│
├── reports/ — Final report and presentation
│   ├── SNAP_analysis_on_costs.pdf
│   └── SNAP_Presentation.pdf
│
├── .gitattributes
├── .gitignore
└── README.md
Analytical Framework
All analyses were conducted in R (version 4.3 or later) using a reproducible R Markdown workflow. The methodological sequence followed the structure below:
Data Integration
Merged SNAP participation data with cost-of-living estimates from the Economic Policy Institute and demographic variables from the U.S. Census and USDA.
Variable Construction
Computed standardized cost shares for major expenditure categories, including housing, childcare, transportation, food, healthcare, and taxes.
Dimensionality Reduction (PCA)
Applied Principal Component Analysis to identify latent affordability dimensions and summarize correlated cost structures.
Regression Analysis
Modeled relationships between SNAP participation and principal components, controlling for median income, metro classification, and state-level variation.
Clustering Analysis
Used k-means and hierarchical clustering to identify distinct county-level cost-of-living regimes and compared SNAP participation across them.
Validation and Visualization
Performed statistical validation through ANOVA, chi-square, and silhouette analyses, and visualized results through biplots, scree plots, and geographic maps.
Key Findings
Principal Components
Component	Interpretation	Variance Explained
PC1	General Cost Burden – high across all expenditure categories	56.7%
PC2	Care vs. Housing Tradeoff – childcare and food versus housing and transport	17.1%
PC3	Tax-Centric Residual – variation primarily driven by tax burdens	10.8%
Regression Insights
SNAP participation is significantly associated with PC1 and PC2, confirming strong links between program reliance and essential cost intensity.
The adjusted R² of approximately 0.61 indicates moderate explanatory power.
Variance inflation factors (GVIF) remained below 2.5 for all predictors, confirming minimal multicollinearity.
Clustering Results
The optimal cluster number was determined to be k = 4 using silhouette and gap statistics.
Urban counties exhibited higher housing and childcare costs, while rural clusters emphasized food and transportation burdens.
ANOVA confirmed statistically significant variation in SNAP participation across cluster profiles (p < 0.001).
Visualizations Included in the Report
All visualizations and diagnostics are available in the full report
reports/SNAP_analysis_on_costs.pdf.
Key figures include:
U.S. county-level SNAP participation map
Correlation heatmap of cost-share variables
Q–Q plots and histograms demonstrating data normalization
PCA scree plot and biplot of cost components
Cluster maps showing affordability regimes across counties
Regression residual and influence diagnostics
These visualizations collectively illustrate the analytical pipeline—from preprocessing and PCA to model validation and spatial interpretation.
Reproducibility
To reproduce the analysis locally:
Clone this repository:
git clone https://github.com/mungsmj/SNAP_PROJECT.git
cd SNAP_PROJECT
Open code/food_final.Rmd in RStudio.
Knit the document to generate the full analytical report.
Install the required R packages prior to execution:
install.packages(c(
  "tidyverse", "ggplot2", "factoextra", "cluster",
  "readr", "dplyr", "car", "sandwich"
))
Interpretation and Policy Relevance
Findings suggest that SNAP participation functions as both a household safety net and a regional indicator of affordability stress. Counties with higher housing and caregiving costs exhibit elevated SNAP reliance even after controlling for income.
This reframes SNAP as a spatial diagnostic tool, revealing how structural cost burdens differ across geographic contexts. The framework supports the design of regionally adjusted assistance formulas and policy interventions that account for the true cost of living in high-expense counties.
Conclusion
This project demonstrates that structural cost variation plays a significant role in shaping public assistance demand. By integrating economic, geographic, and social indicators within a unified analytical framework, the study reveals that SNAP participation mirrors underlying affordability regimes rather than acting solely as a response to poverty.
The combined use of PCA, regression modeling, and clustering provides a multidimensional view of cost structure disparities, while statistical validation confirms that these patterns are systematic and spatially anchored.
The results highlight the importance of viewing SNAP and similar programs through a regional cost lens, where affordability pressures—not just income levels—define vulnerability. In policy terms, these findings point toward regionally differentiated program design, adaptive benefit scaling, and improved integration of cost-of-living metrics into social welfare planning.
Ultimately, the analysis positions SNAP as both a measure of household need and a window into the broader geography of structural economic stress across the United States.
Citation
Mungoshi, M. (2025). SNAP Participation and Structural Cost Burdens Across U.S. Counties.
Clarkson University, IA650: Data Mining.
License
This repository is provided for academic and educational purposes only.