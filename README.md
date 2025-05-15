# Forecasting Italy's Climate 1 and 10 Years Ahead Using ML

## **Overview**
This project applies machine learning techniques to forecast average monthly temperatures in Italy using the Global Historical Climatology Network (GHCN) daily dataset. The models explored include:

- Recurrent Neural Networks (RNNs)
- Long Short-Term Memory networks (LSTMs)

Performance is benchmarked against a naive baseline to assess effectiveness.

---

## **Objectives**

- Forecast average monthly temperatures in Italy over 1-year and 10-year horizons  
- Evaluate model performance using Mean Squared Error (MSE)  
- Assess the impact of using single vs. multiple weather stations  
- Conduct station removal experiments to analyse data sensitivity  

---

## **Dataset**

- **Source:** GHCN-Daily (NOAA)  
- **Scope:** Temperature data (TMAX, TMIN) from five Italian weather stations  

**Preprocessing Steps:**
- Parsed `.dly` files  
- Rescaled temperature values (tenths of degrees)  
- Aggregated daily data into monthly averages  
- Handled missing values and ensured temporal consistency  

---

## **Methodology**

- **Models Used:** RNN, LSTM  
- **Baseline:** Naive prediction (e.g. next temperature = current temperature)  
- **Forecast Horizons:**  
  - Short-term: 12 months (1 year)  
  - Long-term: 120 months (10 years)  
- **Input Format:** Sliding window of 12 months as input to predict the future horizon  
- **Evaluation Strategy:**  
  - 80/20 train/test split  
  - Early stopping  
  - Mean Squared Error (MSE) metrics  

---

## **Key Results**

### **1-Year Forecast (12 Months)**

- **Single Station:**
  - RNN and LSTM underperformed due to data sparsity  
  - Naive baseline outperformed both models  

- **Multiple Stations:**
  - Combining all five stations improved performance  
  - Both RNN and LSTM outperformed the naive baseline  
    - **LSTM MSE:** 4.99  
    - **RNN MSE:** 4.89  
    - **Baseline MSE:** 5.13  

### **10-Year Forecast (120 Months)**

- **Model:** LSTM only (RNN failed due to gradient issues)  
- **Outcome:** Initial months predicted accurately  
- **Problem:** Long-term performance degraded due to overfitting and data limitations  

---

## **Station Sensitivity Analysis**

- Removing stations with the highest data gaps improved model accuracy  
- Best performance achieved by removing:
  - `IT000016134`
  - `IT000162580`  
- Excessive station removal reduced model performance due to limited training data and loss of pattern redundancy  

---

## **Limitations & Future Work**

- **Data Quality:**  
  - Sparse datasets and missing values negatively impact model learning  

- **Feature Scope:**  
  - Introducing additional variables (e.g. precipitation, snow depth) may enhance predictions  

- **Model Tuning:**  
  - Further hyperparameter tuning and sequence extrapolation methods recommended  

- **Geospatial Features:**  
  - Integrating elevation and coordinates may improve temporal coherence between stations
 
  ---

## **Author**

**Giorgi Markhulia**  
BSc Natural Sciences, UCL  
_March 2025_
