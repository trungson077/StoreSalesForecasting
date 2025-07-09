# Store Sales Time Series Forecasting

## 🎯 Project Overview

**Challenge**: Predict sales for product families at store-day level using historical data  
**Result**: RMSLE 0.3894 using Random Forest ensemble  
**Dataset**: [Kaggle Store Sales Competition](https://www.kaggle.com/competitions/store-sales-time-series-forecasting)

## 📁 Repository Structure

```
├── store-sales-time-series-forecasting/     # Original dataset
├── 01_Exploratory_Data_Analysis.ipynb       # EDA and insights
├── 02_ML_Modeling.ipynb                     # Feature engineering & modeling
├── Technical_Report.md                      # Detailed analysis report
├── README.md                                # This file
└── improved_submission.csv                  # Final predictions
```

## 🚀 Quick Start

1. **Install Requirements**
```bash
pip install pandas numpy scikit-learn lightgbm xgboost matplotlib seaborn plotly
```

2. **Run Analysis**
```bash
# Exploratory Data Analysis (~10 mins)
jupyter notebook 01_Exploratory_Data_Analysis.ipynb

# Machine Learning Pipeline (~30 mins)
jupyter notebook 02_ML_Modeling.ipynb
```

## 📊 Key Results

### Model Performance
| Model | RMSLE | Performance |
|-------|-------|-------------|
| **Random Forest** | **0.3894** | Best ✅ |
| LightGBM | 0.9041 | Good |
| XGBoost | 1.0385 | Moderate |

### Data Overview
- **3M+ training records** (2013-2017)
- **54 stores, 33 product families**
- **External factors**: oil prices, holidays, promotions
- **72 engineered features**

### Top Features (Random Forest)
1. `sales_mean_7d` (89%) - Recent sales trend
2. `sales_lag_14` (3.9%) - Two weeks ago sales
3. `sales_lag_7` (3.6%) - One week ago sales
4. `transactions` (1.1%) - Store activity

## 🔧 Technical Approach

**Feature Engineering**: 72 features including lag features, rolling averages, temporal patterns, and external factors

**Models Tested**: Random Forest, LightGBM, XGBoost with time series validation

**Final Solution**: Ensemble (Random Forest 70% + LightGBM 30%)

**Validation**: Time series cross-validation with data leakage prevention

## 💡 Business Insights

- **Recent sales patterns** are the strongest predictor (95%+ importance)
- **Store transaction volume** is key leading indicator
- **Weekend vs weekday** demand requires different strategies
- **25% zero sales** records need special handling

## 🎯 Key Features

✅ **Proper time series methodology** (no data leakage)  
✅ **Comprehensive EDA** that informs ML approach  
✅ **Advanced feature engineering** (lag, rolling, seasonal)  
✅ **Multiple model comparison** with ensemble approach  
✅ **Business-ready insights** for operations  
✅ **Full reproducibility** (fixed random seeds)  



**Note**: All code includes fixed random seeds (42) for full reproducibility. Complete technical analysis available in `Technical_Report.pdf`. 
