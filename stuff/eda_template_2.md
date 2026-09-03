# EDA + Product Analytics Template

*A complete workflow: data understanding → cleaning → EDA → business/product metrics → inference → modeling → recommendations. Sections marked "(if applicable)" are conditional branches — skip them when they don't apply to the dataset in front of you.*

## 0. Company Context & Value Engine
- Revenue sources (the economic engine)
- Influence sources (the growth & demand levers)
- Historical high-level revenue summaries & traffic breakdowns

## 1. Define the Question
- Business question / hypothesis to investigate
- Success metric(s) — what "good" looks like
- Stakeholders and how the analysis will be used
- Constraints: data availability, timeframe, decision deadline
- Data source / collection method
- Known sampling or selection biases
- Data freshness / time range relevance

## 2. Analysis Setup
- Load data
- Shape
- Data types / info
- Missing values per column
- Missing values total
- Duplicate count
- Null-value heatmap
- Unique values / cardinality
- Basic data dictionary

## 3. Multi-Table / Relational Checks (if applicable)
*Only relevant when the analysis spans more than one table.*
- Identify join keys and relationship type (1:1, 1:many, many:many)
- Referential integrity — orphaned keys on either side
- Row-count sanity check before vs after each join
- Duplicate keys causing join fan-out
- Schema drift across tables/sources (renamed or type-changed columns)
- Primary key uniqueness per table

## 4. Clean & Optimise Data
- Fix known dtypes
- Convert timestamp columns to datetime
- Handle missing values
- Handle unknown / invalid labels
- Drop rows with missing critical timestamps
- Remove exact duplicate rows
- Convert repetitive string columns to category
- Check inconsistent categorical values
- Check impossible / invalid numerical values
- Check negative values where impossible

## 5. Structural Feature Creation
*Date and location parsing has no dependency on stats, and unlocks grouped analysis below — do it right after cleaning, not after stats.*
- Date: year, month, day, weekday, hour, minute, second, millisecond
- Time periods: week, quarter, weekend/weekday
- Location: city, place, pin code, state, country, area

## 6. Unstructured Data Prep (if applicable)
*Only relevant when the dataset includes free text or images.*

**Text**
- Language detection
- Text length distribution (characters/tokens)
- Vocabulary size, top terms
- Missing/empty text handling
- Basic sentiment or label distribution

**Images**
- Class balance
- Resolution / aspect ratio consistency
- Corrupt or unreadable file check
- Duplicate or near-duplicate detection

## 7. First-Pass Descriptive Stats
*Covers all variables, including the target — now with weekday/region fields available for grouped stats.*
- Row granularity
- Target variable and predictors
- Mean, median, mode, range, variance, standard deviation, IQR, percentiles
- Distribution shape: histogram, skewness, kurtosis, modality, boxplot
- Numerical vs categorical variable summaries
- Grouped statistics / distribution by major segments (e.g. by weekday, by region)

## 8. Outlier Detection & Treatment
*Ahead of relationship/temporal analysis — correlations, trend lines, and growth rates are all outlier-sensitive, so this needs to happen before you compute them, not after.*
- Target-variable outliers
- Dataset-wide outliers
- Z-score method
- IQR method
- Standard vs extreme outliers
- Multivariate outliers
- Investigate cause
- Decide: retain, transform, cap, or remove

## 9. Derived Feature Creation
*These depend on what's above — bands need quartiles from Section 7, ratios/growth need outlier-treated numbers from Section 8.*
- Bands: Low / Medium / High / Premium, or Q1–Q4 (using quartiles from Section 7)
- Business-specific derived variables
- Ratios / percentages
- Growth variables
- Customer-level features

## 10. Relationship Analysis
- Numerical vs numerical
- Categorical vs numerical
- Categorical vs categorical
- Correlation matrix + heatmap
- Scatterplots
- Group comparisons
- Cross-tabulations
- Proportions / rates
- Relationship between target and predictors
- Confounding variables
- Correlation ≠ causation check

## 11. High-Dimensional / Multicollinearity Check (if applicable)
*Relevant once you're past roughly 15–20 predictors, or ahead of a regression-based model.*
- Variance Inflation Factor (VIF) per predictor
- Correlation-based redundancy check
- Dimensionality reduction (PCA) if needed
- Feature clustering / grouping highly correlated predictors

## 12. Temporal Analysis
- Daily / weekly / monthly / quarterly / yearly trends
- Weekday vs weekend
- Hour-of-day patterns
- Seasonality
- Peak periods
- MoM growth
- YoY growth
- Rolling averages
- Trend breaks / unusual periods

## 13. Time-Series Diagnostics (if forecasting)
*Only relevant when the target is being forecast forward in time.*
- Stationarity tests (ADF, KPSS)
- Trend / seasonal / residual decomposition
- ACF / PACF plots
- Differencing (if non-stationary)
- Lag feature creation
- Train/test split respects time order — no shuffling

## 14. Revenue & KPI Lens
*The KPIs here are mostly the same revenue/transaction/customer numbers reframed as tracked metrics, so they belong together.*
- Total transactions, unique customers, AOV
- Revenue, revenue share
- Revenue by segment / location / product / time
- Top / bottom contributors
- Revenue, transaction, customer, and growth KPIs
- Conversion / rate KPIs
- Contribution analysis, Pareto (80/20)

## 15. Customer Profile & Segmentation
- Unique customers, new vs returning
- Frequency, monetary value, average customer value
- Purchase behaviour, customer distribution
- Cohorts
- Demographics (where available)
- Behavioural segments
- RFM analysis
- High-value / low-value / at-risk customers
- Growth opportunities, segment profitability

## 16. Product Analytics — Retention, Engagement & Experimentation

**Retention**
- N-day retention (D1 / D7 / D30)
- Cohort retention curves
- Churn definition and rate
- Resurrection / reactivation rate

**Engagement**
- DAU / WAU / MAU
- Stickiness (DAU:MAU ratio)
- Session frequency and length
- Feature adoption rate

**Funnel Analysis**
- Define funnel steps
- Conversion rate per step
- Drop-off points
- Time-to-convert

**Experimentation / A-B Testing**
- Randomization unit
- Power analysis / minimum detectable effect (pre-launch)
- Sample ratio mismatch (SRM) check
- Primary metric + guardrail metrics
- Novelty / primacy effects
- Segment-level (heterogeneous) treatment effects
- Statistical vs practical significance (uses the toolkit in 17–19)

## 17. Probability Toolkit
- Relevant probability distributions
- Event probabilities
- Conditional probabilities
- Expected value
- Sampling distributions
- Central Limit Theorem
- Standard error

## 18. Confidence Intervals
- Mean confidence intervals
- Proportion confidence intervals
- Difference in means
- Difference in proportions
- Bootstrap confidence intervals where appropriate

## 19. Hypothesis Testing
*Assumption checks come before test selection, not after — you can't correctly pick a test without knowing if the data meets its assumptions.*
- Define null and alternative hypotheses
- Check assumptions first: normality, independence, variance, sample size, multiple-testing considerations
- Select the appropriate test (parametric vs non-parametric) based on those checks
- Calculate test statistic
- P-value, significance level
- Confidence interval, effect size
- Statistical vs practical significance
- Follow-up: robust / non-parametric alternatives if assumptions fail, sensitivity analysis

## 20. Model Preparation & Baseline
- Define target and predictors
- Check target leakage
- Feature selection, encoding, scaling
- Handle class imbalance
- Train / validation / test split
- Baseline model
- Evaluation metric(s)
- Feature importance / interpretation

## 21. Visual Deliverables Checklist
*Coverage check — charts should happen inline as you go through 5–16, not get batched at the end.*
- Distribution charts (7)
- Outlier charts (8)
- Relationship charts + correlation heatmap (10)
- Multicollinearity / PCA charts (11, if applicable)
- Time-series charts (12)
- Time-series decomposition / ACF-PACF charts (13, if applicable)
- Geographic charts (14)
- Segment / KPI charts (14–15)
- Retention / funnel charts (16)
- Text/image distribution charts (6, if applicable)

## 22. Key Business Answers
*Ties back to Section 1.*
- What happened? Why? Where? When?
- Who contributed most? What changed?
- What's driving the target?
- Biggest problems / opportunities
- Does this answer the question posed in Section 1?

## 23. Recommendations
- Key findings
- Business implications
- Recommended actions, prioritized
- Expected impact
- Risks / limitations
- Further analysis required
