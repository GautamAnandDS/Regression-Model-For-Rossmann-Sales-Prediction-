# Rossmann Sales Prediction Project

## 📊 Project Overview
This project focuses on building a predictive model to forecast daily sales for Rossmann stores. The goal is to assist store managers in making data-driven decisions by providing accurate sales forecasts up to six weeks in advance. Using historical sales data and additional store-specific information, we developed a robust machine learning model to predict sales.

## 🔥 Problem Statement
Rossmann operates over 3,000 drug stores across 7 European countries. Store managers are currently responsible for predicting their daily sales, influenced by factors such as:
- Promotions
- Store types and assortments
- Competition distance
- Weekdays vs. weekends
- State and school holidays

Given the complexity of these variables, our task was to build a model using historical data from 1,115 Rossmann stores to forecast future sales.

## 📦 Dataset Description
The project utilizes two key datasets:
1. **Rossmann Data:** Contains daily sales data for each store, including promotions, holidays, and customer information.
2. **Store Data:** Provides additional store-specific information such as store type, assortment type, competition details, and promotional intervals.

These datasets were merged on the `Store` column to create a comprehensive training set.

## 🔬 Approach
Our approach involved several critical steps:
1. **Data Exploration and Cleaning:**
   - Handled missing values using imputation strategies.
   - Resolved discrepancies in categorical values.
   - Converted data types for efficient processing.
2. **Data Visualization:**
   - Visualized sales trends by day, month, and year.
   - Explored relationships between promotions, holidays, and sales.
3. **Feature Engineering:**
   - Created new features like year, month, week of year, and day of the week.
   - Engineered lag features to capture historical sales patterns.
   - Added interaction terms between promotions and store types.
4. **Model Selection and Tuning:**
   - Experimented with various regression models (Linear Regression, Random Forest, XGBoost).
   - Tuned hyperparameters using Grid Search to optimize model performance.

## 🚀 Model Deployment
We used the **XGBoost** algorithm due to its superior performance on structured data. The final tuned model was saved and loaded using **joblib** for easy deployment:

```python
# Save the tuned XGBoost model using joblib
import joblib
joblib.dump(XGB_tuned, 'XGB_tuned.joblib')

print("XGBoost model saved successfully as 'XGB_tuned.joblib'")

# Load the saved XGBoost model
XGB_tuned_loaded = joblib.load('XGB_tuned.joblib')

# Make predictions
y_pred = XGB_tuned_loaded.predict(X_test.iloc[[2]])
```

## 📈 Evaluation Metrics
We evaluated model performance using:
- **Root Mean Squared Error (RMSE):** Measures the average error between predicted and actual sales.
- **Mean Absolute Error (MAE):** Calculates the absolute differences between predictions and true values.
- **R-squared (R²):** Assesses the proportion of variance in sales explained by the model.

## 🌟 Conclusion
The Rossmann Sales Prediction model successfully forecasts daily sales with high accuracy, providing store managers with reliable data to plan promotions, manage inventory, and optimize operations. Future improvements could include incorporating external data like weather patterns, economic indicators, and customer reviews.

## 📚 How to Run
1. Clone the repository:
```bash
git clone <repo_url>
```
2. Install dependencies:
```bash
pip install -r requirements.txt
```
3. Run the Jupyter Notebook or Python script to train the model:
```bash
jupyter notebook Rossmann_Sales_Prediction.ipynb
```
4. Use the saved model for predictions:
```python
XGB_tuned_loaded.predict(new_data)
```

## 📧 Contact
For any questions or collaboration, feel free to reach out!

---

Let's build data-driven solutions together! 🚀

