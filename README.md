<div align="center">

# Gold Price Forecasting using Machine Learning  
### Python + R | Financial Data Science | Regression, Classification, and Time-Series Modeling

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/R-4.x-276DC3?logo=r&logoColor=white" />
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white" />
  <img src="https://img.shields.io/badge/Domain-Financial%20Forecasting-0A7B34" />
  <img src="https://img.shields.io/badge/Models-Regression%20%7C%20Classification%20%7C%20ARIMA-6A5ACD" />
  <img src="https://img.shields.io/badge/Status-Academic%20Project-success" />
</p>

<p align="center">
  A comparative machine learning and time-series forecasting project for <b>one-day-ahead gold price prediction</b>, built with both <b>Python</b> and <b>R</b> in the same repository.
</p>

</div>

---

## Overview

This repository presents a complete **gold price forecasting pipeline** built around two related academic studies on financial prediction.  
The project combines **macroeconomic indicators**, **commodity signals**, **market indices**, and **technical features** to predict:

- the **next-day gold price**
- the **direction of price movement**
- the behavior of different model families under realistic **time-aware evaluation**

Unlike many forecasting repos that focus on only one toolchain, this repository includes **both Python and R implementations**, making it suitable for:

- machine learning experimentation
- time-series analysis
- cross-language reproducibility
- academic submission and portfolio presentation

---

## Why this project matters

Gold is widely treated as a **safe-haven financial asset**, and its price behavior is influenced by multiple economic and market signals.  
This project studies whether machine learning can meaningfully improve gold forecasting and whether better predictive performance actually translates into **better financial usefulness**.

A major conclusion from the broader study is that **model complexity does not automatically produce better real-world forecasting performance**. In the larger out-of-sample evaluation, **Linear Regression and ARIMA** outperformed more complex tree-based models, while classification-driven trading signals remained weak. :contentReference[oaicite:2]{index=2}

---

## Repository Highlights

<table>
  <tr>
    <td><b>Languages</b></td>
    <td>Python + R in the same repo</td>
  </tr>
  <tr>
    <td><b>Problem Types</b></td>
    <td>Regression, classification, and time-series forecasting</td>
  </tr>
  <tr>
    <td><b>Feature Sources</b></td>
    <td>Gold prices, commodities, currencies, stock indices, technical indicators</td>
  </tr>
  <tr>
    <td><b>Evaluation Focus</b></td>
    <td>Predictive accuracy, generalization, overfitting, and practical interpretability</td>
  </tr>
  <tr>
    <td><b>Key Lesson</b></td>
    <td>Simpler models can outperform more complex ones in trending financial series</td>
  </tr>
</table>

---

## Project Objectives

- Forecast **future gold prices** using regression models
- Predict **upward/downward movement** using classification models
- Compare **baseline**, **statistical**, and **machine learning** approaches
- Evaluate models under **chronological train-test splits**
- Analyze **overfitting**, **feature importance**, and **model limitations**
- Build a portfolio-quality project that demonstrates both **financial reasoning** and **technical implementation**

---

## Data Summary

This repository combines work from two related project reports:

- one study used **3,899 daily observations** spanning **2011 to 2025**
- another study used **1,718 daily records** with **81 features** :contentReference[oaicite:3]{index=3} :contentReference[oaicite:4]{index=4}

### Feature groups used across the project

- **Gold pricing variables**
- **Market indices** such as S&P 500, Dow Jones, and Nasdaq
- **Commodity indicators** such as oil, silver, platinum, and palladium
- **Currency signals** such as USD Index, EUR/USD, and GBP/USD
- **Technical indicators** such as moving averages, daily returns, lagged prices, and trend direction :contentReference[oaicite:5]{index=5} :contentReference[oaicite:6]{index=6}

---

## Methodology

<details>
<summary><b>1. Preprocessing and feature engineering</b></summary>

<br>

The workflow includes:

- chronological sorting of financial time-series data
- missing-value handling using forward fill, with mean imputation where appropriate
- normalization/scaling for distance-based and neural models
- one-day-ahead target generation
- lagged price features
- moving averages
- Bollinger Band deviation
- daily returns and log-returns
- binary trend labeling for directional classification :contentReference[oaicite:7]{index=7} :contentReference[oaicite:8]{index=8}

</details>

<details>
<summary><b>2. Time-aware train/test evaluation</b></summary>

<br>

To avoid look-ahead bias, the forecasting experiments used **chronological train-test splits** rather than random sampling.  
One report explicitly uses an **80/20 split** with **3,095 training observations** and **774 testing observations**, reflecting real out-of-sample forecasting conditions. :contentReference[oaicite:9]{index=9}

</details>

<details>
<summary><b>3. Models evaluated</b></summary>

<br>

### Baselines and statistical models
- Naïve Persistence
- ARIMA

### Regression models
- Linear Regression
- Random Forest Regressor
- XGBoost
- Decision Tree Regressor

### Classification models
- K-Nearest Neighbors (KNN)
- Multi-Layer Perceptron (MLP) :contentReference[oaicite:10]{index=10} :contentReference[oaicite:11]{index=11}

</details>

---

## Key Findings

### Larger out-of-sample forecasting study

The broader forecasting report found that:

- **Linear Regression and ARIMA** achieved the strongest out-of-sample forecasting performance
- tree-based models showed **severe overfitting**
- classification performance was **close to random guessing**
- simple model-based trading strategies produced **negative cumulative returns**
- **buy-and-hold** outperformed model-based trading signals :contentReference[oaicite:12]{index=12}

### Controlled comparative ML study

The other report found strong benchmark metrics for:

- **Linear Regression** with **R² = 0.9961**, **MAE = 0.0865**, **RMSE = 0.1097**
- **Random Forest** with **R² = 0.9837**, **MAE = 0.1896**, **RMSE = 0.2232**
- **KNN** with **Accuracy = 0.7426**, **Precision = 0.7450**, **Recall = 0.6937**, **F1 = 0.7184**
- **MLP** with **Accuracy = 0.7160**, **Precision = 0.7286**, **Recall = 0.6375**, **F1 = 0.6800** :contentReference[oaicite:13]{index=13}

### Practical interpretation

Together, the two studies show an important pattern:

- a model can look very strong in a limited experimental setup
- but still fail under more realistic out-of-sample market behavior
- therefore, **generalization matters more than headline training performance** :contentReference[oaicite:14]{index=14} :contentReference[oaicite:15]{index=15}

---

## Overfitting Insight

One of the strongest findings in the larger study was the failure of tree-based models to extrapolate under a strong upward market trend:

- Random Forest training RMSE was approximately **7 USD**
- test RMSE exceeded **890 USD**
- feature importance showed that **current and lagged gold prices dominated predictions**
- the report concluded that tree-based models are poorly suited for strongly trending extrapolative financial series :contentReference[oaicite:16]{index=16}

---

└── LICENSE
