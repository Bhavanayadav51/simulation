# Data Generation using Simulation for Machine Learning

## Overview

This project focuses on generating synthetic data using a simulation-based approach and applying machine learning models to analyze it. Instead of relying on real-world datasets, a queueing system is simulated to produce data under different conditions. The generated dataset is then used to train and evaluate multiple regression models.

---

## Objective

The main goals of this project are:

* To explore and implement a simulation framework
* To understand how system parameters affect outcomes
* To generate a dataset using repeated simulations
* To apply multiple machine learning models on the generated data
* To compare model performance using standard evaluation metrics

---

## Simulation Framework

**Tool Used:** SimPy (Discrete Event Simulation Library in Python)

SimPy is used to simulate a real-world queue system where events occur over time. It allows modeling of systems such as customer service operations, making it suitable for this project.

---

## System Description

A simplified bank queue system is modeled where:

* Customers arrive randomly over time
* A fixed number of servers attend customers
* Each customer experiences a waiting time before service

---

## Target Variable

The key output of the simulation is:

* **Average Waiting Time**, which is used as the dependent variable for machine learning models

---

## Simulation Parameters

| Parameter         | Description                    | Range     |
| ----------------- | ------------------------------ | --------- |
| Arrival Rate      | Rate at which customers arrive | 0.2 – 2.0 |
| Service Rate      | Speed of service               | 0.5 – 2.5 |
| Number of Servers | Available service counters     | 1 – 5     |

---

## Data Generation Methodology

* Random values are sampled within predefined parameter ranges
* These values are passed to the simulation model
* The simulation runs and computes the average waiting time
* This process is repeated multiple times (1000 iterations)
* The results are stored as a structured dataset

---

## Dataset Structure

The generated dataset contains the following features:

* `arrival_rate`
* `service_rate`
* `num_servers`
* `avg_wait_time` (target variable)

---

## Machine Learning Models Applied

Several regression models were implemented to study performance differences:

* Linear Regression
* Ridge Regression
* Lasso Regression
* Decision Tree Regressor
* Random Forest Regressor
* Gradient Boosting Regressor
* Support Vector Regressor (SVR)

---

## Evaluation Criteria

Models were evaluated using:

* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)
* R² Score

---

## Performance Summary

| Model             | Performance Insight          |
| ----------------- | ---------------------------- |
| Linear Regression | Struggles with non-linearity |
| Decision Tree     | Moderate performance         |
| Random Forest     | Best overall performance     |
| Gradient Boosting | Strong and consistent        |
| SVR               | Moderate accuracy            |

👉 **Best Model:** Random Forest Regressor

---

## Visual Analysis

The following visualizations are included in the notebook:

* Scatter plot of actual vs predicted values
* Feature importance graph

These help in understanding prediction accuracy and the influence of different parameters.

---

## Technologies Used

* Python
* SimPy
* NumPy
* Pandas
* Scikit-learn
* Matplotlib

---

## Conclusion

This project highlights how simulation can be effectively used to generate datasets when real-world data is unavailable. The results indicate that ensemble learning methods, particularly Random Forest, are well-suited for capturing complex relationships in simulation-generated data.

---
