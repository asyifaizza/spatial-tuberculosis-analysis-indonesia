# East Java Tuberculosis Spatial Analysis

**Spatial Data Analysis | Statistical Modeling | Public Health Analytics**

An exploratory statistical analysis of tuberculosis (TB) cases across regencies and cities in East Java, Indonesia, in 2025. This project investigates the distribution of TB cases, examines relationships with socioeconomic and public health indicators, and evaluates spatial patterns to support further spatial count modeling.

## Project Overview

Tuberculosis (TB) remains a significant public health concern in Indonesia. Differences in the number of reported cases across regions may reflect variations in population characteristics, healthcare availability, economic conditions, and environmental factors.

This project analyzes TB case counts across **38 regencies and cities in East Java in 2025**, using exploratory data analysis, count regression models, and spatial diagnostic tests.

The analysis focuses on understanding the distribution of TB cases, evaluating overdispersion in Poisson regression, and identifying spatial heterogeneity and autocorrelation that may inform subsequent modeling decisions.

## Objectives

- Explore the distribution of TB cases across regencies and cities in East Java.
- Examine the relationship between TB case counts and selected socioeconomic and public health indicators.
- Evaluate multicollinearity among explanatory variables.
- Compare Poisson and Negative Binomial regression approaches.
- Assess spatial heterogeneity and spatial autocorrelation to inform further spatial modeling.

## Dataset

The analysis uses regional data compiled from the following sources:

- Open Data Jawa Timur
- Badan Pusat Statistik (BPS) Indonesia

The dataset contains **38 observations**, representing regencies and cities in East Java, with geographic coordinates, TB case counts, population information, and explanatory variables.

### Variables

| Variable | Description |
|---|---|
| `tbc` | Number of tuberculosis cases |
| `miskin` | Number of people living in poverty |
| `faskes` | Number of healthcare facilities |
| `pdrb` | Gross Regional Domestic Product (GRDP) |
| `sanitasi` | Percentage of households with adequate sanitation |
| `tpt` | Open unemployment rate |
| `iku` | Environmental Quality Index |
| `penduduk` | Total population |
| `longitude` | Regional longitude |
| `latitude` | Regional latitude |

The response variable is the number of TB cases. The explanatory variables represent selected socioeconomic, healthcare, and environmental characteristics.

## Methodology

The analysis follows these stages:

### 1. Data Preparation

- Import and organize regional datasets.
- Prepare geographic coordinates and analytical variables.
- Inspect the dataset structure and check for missing values.
- Generate descriptive statistics for the variables.

### 2. Exploratory Data Analysis (EDA)

- Examine the distribution of TB case counts.
- Calculate descriptive statistics, including the mean, variance, and standard deviation.
- Visualize the distribution of cases.
- Map TB case counts across East Java to explore regional variation.

### 3. Multicollinearity Assessment

Variance Inflation Factor (VIF) is used to assess multicollinearity among explanatory variables.

The initial analysis reports VIF values below 10 for all explanatory variables, indicating no strong multicollinearity based on this threshold.

### 4. Poisson Regression

Poisson regression is fitted as an initial count regression model.

The analysis includes:

- Likelihood Ratio testing.
- Parameter estimation and significance assessment.
- Model fit evaluation using deviance and Akaike Information Criterion (AIC).
- Overdispersion diagnostics.

### 5. Overdispersion Testing

Overdispersion is assessed using two approaches:

- The dispersion test implemented through the `AER` package.
- The Cameron–Trivedi approach.

The initial results indicate evidence of overdispersion under the `AER` test, motivating further evaluation of alternative count regression models.

### 6. Negative Binomial Regression

Negative Binomial regression is evaluated as an alternative to Poisson regression to account for overdispersion.

The analysis examines parameter estimates, statistical significance, model fit, and the estimated dispersion parameter.

### 7. Spatial Diagnostics

Spatial diagnostic tests are conducted to investigate regional variation and spatial dependence.

- **Breusch–Pagan test:** assesses heteroskedasticity in the auxiliary model.
- **Moran's I test:** evaluates spatial autocorrelation in TB case counts.

The initial Moran's I test indicates statistically significant positive spatial autocorrelation at the 5% significance level.

These findings motivate further investigation of spatial modeling approaches.

## Key Findings

The preliminary analysis produced the following findings:

- **Regional variation:** TB case counts differ across regencies and cities in East Java.
- **Overdispersion:** The variance of TB case counts substantially exceeds the mean, indicating potential overdispersion.
- **Multicollinearity:** All explanatory variables have reported VIF values below 10.
- **Poisson regression:** The initial model indicates statistically significant joint contributions from the explanatory variables.
- **Negative Binomial regression:** This alternative model is evaluated to address overdispersion; its parameter estimates differ from those of the Poisson model.
- **Spatial heterogeneity:** The Breusch–Pagan test indicates heteroskedasticity in the auxiliary model.
- **Spatial autocorrelation:** Moran's I test reports positive and statistically significant spatial autocorrelation in TB case counts.

These are preliminary findings from the current analysis. Further model evaluation is needed before drawing final conclusions about spatial relationships or selecting a final model.

## Tools & Technologies

- **R** — Statistical computing and modeling
- **RStudio** — Analysis workflow and reporting
- **Data visualization** — Distribution plots and spatial maps
- **Statistical methods** — Poisson regression, Negative Binomial regression, VIF, Breusch–Pagan test, and Moran's I

## Future Work

The next stages of the project may include:

- Further evaluation of spatial count regression methods.
- Investigation of geographically varying relationships between explanatory variables and TB cases.
- Implementation and evaluation of Geographically Weighted Negative Binomial Regression (GWNBR) with an Adaptive Bisquare weighting scheme, subject to methodological validation.
- Comparison of candidate models using appropriate goodness-of-fit criteria and diagnostic tests.

## Project Status

**Status:** Exploratory analysis and preliminary statistical modeling.

The current work establishes an initial analytical foundation for investigating TB case distribution and spatial patterns in East Java. Final spatial model selection and validation remain areas for further development.

## Authors

- **Asyifa Izzatil Isma**
- **M. Aufa Ibadillah**

## Disclaimer

This repository documents an ongoing academic project. The methods, results, visualizations, and interpretations presented here are preliminary and may be updated as the project develops. The current findings should not be considered final conclusions.
