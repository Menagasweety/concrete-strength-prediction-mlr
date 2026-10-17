# Concrete Compressive Strength Prediction Using Multiple Linear Regression

## Project Overview

This project applies Multiple Linear Regression to estimate concrete compressive strength using the quantities of concrete ingredients and curing age.

Concrete strength is a continuous numerical target, making this a supervised regression problem. The project explores the dataset, establishes a baseline, trains a regression model, and evaluates its predictive performance on unseen test data.

## Problem Statement

Can concrete compressive strength be estimated from eight numerical input features?

The objective is to learn relationships between the concrete mixture characteristics and measured compressive strength, then evaluate how accurately the model predicts strength for unseen observations.

## Dataset

- **Source:** UCI Machine Learning Repository
- **Dataset:** Concrete Compressive Strength
- **Observations:** 1,030
- **Input features:** 8
- **Target variable:** Concrete compressive strength (MPa)

### Input Features

- Cement
- Blast furnace slag
- Fly ash
- Water
- Superplasticizer
- Coarse aggregate
- Fine aggregate
- Age in days

**Target:** Concrete compressive strength, measured in megapascals (MPa).

Dataset source: https://archive.ics.uci.edu/dataset/165/concrete+compressive+strength

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Project Workflow

1. Load and inspect the dataset.
2. Standardize column names for easier analysis.
3. Check missing values, duplicate observations, and descriptive statistics.
4. Explore feature distributions and correlations.
5. Separate input features and the target variable.
6. Split the data into training and testing sets using an 80:20 ratio.
7. Establish a mean-prediction baseline.
8. Train a Multiple Linear Regression model.
9. Evaluate performance using MAE, RMSE, and R².
10. Examine actual-versus-predicted values, residuals, and large prediction errors.

## Model Evaluation

The following results were obtained on the held-out test set containing 206 observations.

| Metric | Mean Baseline | Multiple Linear Regression |
|---|---:|---:|
| MAE (MPa) | 13.052 | 7.745 |
| RMSE (MPa) | 16.054 | 9.797 |
| R² | Approximately 0.000 | 0.628 |

The regression model reduced MAE by approximately 40.7% compared with the baseline. Its lower MAE and RMSE indicate improved predictive performance on this test set.

The R² score of 0.628 indicates that the model explains approximately 62.8% of the variation in the test-set target relative to a mean benchmark.

## Residual Analysis

The residuals-versus-fitted plot suggests that residual spread may vary across predicted strength values. The largest absolute prediction error in the test set was 27.78 MPa.

These findings indicate that the model has limitations and may not capture every relationship in the dataset. The visual pattern raises a question about constant error variance, but further diagnostic analysis would be required to establish whether the assumption is violated.

## Key Learnings

- Preparing and exploring a real-world numerical dataset.
- Understanding features, targets, and train-test splitting.
- Establishing a regression baseline before evaluating a trained model.
- Training and interpreting Multiple Linear Regression.
- Evaluating regression models with MAE, RMSE, and R².
- Using residual analysis to investigate prediction errors and model limitations.

## Limitations

Multiple Linear Regression may not fully represent nonlinear relationships or interactions between concrete ingredients. The model also produces substantial errors for some observations.

The reported results are based on one train-test split and should not be assumed to represent performance on every future dataset.

This project is for educational purposes only. Its predictions must not replace laboratory testing, applicable standards, or qualified engineering judgment for construction safety.

## Repository Structure

```text
Multiple_Linear_Regression_Concrete/
├── data/
│   └── Concrete_Data.xls
├── notebooks/
│   └── multiple_linear_regression.ipynb
├── README.md
└── requirements.txt
```

## How to Run the Project

1. Clone or download this repository.
2. Install the required packages using `pip install -r requirements.txt`.
3. Place the dataset file in the `data/` folder.
4. Open the notebook in Jupyter.
5. Run the cells in order.

The notebook expects the dataset at `../data/Concrete_Data.xls` when executed from the `notebooks/` directory.
