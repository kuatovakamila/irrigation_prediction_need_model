# Irrigation Need Prediction Model

## Overview
A machine learning project for predicting irrigation need (Low, Medium, High) 
for the Kaggle Playground Series Season 6 Episode 4 competition.

## Results
- **Final Public Leaderboard Score: 0.97448**
- **Starting Score (Logistic Regression): 0.876**
- **Total Improvement: +9.8%**

## Approach

### Models Used
- CatBoost (3 seeds × 5 folds = 15 models)
- XGBoost (3 seeds × 5 folds = 15 models)  
- LightGBM (5 folds)
- Logistic Regression (meta-model for stacking)

### Key Techniques
1. **Original dataset** — added the source dataset that the competition 
   data was generated from, giving the model more real patterns to learn
2. **Feature engineering** — binary threshold features, categorical bigram 
   interactions, digit features, fold-based aggregate statistics
3. **K-fold cross validation with multiple seeds** — more stable predictions
4. **Stacking** — trained a meta-model on top of all base model predictions
5. **GPU acceleration** — used T4 GPU on Google Colab for faster training

### Score Progression
| Model | Public Score |
|-------|-------------|
| Logistic Regression | 0.876 |
| LightGBM (baseline) | 0.963 |
| LightGBM (full dataset) | 0.965 |
| LightGBM (tuned) | 0.967 |
| CatBoost (2000 iter) | 0.967 |
| CatBoost (10000 iter, GPU) | 0.974 |
| Stacked CatBoost + XGBoost + LightGBM | **0.97448** |

## Competition
Kaggle Playground Series S6E4 — Predicting Irrigation Need  
https://www.kaggle.com/competitions/playground-series-s6e4
