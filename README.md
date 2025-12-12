# 📈 Sales Forecast Model — Walmart Weekly Sales  
**Author:** Ana C. Carrasco  
**Tools:** Python, Pandas, Matplotlib, Statsmodels, Prophet, Excel  

---

## 📌 Overview
This project focuses on building and evaluating sales forecasting models using historical weekly sales data from Walmart. The goal was to compare different forecasting approaches, starting from a simple baseline and progressing to more advanced time-series models, in order to identify the most suitable method for retail demand forecasting.

Rather than selecting a single “best” model, the project emphasizes **model comparison, trade-offs, and analytical judgment**, reflecting how forecasting decisions are made in real business environments.

---

## 🎯 Objectives
- Build a clean and reliable time-series forecasting pipeline  
- Establish a naïve baseline forecast for benchmarking  
- Implement and compare advanced forecasting models  
- Evaluate model performance using MAE and MAPE  
- Communicate results using clear visualizations and business-oriented insights  

---

## 🛠️ Tools & Skills Used
- **Python**  
- **Pandas & NumPy** for data manipulation  
- **Matplotlib** for data visualization  
- **Statsmodels** (Exponential Smoothing / ETS)  
- **Prophet** for business-focused forecasting  
- **Excel** for validation and presentation  

---

## 🔍 Data Understanding
**Dataset:** Walmart Store Sales Forecasting (Kaggle)  
**Granularity:** Weekly sales  
**Scope:** Store 1 – Department 1  

**Key fields:**
- Date  
- Weekly_Sales  
- Store  
- Department  
- IsHoliday  

**Quality checks performed:**
- Verified weekly date continuity  
- Checked for missing or null values  
- Confirmed numeric data types  
- Visual inspection for outliers and seasonal patterns  

---

## 🧹 Data Cleaning & Preparation
- Converted date column to datetime format  
- Filtered a single store and department to isolate one time series  
- Sorted observations chronologically  
- Set date as the time-series index  
- Split data into training and test sets using a time-based approach  

---

## 📊 Exploratory Analysis (EDA)
Initial visualization revealed:
- Strong **annual seasonality**, driven by holidays  
- Stable baseline demand during non-holiday weeks  
- Sharp sales spikes during peak retail periods  
- No clear long-term upward or downward trend  

These observations guided the selection of seasonality-aware forecasting models.

---

## 🏗️ Methodology / Pipeline
1. Data loading and cleaning  
2. Time-series preparation  
3. Train–test split (last 12 weeks as test set)  
4. Baseline forecast using a 4-week moving average  
5. Exponential Smoothing (ETS) model  
6. Prophet model  
7. Model evaluation using MAE and MAPE  
8. Visual comparison of forecasts  
9. Model interpretation and selection  

---

## 🤖 Models & Algorithms

### Baseline — 4-Week Moving Average
A naïve benchmark representing recent average demand. Used to establish a minimum performance threshold.

### Exponential Smoothing (ETS)
- Additive trend  
- Additive seasonality  
- Seasonal period set to 52 weeks  
- Well-suited for structured retail time series  

### Prophet
- Additive trend and seasonality  
- Business-oriented forecasting framework  
- Strong interpretability and robustness  
- Handles trend changes smoothly  

---

## 📈 Model Performance Comparison

| Model | MAE | MAPE (%) |
|---|---|---|
| Baseline (4W MA) | ~3,620 | ~16.1 |
| ETS | ~1,707 | ~7.41 |
| Prophet | ~1,703 | ~8.55 |

---

## 🔑 Key Findings
- The baseline forecast provided a reasonable benchmark but failed to capture trend and seasonality  
- ETS achieved the **best overall accuracy**, with the lowest MAE and MAPE  
- Prophet delivered **comparable performance**, with slightly higher MAPE but stronger interpretability  
- Both ETS and Prophet significantly outperformed the baseline  
- Model selection depends on the trade-off between **accuracy** and **business interpretability**  

---

## 📝 Conclusion
This project demonstrates a structured approach to sales forecasting by comparing multiple models rather than relying on a single technique. While Exponential Smoothing achieved the best quantitative performance, Prophet proved to be a strong alternative due to its clarity and business-oriented design.

Presenting both models reflects a realistic decision-making process commonly used in data teams, where analytical rigor and stakeholder needs must be balanced.

---

## 🚀 Next Steps
- Extend forecasting to multiple stores and departments  
- Incorporate explicit holiday and promotional features  
- Explore SARIMA or regression-based forecasting approaches  
- Automate forecast generation for ongoing monitoring  

---

## 📂 Related Files
- 📓 **Notebook:** `Sales_Forecast_Walmart.ipynb`  
- 📁 **Dataset:** Walmart Store Sales Forecasting ([Kaggle](https://www.kaggle.com/datasets/micgonzalez/walmart-store-sales-forecasting))  
- 📊 **Visualizations:** Included in notebook outputs  
