# Benzene Sulfonation Process Optimization

## Project Overview

This project aims to optimize the production of **benzenesulphonic acid** in a chemical plant by analyzing data collected from a **double-pipe heat exchanger reactor**. The goal is to maximize the composition of benzenesulphonic acid while minimizing production costs, using operational data from one month. The project focuses on understanding the process, pre-processing the data, developing models for prediction, and providing recommendations for cost-efficient production.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Process Understanding](#process-understanding)
    - [System Diagram](#system-diagram)
    - [Variable Classification](#variable-classification)
    - [Cost vs Revenue Streams](#cost-vs-revenue-streams)
3. [Data Pre-processing](#data-pre-processing)
    - [Data Quality Concerns](#data-quality-concerns)
    - [Data Cleaning Techniques](#data-cleaning-techniques)
    - [Feature Engineering](#feature-engineering)
4. [Model Development and Evaluation](#model-development-and-evaluation)
    - [Data Transformation and Partitioning](#data-transformation-and-partitioning)
    - [Model Training](#model-training-linear-regression-knn-neural-networks)
    - [Model Selection](#model-selection)
    - [Model Testing and Key Variable Identification](#model-testing-and-key-variable-identification)
5. [Recommendations](#recommendations)
    - [Steam Behavior Insights](#steam-behavior-insights)
    - [Optimal Mole Ratio of Benzene to Sulfuric Acid](#optimal-mole-ratio-of-benzene-to-sulfuric-acid)
6. [Conclusion](#conclusion)

---

## Introduction

In the production of **benzenesulphonic acid**, a stream of pure **benzene** is mixed with pure **sulphuric acid** and passed through a **double-pipe heat exchanger**. The reaction is endothermic, and low-quality steam flows through the outer tube, while the reaction mixture passes through the inner tube.

The plant's objective is to maximize the benzenesulphonic acid concentration in the product stream while minimizing production costs. Data collected over a month includes flow rates of benzene, sulphuric acid, and steam, as well as temperature readings at various points in the system.

This project analyzes the provided data to:
1. **Understand the process** and identify relevant variables.
2. **Pre-process** and clean the data for model development.
3. **Develop and evaluate predictive models** for the **mass fraction of benzenesulphonic acid** in the product stream.
4. **Provide recommendations** to improve product composition and reduce costs.

---

## Process Understanding

### System Diagram & Variable Classification

A system diagram will visualize the flow of benzene and sulphuric acid through the heat exchanger reactor. Variables can be classified as follows:

- **Disturbance Variables**: Temperature of steam entering the heat exchanger, ambient temperature.
- **Manipulated Variables**: Flow rates of benzene, sulphuric acid, and steam.
- **Outputs**: Mass fraction of benzenesulphonic acid in the effluent stream, temperature of product stream.
- **States**: Internal temperature of the heat exchanger, flow rates of inputs.

### Cost vs Revenue Streams

- **Revenue-generating Streams**: The **benzenesulphonic acid** produced.
- **Cost-associated Streams**: **Benzene**, **sulphuric acid**, and **steam** are considered cost-generating streams due to their consumption in the production process.

---

## Data Pre-processing

### Data Quality Concerns

- **Missing Data**: Temperature readings may be missing for some records.
- **Outliers**: Extreme values in flow rates and temperatures should be identified and addressed.
- **Inconsistent Units**: All data must use consistent units for accurate analysis.

### Data Cleaning Techniques

- **Missing Values**: Imputation (e.g., forward filling, interpolation) will be applied to handle missing data.
- **Outlier Detection**: Methods like IQR or Z-score will be used to detect and handle outliers.
- **Scaling**: Standardization or normalization of variables will be performed to ensure fair contribution in model development.

### Feature Engineering

- **Mole Ratio**: A feature for the **mole ratio of benzene to sulfuric acid** will be created to examine its impact on the output.
- **Additional Features**: A feature based on the **temperature difference between input and output streams** will be engineered to assess heat exchanger efficiency.

---

## Model Development and Evaluation

### Data Transformation and Partitioning

- **Data Transformation**: Transformations like log-scaling or power transformations will be applied to any skewed data.
- **Data Partitioning**: The data will be split into training, validation, and test sets (e.g., 70% training, 15% validation, 15% testing).

### Model Training: Linear Regression, KNN, Neural Networks

1. **Linear Regression**: A baseline model to predict the mass fraction of benzenesulphonic acid.
2. **K-Nearest Neighbors (KNN)**: A non-linear model with hyperparameters like the number of neighbors tuned via cross-validation.
3. **Neural Network**: A complex model with tuned hyperparameters for the number of layers and nodes.

### Model Selection

Model performance will be evaluated using metrics such as **Mean Squared Error (MSE)** and **R-squared** on validation data. The best-performing model will be selected for further testing.

### Model Testing and Key Variable Identification

The selected model will be tested on unseen data, and key variables will be identified to understand their significance in the predictions. The variables’ relevance will be compared to domain knowledge.

---

## Recommendations

### Steam Behavior Insights

By analyzing the time series of steam temperature (T_steam_in), steam flow rate (q_steam), and product temperature (T_prod_out), potential explanations for steam flow anomalies will be identified. Recommendations will be provided on how to adjust steam flow and temperature for improved efficiency.

### Optimal Mole Ratio of Benzene to Sulfuric Acid

Using prescriptive analysis, an optimal **mole ratio of benzene to sulfuric acid** will be recommended to maximize the product yield. This analysis will consider the average feed temperature of 20°C.

---

## Conclusion

This report will present key findings, highlight the best predictive model for benzenesulphonic acid concentration, and provide actionable recommendations to optimize plant operations. By optimizing both the mole ratio and steam behavior, production costs can be reduced, and the output can be maximized.

