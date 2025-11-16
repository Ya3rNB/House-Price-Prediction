# House-Price-Prediction
A complete data science workflow (Data Cleaning, EDA, and Feature Engineering) to predict house prices using data from Divar.ir advertisements.

# 🏠 Tehran House Price Prediction (from Divar Data)

This project is an end-to-end data science workflow designed to predict house prices in Tehran, based on advertisement data scraped from Divar.ir.

The primary focus is not on a specific algorithm, but on the complete methodology required to handle **messy, real-world data** and transform it into a predictive asset.

* **Original Dataset:** [Divar House Advertisement Dataset on Kaggle](https://www.kaggle.com/datasets/raoofiali/divar-house-adv-dataset)

---

##  CHALLENGE: Working with "Dirty" Real-World Data

Data scraped from public classifieds sites like Divar is notoriously "dirty" and unstructured. The main challenge of this project was intensive data cleaning and feature engineering to convert inconsistent user entries and raw Persian text into a machine-readable format.

---

## 🛠️ Project Workflow

My methodology followed these key data science stages:

### 1. Data Cleaning & Preprocessing
This was the most critical phase, involving:
* **Handling Unstructured Text:** Cleaning and standardizing Persian text data (e.g., neighborhood names, descriptions).
* **Type Conversion:** Converting columns like `Price` and `Area` from string formats (e.g., " متر", "توافقی") into clean numerical values.
* **Missing Value Imputation:** Developing strategies for a large number of missing values (e.g., `Parking`, `Rooms`, `Elevator`), often imputing based on logical rules (e.g., a 20-meter apartment likely doesn't have 3 rooms).

### 2. Exploratory Data Analysis (EDA)
After cleaning the data, I analyzed it to find patterns:
* **Target Variable Analysis:** The `Price` column was heavily skewed. I applied a **log-transformation** to normalize its distribution, which is critical for accurate regression.
* **Geospatial Analysis:** Visualized house prices across different neighborhoods (`Mahalleh`) in Tehran to identify the most expensive areas.
* **Correlation:** Analyzed how features like `Area`, `Rooms`, and `Parking` correlate with the final `Price`.

### 3. Feature Engineering
New features were created from existing data to improve the model's predictive power:
* **Categorical Encoding:** Converted high-cardinality categorical features (like `Neighborhood`) into numerical representations using techniques like Target Encoding or Hashing.
* **Feature Creation:** Engineered new features, such as `Price_per_Meter` (for analysis) and `Building_Age`.
* **Text Feature Extraction:** Explored using the `Description` text by extracting keywords or using TF-IDF to capture information not present in other columns.

### 4. Model Training & Evaluation
* **Data Splitting:** The data was split into training and validation sets to evaluate the model's performance on unseen data and prevent overfitting.
* **Model Training:** A robust regression model was trained on the fully processed and engineered feature set.
* **Performance Metric:** The model was evaluated using **Root Mean Squared Logarithmic Error (RMSLE)** to accurately measure the percentage error in price predictions.

---


