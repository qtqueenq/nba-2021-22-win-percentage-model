# Econometric Analysis of NBA Scoring Metrics & Team Win Percentages

## 📌 Executive Summary
What drives team success in professional basketball? Is victory primarily a function of high-volume individual scoring, or do team-wide offensive efficiency metrics provide superior predictive power? This research project investigates the determinants of regular-season success across all 30 NBA franchises ($N = 30$) using multivariate Ordinary Least Squares (OLS) regression modeling.

By evaluating player-level production (e.g., top scorer Points Per Game) alongside team-level scoring output, this study demonstrates how iterative model respecification and residual diagnostics systematically increase explanatory power ($R^2$ improving from **0.34 to 0.67**).

---

## 🛠️ Tech Stack & Analytical Tools
* **Language:** R
* **Data Wrangling & Visualization:** `tidyverse` (`dplyr`, `ggplot2`, `readr`)
* **Econometric Diagnostics:** `lmTest`, `car`
* **Tables & Reporting:** `stargazer`, `kableExtra`

---

## 🔬 Econometric Methodology & Model Evolution

To test for omitted variable bias and evaluate the stability of scoring parameters, three regression models were iteratively specified:

### 1. **Model 1: Bivariate Baseline (Top Scorer Impact)**
Evaluates whether relying on an elite individual scorer predicts overall team winning percentage:
$$\text{Win\_Pct} = \beta_0 + \beta_1(\text{Top\_Scorer\_PPG}) + u$$

### 2. **Model 2: Multivariate Expansion (Team Offense & Defense)**
Incorporates team-level offensive scoring average and defensive points allowed to isolate net scoring efficiency:
$$\text{Win\_Pct} = \beta_0 + \beta_1(\text{Top\_Scorer\_PPG}) + \beta_2(\text{Team\_PPG}) + \beta_3(\text{Opponent\_PPG}) + u$$

### 3. **Model 3: Full Specification (Net Rating & Efficiency Controls)**
Includes offensive rating, defensive rating, and point differential controls to address structural omitted variable bias:
$$\text{Win\_Pct} = \beta_0 + \beta_1(\text{Point\_Differential}) + \beta_2(\text{Top\_Scorer\_PPG}) + \sum \beta_k(\text{Control\_k}) + u$$

---

## 📊 Key Findings & Econometric Diagnostics

* **Individual Volume vs. Team Efficiency:** Top scorer PPG alone is a weak predictor of overall win percentage ($R^2 = 0.34$), confirming that high-volume scoring without team-wide efficiency does not guarantee regular-season success.
* **Point Differential Efficiency:** Net point differential ($\text{Team PPG} - \text{Opponent PPG}$) accounts for nearly **67% of the variance** in team winning percentages ($p < 0.001$).
* **Diagnostic Verification:**
  * **Multicollinearity:** Verified using Variance Inflation Factors (VIF < 5 across primary predictors).
  * **Heteroskedasticity:** Tested using the Breusch-Pagan test to ensure standard errors were robust and homoskedasticity assumptions held.
  * **Residual Analysis:** Inspected residual plots to confirm linearity and normality of error terms.

---

## 📁 Repository Structure
```text
.
├── data/
│   └── nba_team_stats.csv              # 30-Team NBA Scoring & Performance Dataset
├── scripts/
│   └── econ_317_research_paper.Rmd     # Full R Markdown Analysis Script
├── outputs/
│   └── econ_317_paper.pdf              # Original Academic Paper Output
└── README.md                           # Project Documentation
