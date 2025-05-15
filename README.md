# Forecasting-Italy-s-Climate-1-and-10-Years-head-Using-ML

Overview
This project applies machine learning techniques to forecast average monthly temperatures in Italy using the Global Historical Climatology Network (GHCN) daily dataset. The models explored include Recurrent Neural Networks (RNNs) and Long Short-Term Memory networks (LSTMs), with performance benchmarks against a naive baseline.

Objectives
Forecast average monthly temperatures in Italy over 1-year and 10-year horizons.

Evaluate model performance using Mean Squared Error (MSE).

Assess the impact of using single versus multiple weather stations.

Conduct station removal experiments to analyse data sensitivity.

Dataset
Source: GHCN-Daily (NOAA)

Scope: Temperature data (TMAX, TMIN) from five Italian weather stations

Preprocessing:

Parsed .dly files

Rescaled temperature values

Aggregated daily readings to monthly averages

Handled missing data and ensured temporal alignment across stations

Methodology
Models: RNN and LSTM

Baseline: Naive forecast (next temperature = current temperature)

Forecast Horizons: 12 months (1 year), 120 months (10 years)

Input Format: Sliding window of 12 months history to predict the future horizon

Evaluation: Training/validation split (80/20), early stopping, MSE metrics

Station Sensitivity Analysis
Removing stations with the most missing data improved model accuracy significantly.

Optimal performance achieved by removing stations IT000016134 and IT000162580.

Excessive station removal degraded model performance due to reduced training data size and inter-station variability.

Limitations & Future Work
Data Quality: Missing entries across stations significantly hinder model learning.

Feature Scope: Inclusion of additional climate variables (precipitation, snow) is proposed.

Model Tuning: Further hyperparameter tuning and use of extrapolation techniques to fill data gaps could enhance results.

Geospatial Features: Incorporating station elevation and coordinates into the model may improve accuracy.

Author
Giorgi Markhulia — BSc Natural Sciences, UCL
Project completed in March 2025.
