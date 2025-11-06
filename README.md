# Temp-Logistics-Detroit's-Seasonal-Strategy
This project uses Random Forest, LSTM, and GRU models to predict Detroit’s monthly extreme temperatures. Accurate forecasts help enhance logistics efficiency, route optimisation, vehicle maintenance, and cargo safety. The GRU model achieved the best performance with an R² of 0.91.


## 🎯 Objectives
- Build and evaluate predictive models (Random Forest, LSTM, GRU) for temperature forecasting.
- Analyze historical weather data spanning **20 years**.
- Compare model performance to identify the most accurate and robust forecasting approach.
- Apply insights to optimize logistics and reduce weather-related disruptions.

---

## 🧩 Dataset
- **Source:** [Meteostat](https://meteostat.net/)
- **Data:** 20 years of historical temperature data for Detroit.
- **Features:** Average, minimum, and maximum temperature, precipitation, snowfall, and wind speed.
- **Preprocessing Steps:**
  - Removed irrelevant or incomplete columns (`tsun`, `wdir`).
  - Filled missing values using seasonal medians.
  - Standardized ‘tavg’ (average temperature) via imputation and normalization.

---

## ⚙️ Data Preprocessing
1. Handled missing and inconsistent data entries.  
2. Imputed missing `tavg` using the mean of `tmin` and `tmax`.  
3. Normalized data with `MinMaxScaler`.  
4. Created **lag features** (`lag1`, `lag2`, `lag3`) for temporal dependency.  
5. Split dataset into **80% training** and **20% testing** sets.

---

## 🧠 Model Architectures

### 🌲 **Random Forest**
- 100 estimators  
- Handles nonlinear relationships  
- **MSE:** 13.22  
- **RMSE:** 3.64  
- **MAE:** 2.69  
- **R²:** 0.883  

---

### 🔁 **LSTM (Long Short-Term Memory)**
- Sequence length: 30 days  
- Trained for 100 epochs, batch size 32  
- **MSE:** 7.94  
- **RMSE:** 2.82  
- **R²:** 0.910  
- Captures temporal dependencies and seasonal variations.

---

### 🔄 **GRU (Gated Recurrent Unit)**
- Two GRU layers (50 units each) + Dense output layer  
- Trained for 30 epochs  
- **MSE:** 0.00297  
- **R²:** 0.912  
- Most accurate and efficient model for forecasting.  

---

## 📊 Model Comparison

| Model        | MSE      | RMSE   | MAE   | R² Score |
|---------------|----------|--------|-------|-----------|
| Random Forest | 13.220   | 3.636  | 2.694 | 0.883     |
| LSTM          | 7.941    | 2.818  | —     | 0.910     |
| GRU           | 0.00297  | —      | —     | 0.912     |

✅ **GRU achieved the highest accuracy**, making it the most reliable model for temperature prediction and logistics planning.

---

## 🚀 Business Impact

- **Enhanced Routing Efficiency:** Predict temperature extremes to avoid heat-related or icy road delays.  
- **Proactive Vehicle Maintenance:** Schedule maintenance based on forecasted weather stress.  
- **Improved Cargo Safety:** Protect perishable or temperature-sensitive goods during transport.  
- **Resource Optimization:** Reduce energy usage by aligning with forecasted temperature trends.

---

## 🧰 Tech Stack
- **Python**
- **TensorFlow / Keras**
- **Pandas / NumPy**
- **Scikit-learn**
- **Matplotlib / Seaborn**
