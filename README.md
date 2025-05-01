# 📈 Stock Price Prediction Using Machine Learning

This project applies multiple machine learning models to predict stock closing prices using historical data from U.S.-based stocks and ETFs. The goal is to evaluate and optimize various regression algorithms and identify the most effective model for forecasting stock price trends.

---

## 🗂️ Dataset Overview

- **Source**: [Kaggle – All US Stocks & ETFs Daily Prices](https://www.kaggle.com/)
- **Structure**:
  - `stocks/` folder: 1288 files loaded (32 skipped due to missing data)
  - `etfs/` folder: 1344 files loaded (no skipped files)
- **Features**:
  - `Open`, `High`, `Low`, `Close`, `Volume`

Each file contains daily historical data for one stock or ETF.

---

## 🎯 Project Objectives

- Predict stock closing prices using historical market data
- Compare the performance of five regression models
- Engineer new features to improve model accuracy
- Apply hyperparameter tuning for model optimization

---

## 🧠 Models Used

| Model              | Description                                             |
|-------------------|---------------------------------------------------------|
| Linear Regression | Baseline linear model                                   |
| Ridge Regression  | Regularized linear regression (L2 penalty)              |
| Decision Tree     | Rule-based non-linear model                             |
| Random Forest     | Ensemble of decision trees for better generalization    |
| XGBoost           | Gradient boosting model optimized for performance       |

---

## 🛠️ Feature Engineering

- **Datetime Features**: Extracted `hour`, `month`, `day of week`
- **Lag Features**: Previous day(s) closing prices to model trends
- **Volatility Features**: Rolling standard deviations for recent price movement

*NaN values introduced by these operations were removed to ensure data quality.*

---

## 📊 Model Performance

### Before Optimization

| Model             | RMSE    | R²     |
|------------------|---------|--------|
| Linear Regression | 0.2236  | 0.9490 |
| Ridge Regression  | 0.0265  | 0.9730 |
| Random Forest     | 0.0383  | 0.9610 |
| XGBoost           | 0.3401  | 0.6531 |
| Decision Tree     | 0.0049  | 0.9950 |

### After Optimization (GridSearchCV)

| Model             | RMSE    | R²     |
|------------------|---------|--------|
| Decision Tree     | 0.0036  | 0.9963 |
| Random Forest     | 0.0163  | 0.9834 |
| Ridge Regression  | 0.0265  | 0.9730 |
| Linear Regression | 0.0265  | 0.9730 |
| XGBoost           | 0.4485  | 0.5425 |

---

## 🔍 Key Insights

- **Decision Tree** was the top-performing model overall.
- **Random Forest** offered strong accuracy with robustness.
- **Linear & Ridge Regression** were consistent, but less flexible.
- **XGBoost** underperformed without deeper hyperparameter tuning.
- Feature engineering (especially lag/volatility features) significantly improved model accuracy.

---

## 🚀 Real-World Applications

- Automated trading systems  
- Portfolio risk assessment  
- Market trend forecasting  
- Comparative analysis of stocks vs ETFs

---

## 🔮 Future Enhancements

- Integrate LSTM or other deep learning models for time series forecasting
- Add technical indicators (e.g., RSI, MACD)
- Include external data (news sentiment, macroeconomic variables)
- Use rolling window validation for time-aware evaluation
- Develop a live prediction system using real-time data feeds

---

## ✅ Conclusion

This project shows that machine learning, especially tree-based models like Decision Trees and Random Forests, can effectively predict stock prices when combined with thoughtful feature engineering. The results provide a strong foundation for further research and development in financial prediction and automated decision-making.

---

## 📚 References

- [Scikit-learn Documentation](https://scikit-learn.org/stable/)
- [XGBoost Documentation](https://xgboost.readthedocs.io/en/latest/)
- [Kaggle Dataset](https://www.kaggle.com/)

---
