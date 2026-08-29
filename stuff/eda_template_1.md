# EDA Template

## 1. Analysis Setup

* Observe dataset

* Download / load data

* Shape

* Data types / Info

* Missing values per column

* Missing values total

* Duplicate count

* Null-value heatmap

* Unique values / cardinality

* Basic data dictionary

## 2. Clean & Optimise Data

* Fix known dtypes

* Convert timestamp columns to datetime

* Handle missing values

* Handle unknown / invalid labels

* Drop rows with missing critical timestamps

* Remove exact duplicate rows

* Convert repetitive string columns to category

* Check inconsistent categorical values

* Check impossible / invalid numerical values

* Check negative values where impossible

## 3. Feature Creation

* Location: city, place, pin_code, state, country, area_name

* Date: year, month, day, weekday, hour, minute, second, millisecond

* Time periods: week, quarter, weekend/weekday

* Bands: Low, Medium, High, Premium OR Q1, Q2, Q3, Q4

* Business-specific derived variables

* Ratios / percentages

* Growth variables

* Customer-level features

## 4. Characteristics of Target Variable

* Row granularity

* Target variable for analysis

* Target variable predictors

* Descriptive statistics

* Mean

* Median

* Mode

* Range

* Variance

* Standard deviation

* IQR

* Distribution of target variable → histogram

* Shape of distribution

* Skewness

* Kurtosis

* Modality

* Boxplot

## 5. Descriptive Statistics

* Descriptive statistics — all relevant variables

* Numerical variables

* Categorical variables

* Grouped statistics

* Mean / median comparison

* Percentiles

* Distribution by major segments

## 6. Relationship Analysis

* Numerical vs numerical

* Categorical vs numerical

* Categorical vs categorical

* Correlation matrix

* Correlation heatmap

* Scatterplots

* Group comparisons

* Cross-tabulations

* Proportions / rates

* Relationship between target and predictors

* Identify potential confounding variables

* Correlation ≠ causation assessment

## 7. Temporal Analysis

* Daily trends

* Weekly trends

* Monthly trends

* Quarterly trends

* Yearly trends

* Weekday vs weekend

* Hour-of-day patterns

* Seasonality

* Peak periods

* MoM growth

* YoY growth

* Rolling averages

* Trend breaks / unusual periods

## 8. Outlier Detection

* Target-variable outliers

* Dataset-wide outliers

* Z-score

* IQR method

* Standard outliers

* Extreme outliers

* Multivariate outliers

* Investigate cause of outliers

* Decide: retain, transform, cap, or remove

## 9. Revenue Lens

* Total transactions

* Unique customers

* AOV — Average Order Value

* Revenue

* Revenue share

* Revenue by segment

* Revenue by location

* Revenue by product/category

* Revenue by time

* Top / bottom contributors

## 10. Customer Profile

* Unique customers

* New vs returning customers

* Customer frequency

* Customer monetary value

* Average customer value

* Purchase behaviour

* Customer distribution

* Customer cohorts

* Customer segments

## 11. Money Segment / KPI Analysis

* Revenue KPIs

* Transaction KPIs

* Customer KPIs

* Conversion / rate KPIs where applicable

* Growth KPIs

* Segment KPIs

* Contribution analysis

* Pareto / 80-20 analysis

## 12. Probability Analysis

* Relevant probability distributions

* Event probabilities

* Conditional probabilities

* Expected value

* Sampling distributions

* Central Limit Theorem

* Standard error

## 13. Confidence Intervals

* Mean confidence intervals

* Proportion confidence intervals

* Difference in means

* Difference in proportions

* Bootstrap confidence intervals where appropriate

## 14. Hypothesis Tests

* Define null hypothesis

* Define alternative hypothesis

* Select appropriate test

* Test assumptions

* Calculate test statistic

* P-value

* Significance level

* Confidence interval

* Effect size

* Statistical vs practical significance

## 15. Verify Tests

* Normality assumptions

* Independence

* Variance assumptions

* Sample-size requirements

* Multiple-testing considerations

* Robust / non-parametric alternatives

* Sensitivity analysis

## 16. Chart Set

* Distribution charts

* Comparison charts

* Relationship charts

* Time-series charts

* Geographic charts

* Segment charts

* KPI charts

* Outlier charts

* Correlation heatmap

## 17. Customer Profile / Segmentation

* Customer demographics where available

* Behavioural segments

* RFM analysis

* High-value customers

* Low-value customers

* At-risk customers

* Growth opportunities

* Segment profitability

## 18. Model Preparation

* Define target

* Define predictors

* Check target leakage

* Feature selection

* Feature encoding

* Feature scaling where required

* Handle class imbalance

* Train / validation / test split

* Prepare modelling dataset

## 19. Key Business Answers

* What happened?

* Why did it happen?

* Where did it happen?

* When did it happen?

* Who contributed most?

* What changed?

* What is driving the target?

* What are the biggest problems?

* What are the biggest opportunities?

## 20. Recommendations

* Key findings

* Business implications

* Recommended actions

* Priority actions

* Expected impact

* Risks / limitations

* Further analysis required
