## ⚡ Spot Price Forecasting in the Australian National Electricity Market (NEM)
## 📌 Project Overview

This project develops an end-to-end spot price forecasting pipeline for the Australian National Electricity Market (NEM), with a strong focus on market behaviour, renewable impacts, and price risk rather than treating prices as a purely statistical time series.

The objective is not to replicate AEMO’s operational models, but to build a transparent, interpretable, and business-aligned forecasting framework that demonstrates how demand, rooftop solar, intermittent generation, weather, and ramping behaviour jointly shape wholesale electricity prices.

The project spans data engineering → exploratory analysis → feature engineering → machine learning forecasting → dashboarding, and is designed to be easily extended or adapted for real-world market analytics roles.

## 🎯 Business Questions Addressed

This project explicitly answers five core business questions:

#### What is happening to spot prices?
– Volatility, negative prices, extreme spikes, and intraday patterns

#### Why is it happening?
– Demand levels, net demand after solar, renewable availability, ramps, and time-of-day effects

#### When does price risk increase?
– Specific hours, demand ramp events, and low renewable availability periods

#### So what for the business?
– Implications for retailers, generators, risk managers, and planners

#### What should decision-makers do?
– Improve monitoring, hedging strategies, and short-term forecasting capability

## 📂 Data Sources

- AEMO market data
- Regional reference prices (RRP)
- Total demand
- Intermittent generation
- Rooftop PV estimates
- Weather data
- Temperature
- Wind speed

All data is aligned at 5-minute resolution, consistent with the NEM dispatch interval.

## 🧪 Methodology & Project Structure
#### Phase 1 — Data Preparation
- Data ingestion and alignment
- Missing value handling
- Creation of net demand after PV
- Validation and quality checks

#### Phase 2 — Exploratory Data Analysis (EDA)
- Spot price behaviour and volatility
- Demand vs price relationships
- Renewable and rooftop PV impacts 
- Time-of-day, weekday/weekend, and seasonal patterns
- Ramp analysis (demand and renewables)

The EDA phase focuses on understanding market mechanics before modelling.

#### Phase 3 — Feature Engineering

- Lagged prices (short, medium, long horizons)
- Lagged demand, net demand, and renewables
- Ramp features (absolute and directional)
- Time features (hour, day of week, month)
- Log transformation of prices for stability

#### Phase 4 — Forecasting Models
- Baseline persistence model
- Linear regression benchmark
- Tree-based models (Random Forest, XGBoost)
- Model comparison using RMSE
- Feature importance analysis for interpretability

XGBoost was selected as the best-performing model due to its ability to:
- Capture non-linear price behaviour
- Respond to ramps and demand stress
- Handle extreme price movements better than linear models

##### Phase 5 — Short-Term Forecasting

- 24-hour forward spot price forecast
- 5-minute resolution
- Recursive forecasting using latest known system state
- Forecast interpretation and validation logic

##### Phase 6 — Power BI Dashboards

Two dashboard levels were created:

- Executive View: High-level price trends and risk signals

- Analyst View: Drivers, errors, ramps, and forecast diagnostics

### 📊 Key Insights

- High prices are not driven by demand alone — time-of-day and renewable availability are critical.
- Rooftop solar significantly suppresses midday prices but increases evening price risk.
- Price volatility increases sharply during rapid demand ramps, even at moderate demand levels.
- Net demand after PV is a stronger price driver than total demand.
- Forecasting models must explicitly account for ramps and lag effects to avoid underestimating risk.

### 🛠️ Tech Stack

- Python: pandas, numpy, matplotlib, seaborn
- Machine Learning: scikit-learn, XGBoost
- Visualisation: Power BI
- Environment: Jupyter Notebooks
- Data Handling: CSV-based modular pipeline

### 📈 Outputs
- Clean, model-ready datasets
- 24-hour spot price forecasts (5-minute resolution)
- Power BI dashboard datasets (5-minute & hourly)
- Reproducible notebooks for EDA, feature engineering, and modelling

🚀 How This Project Can Be Extended

- Multi-region forecasting
- Probabilistic / quantile forecasts
-Incorporation of interconnector constraints
- Longer horizon forecasting (48–168 hours)
Integration with live market feeds

### 👋 Feedback & Collaboration

This project is part of my ongoing journey in energy analytics and electricity market modelling.
If you work in energy markets, analytics, or system operations and have suggestions or feedback, I’d love to hear from you.
