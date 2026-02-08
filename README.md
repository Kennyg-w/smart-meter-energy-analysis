# Smart Meter Energy Analytics & Forecasting

## 📊 Project Overview
Developed an end-to-end data science pipeline to analyze 1.2M+ rows of London smart meter data. Built a system to identify consumption anomalies and forecast future demand.

## 🛠️ Technical Achievements
- **Advanced SQL:** Implemented DuckDB window functions (RANK, Partition) to identify household peak usage tiers.
- **Machine Learning:** Deployed an XGBoost Regressor achieving a 40% performance improvement over linear baselines.
- **Anomaly Detection:** Engineered a dynamic 24-hour rolling mean/std threshold system to trigger actionable maintenance alerts.
- **Time-Series Forecasting:** Utilized Facebook Prophet to model complex residential seasonality and 7-day future demand.
- **Production Pipeline:** Wrapped preprocessing and modeling into a Scikit-Learn Pipeline for reproducible deployment.

## 📈 Business Impact
- Identified specific high-volatility households requiring revenue assurance audits.
- Quantified the 2-hour "Weekend Shift" in peak demand, providing data for grid load optimization.

## 🐍 Environment
- Python 3.11 (Conda)
- XGBoost, Prophet, Scikit-Learn, DuckDB
