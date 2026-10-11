# Econometric Analysis of NBA Scoring Metrics & Team Win Percentages

## 📌 Executive Summary
> 📄 **[Read the Full Research Paper (PDF)](outputs/ECON_317_Research_Paper.pdf)**

What drives team success in professional basketball? Is victory primarily a function of high-volume individual scoring, or do team-wide offensive efficiency metrics provide superior predictive power? This research project investigates the determinants of regular-season success across all 30 NBA franchises ($N = 30$) using multivariate Ordinary Least Squares (OLS) regression modeling built entirely in **Microsoft Excel**.

By evaluating individual player production alongside team-level scoring output, this study demonstrates how iterative model respecification and statistical diagnostics systematically increase explanatory power ($R^2$ improving from **0.34 to 0.67**).

---

## 🛠️ Tech Stack & Analytical Tools
* **Software:** Microsoft Excel
* **Statistical Analysis:** Data Analysis Toolpak (Regression, Descriptive Statistics, Correlation Matrices)
* **Data Wrangling:** Power Query, XLOOKUP, PivotTables, Conditional Formatting
* **Visualization:** Excel Charts & Dynamic Dashboards

---

## 🔬 Econometric Methodology & Model Specification

To test for omitted variable bias and evaluate the stability of scoring parameters, three regression models were iteratively specified:

### 1. **Model 1: Bivariate Baseline (Top Scorer Impact)**
Evaluates whether relying on an elite individual scorer predicts overall team winning percentage:
$$\text{Win Pct} = \beta_0 + \beta_1(\text{Top Scorer PPG}) + u$$

### 2. **Model 2: Multivariate Expansion (Team Offense & Defense)**
Incorporates team-level offensive scoring average and defensive points allowed to isolate net scoring efficiency:
$$\text{Win Pct} = \beta_0 + \beta_1(\text{Top Scorer PPG}) + \beta_2(\text{Team PG}) + \beta_3(\text{Opponent PPG}) + u$$

### 3. **Model 3: Full Specification (Net Point Differential)**
Includes point differential and net efficiency controls to address structural omitted variable bias:
$$\text{Win Pct} = \beta_0 + \beta_1(\text{Point Differential}) + \beta_2(\text{Top Scorer PPG}) + u$$

---

## 📊 Key Findings & Statistical Insights

* **Individual Volume vs. Team Efficiency:** Top scorer PPG alone is a weak predictor of overall win percentage ($R^2 = 0.34$), confirming that high-volume scoring without team-wide efficiency does not guarantee regular-season success.
* **Point Differential Power:** Net point differential ($\text{Team PPG} - \text{Opponent PPG}$) accounts for nearly **67% of the variance** in team winning percentages ($p < 0.001$).
* **Rigorous Validation:** Evaluated $t$-statistics, standard errors, and $p$-values natively within Excel to ensure coefficient significance and validate economic assumptions.

---

## 📁 Repository Structure
```text
.
├── data/
│   └── nba_team_stats.csv              # Raw 30-Team NBA Performance Dataset
├── outputs/
│   └── econ_317_analysis_workbook.xlsx # Fully Audited Excel Model & Regression Outputs
└── README.md                           # Project Documentation
