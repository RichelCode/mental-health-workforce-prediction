# Mental Health Treatment Prediction in the Workplace

> A machine learning project predicting likelihood of mental health treatment-seeking among tech workers, using the OSMI Mental Health in Tech Survey dataset.

---

## Overview

Mental health disorders affect approximately 1 in 5 adults in the United States, yet treatment rates remain low , particularly in high-pressure industries like tech. This project applies supervised machine learning methods to predict whether a tech worker is likely to seek mental health treatment, based on workplace environment, employer support, demographic factors, and personal attitudes.

The goal is both predictive and interpretive: not just *who* seeks treatment, but *what workplace factors* most strongly influence that decision.

---

## Business & Research Question

**Can we predict whether a tech worker will seek mental health treatment based on their workplace environment and personal background?**

This has direct implications for:
- Employers designing mental health benefit programs
- HR teams identifying high-risk workplace structures
- Public health researchers studying treatment barriers

---

## Dataset

**Source:** [OSMI Mental Health in Tech Survey](https://www.kaggle.com/datasets/osmi/mental-health-in-tech-survey) — Open Sourcing Mental Illness (OSMI)

- 1,259 respondents across 60+ countries
- 27 features covering workplace policies, demographics, attitudes, and mental health history
- Binary outcome: `treatment` ,  whether the respondent has sought mental health treatment

---

## Methods

This project follows a rigorous two-stage resampling framework (Macro/Micro split) and fits five distinct model types:

| Model | Type | Tuned? |
|---|---|---|
| Logistic Regression | Baseline | No |
| Elastic Net (LASSO/Ridge) | Shrinkage | Yes — α, λ |
| K-Nearest Neighbors | Instance-based | Yes — K |
| Random Forest | Ensemble (bagging) | Yes — mtry, ntree |
| Gradient Boosting (XGBoost) | Ensemble (boosting) | Yes — depth, η, rounds |

**Evaluation metrics:** AUC-ROC, Accuracy, Sensitivity, Specificity, F1-Score

---

## Project Structure

```
mental-health-workforce-prediction/
│
├── data/
│   └── survey.csv                  # Raw OSMI survey data
│
├── report/
│   └── mental_health_report.html   # Final rendered report
│
├── mental_health_analysis.Rmd      # Full reproducible R Markdown
└── README.md
```

---

## Key Findings


---

## How to Reproduce

1. Clone this repository
2. Download `survey.csv` from [Kaggle](https://www.kaggle.com/datasets/osmi/mental-health-in-tech-survey) and place in `/data`
3. Open `mental_health_analysis.Rmd` in RStudio
4. Install required packages (listed at top of `.Rmd`)
5. Knit to HTML

**Key packages:** `tidyverse`, `caret`, `glmnet`, `randomForest`, `xgboost`, `pROC`, `ggplot2`

---

## Skills Demonstrated

- Exploratory data analysis & visualization
- Feature engineering & missing data handling
- Macro/Micro resampling strategy
- Hyperparameter tuning via cross-validation
- Model comparison and selection
- Reproducible research with R Markdown
---

## Citation

OSMI Mental Health in Tech Survey (2014). Open Sourcing Mental Illness, LTD. Retrieved from https://www.kaggle.com/datasets/osmi/mental-health-in-tech-survey
