# Empowering New York: Leveraging Surplus Renewable Energy for Community Benefits

A data-driven analysis of New York City's electricity consumption and renewable energy production patterns, with a proposed credit refund system to redistribute surplus electricity benefits to local communities.

---

## 📋 Project Overview

This project addresses the dual challenge of:
1. Rising energy demand from AI-driven data centers
2. Energy supply imbalance from fossil fuel phase-out and renewable energy adoption

By analyzing NYC's power consumption and production data (2021-2023), this study develops a **credit refund system** that redistributes surplus electricity benefits to residents based on consumption patterns and population ratios.

---

## 🎯 Key Objectives

- Analyze electricity consumption patterns across NYC's five boroughs
- Identify correlations between weather variables and energy usage
- Quantify surplus electricity from renewable sources
- Design an equitable credit distribution algorithm
- Build predictive models for surplus power forecasting

---

## 📊 Key Findings

- **Temperature** is the strongest predictor of electricity consumption (Mutual Information: 0.421)
- Average monthly surplus power: **~10,093 Million KWh**
- Predictive model achieves **R² = 0.870** (Random Forest Regression)
- Credit refunds range from **$910.27 (Queens)** to **$4,938.59 (Bronx)** per person

---

## 🛠️ Tech Stack

- **Python 3.8+**
- **Data Processing**: pandas, numpy
- **Machine Learning**: scikit-learn (Random Forest, KNN, Linear Regression)
- **Visualization**: matplotlib, seaborn, plotly
- **Statistical Analysis**: scipy, statsmodels

---

## 📁 Data Sources

1. **NYC Open Data Portal** - Borough-level electricity consumption
2. **Energy Information Administration (EIA)** - Power generation data
3. **NOAA** - Weather data (temperature, precipitation, wind speed)

*Note: Due to file size, raw data is not included in this repository. See `data/README.md` for download instructions.*

---

## 🚀 Getting Started

### Installation
```bash
# Clone the repository
git clone https://github.com/yourusername/nyc-surplus-energy-analysis.git
cd nyc-surplus-energy-analysis

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Register Jupyter kernel
python -m ipykernel install --user --name=venv --display-name="Python (venv)"

# Launch Jupyter Notebook
jupyter notebook
Project Workflow
Follow these notebooks in sequence to reproduce the analysis:
Phase 1: Data Collection & Preparation
01_data_collection.ipynb

Download electricity consumption data from NYC Open Data Portal
Retrieve power generation data from EIA
Collect weather data from NOAA
Organize raw data into data/raw/ directory
Verify data integrity and completeness

02_data_preprocessing.ipynb

Handle missing values using KNN imputation and regression models
Remove outliers with Isolation Forest algorithm and IQR method
Normalize variables using StandardScaler
Aggregate weather data to monthly intervals
Merge datasets on temporal and regional keys
Save cleaned data to data/processed/

Phase 2: Exploratory Data Analysis
03_eda_consumption.ipynb

Analyze electricity consumption patterns by borough (2021-2023)
Visualize seasonal trends and monthly variations
Calculate correlation between weather variables and consumption
Perform Pearson and Spearman correlation analysis
Calculate Mutual Information scores
Generate visualizations (Figure 1-7)

04_eda_generation.ipynb

Analyze power generation by source (hydroelectric, wind, solar)
Examine seasonal patterns in renewable energy production
Correlate weather conditions with generation capacity
Visualize monthly generation trends
Generate visualizations (Figure 8-12)

Phase 3: Surplus Analysis & Modeling
05_surplus_analysis.ipynb

Calculate monthly surplus electricity (Production - Consumption)
Identify seasonal surplus patterns
Analyze regional variations in surplus distribution
Quantify surplus power statistics
Generate visualizations (Figure 13-14)

06_modeling.ipynb

Build predictive models (Random Forest, KNN, Linear Regression)
Train models on historical surplus data
Evaluate model performance (MAE, RMSE, R²)
Compare actual vs predicted surplus power
Perform residual analysis
Generate visualizations (Figure 15-17)

Phase 4: Credit System Implementation
07_credit_system.ipynb

Design credit refund algorithm based on:

Borough consumption ratios
Population distribution
Surplus electricity availability


Calculate per capita credit amounts by borough
Simulate economic impact on residents
Visualize credit distribution
Generate visualizations (Figure 18-19)


📈 Project Structure
nyc-surplus-energy-analysis/
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   ├── raw/                    # Original data files
│   ├── processed/              # Cleaned datasets
│   └── README.md              # Data sources documentation
├── notebooks/
│   ├── 01_data_collection.ipynb
│   ├── 02_data_preprocessing.ipynb
│   ├── 03_eda_consumption.ipynb
│   ├── 04_eda_generation.ipynb
│   ├── 05_surplus_analysis.ipynb
│   ├── 06_modeling.ipynb
│   └── 07_credit_system.ipynb
├── src/
│   ├── data_loader.py         # Data loading utilities
│   ├── preprocessing.py       # Preprocessing functions
│   ├── visualization.py       # Plotting functions
│   └── models.py              # ML model implementations
├── results/
│   ├── figures/               # Generated plots
│   └── models/                # Saved model files
└── docs/
    └── original_paper.pdf     # Research paper

🔬 Methodology
Data Preprocessing

Missing Values: KNN imputation, time interpolation, regression models
Outliers: Isolation Forest algorithm, IQR method
Normalization: StandardScaler for feature scaling

Feature Engineering

Weather variables: TAVG (temperature), PRCP (precipitation), AWND (wind speed)
Temporal features: Month, season, year
Regional features: Borough-specific consumption patterns

Machine Learning Models

Random Forest Regression: Primary model (R² = 0.870)
K-Nearest Neighbors: Regional pattern analysis
Linear Regression: Baseline comparisons

Credit Calculation Formula
Credit per person = (Surplus Energy × Borough Consumption Share × Electricity Price) / Borough Population

📊 Results Summary
MetricValueAverage Monthly Surplus10,093 Million KWhModel R² Score0.870Mean Absolute Error (MAE)28.5 Million KWhRoot Mean Squared Error (RMSE)38.8 Million KWhSurplus Range8,500 - 12,500 Million KWh
Credit Distribution by Borough
BoroughCredit per PersonBronx$4,938.59Manhattan$4,761.30Brooklyn-Queens$910.27Staten Island-

🔮 Future Improvements

Incorporate real-time data streaming
Add XGBoost and LightGBM models for improved predictions
Include economic activity indicators
Develop interactive dashboard using Streamlit or Dash
Expand analysis to other major US cities


📝 Citation
If you use this work, please cite:
Ann, C. (2024). Empowering New York: Leveraging Surplus Renewable Energy 
for Community Benefits. GitHub Repository.
https://github.com/yourusername/nyc-surplus-energy-analysis


🙏 Acknowledgments

NYC Open Data Portal for providing comprehensive electricity consumption data
Energy Information Administration (EIA) for power generation statistics
National Oceanic and Atmospheric Administration (NOAA) for weather data


This project demonstrates end-to-end data science workflow: from data collection and preprocessing to modeling and practical solution implementation for sustainable urban energy management.