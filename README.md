# 16PF Gender Prediction

This project analyzes whether gender can be predicted from responses to Cattell’s 16 Personality Factor (16PF) questionnaire using dimensionality reduction and classification models.

Using data from over 49,000 respondents, I apply Principal Component Analysis (PCA) to reduce 162 questionnaire items into latent personality factors, then evaluate how well those factors predict gender using logistic regression and LASSO regularization.

---

## Data

- **Source:** Kaggle (uploaded by Bojan Tunguz) (<https://www.kaggle.com/datasets/tunguz/cattells-16-personality-factors>)
- **Original source:** Open-Source Psychometrics Project (<https://openpsychometrics.org/_rawdata/>)
- **Observations:** 49,159 respondents  
- **Variables:**
  - 162 personality questions (Likert scale 1–5)
  - Gender (Male / Female; other values removed)

---

## Methods

- Data cleaning and filtering
- Correlation analysis and multicollinearity checks
- Principal Component Analysis (PCA)
  - Bartlett’s Test of Sphericity
  - Kaiser–Meyer–Olkin (KMO) test
  - Parallel analysis to select number of components
- Logistic regression
- LASSO regularization (glmnet)
- Model evaluation:
  - Accuracy
  - Kappa
  - Sensitivity / Specificity
  - RMSE
  - AIC

---

## Key Findings

- PCA identified **22 latent personality components**, not the original 16 proposed by Cattell.
- Gender prediction accuracy reached **~76% on testing data**, indicating performance better than random but far from deterministic.
- Strongest predictors of **men**:
  - Introverted
  - Insecure
  - Present-focused
  - Defiant
- Strongest predictors of **women**:
  - Quiet
  - Scattered
  - Funny
  - Bold
  - Intellectual
- Results challenge common gender stereotypes and suggest personality differences by gender are present but limited.

---

## Limitations

- Personality responses are self-reported.
- PCA-derived factors differed in size and interpretability.
- Gender is difficult to predict accurately from personality alone.
- LASSO offered minimal improvement due to large sample size and limited predictors.

---

## Future Work

- Compare results using Cattell’s original 16 factors
- Explore prediction of other variables (e.g., age, country)
- Test non-linear models (e.g., random forests, SVMs)

---

## Tools & Libraries

R packages used include:
- tidyverse
- psych
- caret
- glmnet
- factoextra
- GGally

---

## Author

**Cami Krugel**
