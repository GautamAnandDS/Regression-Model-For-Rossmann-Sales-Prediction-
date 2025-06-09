# 📈 Rossmann Sales Prediction Project

![image](https://github.com/user-attachments/assets/1149d79a-5b26-4369-a247-104457f977ed)

## 📊 Project Overview

* Built a predictive model to **forecast daily sales** for Rossmann stores.
* Goal: Assist store managers in making **data-driven decisions** for up to **6 weeks in advance**.
* Utilized historical sales and store-specific data to develop a **robust ML model**.

---

## 🔥 Problem Statement

* Rossmann operates **3,000+ stores** across 7 European countries.
* Store managers manually predict sales affected by multiple factors such as:

  * Promotions
  * Store types and assortments
  * Competition distance
  * Weekdays vs. weekends
  * State and school holidays
* Objective: Build a **predictive model** using historical data from **1,115 stores**.

---

## 📦 Dataset Description

* Used two primary datasets:

  1. **Sales Data:** Daily sales, promotions, holidays, and customer information.
  2. **Store Data:** Details like store type, assortment, competition, and promotions.
* Datasets merged on the **`Store`** column to form a comprehensive training dataset.

---

## 🔬 Approach

### 1. Data Exploration and Cleaning

* Handled missing values using **imputation**.
* Fixed **inconsistent categorical values**.
* Optimized data types for **efficient processing**.

### 2. Data Visualization

* Analyzed **sales trends** across time periods.
* Explored relationships between **promotions, holidays**, and sales.

### 3. Feature Engineering

* Extracted time-based features: **year, month, week, day of week**.
* Created **lag features** to incorporate historical context.
* Engineered **interaction terms** (e.g., promotions × store type).

### 4. Model Selection and Tuning

* Tested models like **Linear Regression, Random Forest, and XGBoost**.
* Applied **Grid Search** for hyperparameter tuning.

---

## 🚀 Model Deployment

* Final model: **XGBoost** (best performance on structured/tabular data).
* Saved model using **joblib** for deployment:

```python
# Save model
import joblib
joblib.dump(XGB_tuned, 'XGB_tuned.joblib')

# Load model
XGB_tuned_loaded = joblib.load('XGB_tuned.joblib')

# Predict
y_pred = XGB_tuned_loaded.predict(X_test.iloc[[2]])
```

---

## 📈 Evaluation Metrics

* **RMSE:** Measures average prediction error.
* **MAE:** Calculates average absolute difference from true values.
* **R² Score:** Indicates how well the model explains variance in sales.
* **Tuned Final Model Evaluation Metrics**


  ![Screenshot 2025-06-09 231111](https://github.com/user-attachments/assets/5e6c2f59-decb-4d75-a6b2-6d1bce3c373a)


---

## 🌟 Conclusion

* Developed a **high-accuracy model** for daily sales forecasting.
* Enables store managers to:

  * Plan promotions
  * Manage inventory
  * Optimize store operations
* Future scope:

  * Integrate **weather, economic data, and reviews** for even better accuracy.

---

## 📚 How to Run

1. **Clone the repo:**

   ```bash
   git clone <repo_url>
   ```

2. **Install required packages:**

   ```bash
   pip install -r requirements.txt
   ```

3. **Run the model training notebook:**

   ```bash
   jupyter notebook Rossmann_Sales_Prediction.ipynb
   ```

4. **Use the trained model for predictions:**

   ```python
   XGB_tuned_loaded.predict(new_data)
   ```

---

## 📧 Contact

* For questions, feedback, or collaboration, feel free to reach out.
* Let’s build **data-driven solutions** together! 🚀

---

