# Marketing Campaign Analysis and Response Prediction

## Project Overview
This project analyzes a marketing campaign dataset to understand customer behavior and predict response to promotional campaigns. The goal is to identify potential responders using machine learning models and provide actionable insights for marketing strategy.

---

## Dataset
- Source: Marketing Campaign Dataset from Kaggle (https://www.kaggle.com/datasets/rodsaldanha/arketing-campaign), `marketing_campaign.csv`
- Records: 2,240 customers
- Features: Demographics, purchase history, campaign acceptance, and other behavioral metrics.
- Cleaning steps included:
  - Handling missing values (Income)
  - Removing unrealistic birth years
  - Converting dates and categorical features
  - Creating additional features such as Age and Recency in months

---

## Exploratory Data Analysis (EDA)
- Visualizations included:
  - **Figure 1:** Numeric Feature Distributions  
    *Displays histograms of numeric features to identify distributions and potential outliers.*
  - **Figure 2:** Correlation Matrix of Numeric Features  
    *Shows relationships between numeric features to identify potential multicollinearity and insights.*
  - **Figure 3:** Pairwise Relationships of Key Features vs Response  
    *Visualizes distributions and relationships of selected features with the response variable.*

---

## Preprocessing
- Categorical features converted to dummy variables
- Numeric features scaled using `StandardScaler`
- Target variable: `Response` (binary: 0 = No, 1 = Yes)
- Train-test split: 80% train, 20% test

---

## Modeling
### Models Evaluated
1. Logistic Regression (class-weighted, balanced)
2. Random Forest (baseline)
3. Gradient Boosting
4. Random Forest (hyperparameter-tuned)

### Model Performance Comparison

| Model                         | Accuracy | Class 1 Recall | Class 1 F1 |
|-------------------------------|---------|----------------|------------|
| Logistic Regression (Balanced)| 0.815   | 0.75           | 0.57       |
| Random Forest                 | 0.877   | 0.36           | 0.49       |
| Gradient Boosting             | 0.884   | 0.43           | 0.54       |
| Random Forest (Tuned)         | 0.873   | 0.32           | 0.45       |

> **Note:** Because only ~15% of customers responded, the main goal was to identify as many responders as possible. Logistic Regression with class weighting was chosen as the final model due to its highest recall for the positive class.
