# ⚡ Electricity Consumption Forecast

## 📖 Project Overview
This project is a technical assessment solution designed to forecast daily household electricity consumption. The goal was to build a machine learning pipeline that loads historical usage data, performs feature engineering, and generates a 7-day forecast using a regression model.

## 🛠️ Methodology

### 1. Data Handling (Synthetic Generation)
Due to the unavailability of the specific source dataset, I implemented a **Robust Proxy Data Generator** within the notebook.
- **Simulation:** Generated 90 days of daily consumption data.
- **Patterns:** Incorporated realistic "Weekend Spikes" and random noise to mimic actual household behavior.

### 2. Feature Engineering
To capture time-series dependencies, the following features were engineered:
- **`lag_1`**: Consumption from the previous day (capture immediate trend).
- **`lag_7`**: Consumption from the same day last week (capture weekly seasonality).
- **`rolling_mean_7`**: 7-day rolling average (capture general baseline usage).

### 3. Modeling Strategy
- **Algorithm:** Multiple Linear Regression (Scikit-Learn).
- **Validation:** Time-series split (First 80% Train, Last 20% Test).
- **Metric:** Mean Absolute Error (MAE) was used to quantify prediction accuracy in kWh.

## 📊 Results
The model successfully captured the weekly seasonality inherent in the data.
- **Output:** A CSV file (`forecast_next_7_days.csv`) containing predictions for the upcoming week.
- **Performance:** The model demonstrated low variance and successfully tracked the weekend spikes during validation.

## 🚀 How to Run
1. Open the notebook `Electricity_Consumption_Forecast.ipynb` in Google Colab or Jupyter.
2. Run all cells sequentially.
3. The script will automatically generate the dataset, train the model, and save the forecast CSV.

---
*Submitted by Aneesh Kankati*
