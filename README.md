# Car Price Prediction using Linear Regression 🚗💰

A comprehensive analysis and predictive modeling project focused on estimating the resale value of used cars using advanced statistical methods and machine learning.

## 📌 Project Overview

This project demonstrates a full data science workflow to predict used car prices. By analyzing a dataset of over 4,000 car entries, we developed a robust linear regression model that accounts for key features like brand, mileage, engine volume, and year of manufacture.

The project emphasizes rigorous data preprocessing, including handling missing values, identifying and removing outliers, and meeting the core assumptions of linear regression through feature engineering.

## 🛠️ Technologies & Libraries

- **Language**: Python 3.x
- **Data Manipulation**: `Pandas`, `NumPy`
- **Visualization**: `Matplotlib`, `Seaborn`
- **Machine Learning**: `Scikit-learn` (Linear Regression)

## 📊 Methodology

### 1. Data Cleaning & Preprocessing

- **Variable Selection**: Dropped high-cardinality features (like 'Model') to maintain model simplicity and avoid overfitting.
- **Handling Nulls**: Identified and removed records with missing 'Price' and 'EngineV' data to ensure data quality.
- **Outlier Treatment**: Implemented quantile-based filtering (99th percentile) for 'Price' and 'Mileage' to remove extreme values that distort statistical analysis.
- **Filtering**: Removed unrealistic engine volumes (> 6.5L).

### 2. Feature Engineering

- **Log Transformation**: Applied a logarithmic transformation to the target variable ('Price') to fix the non-linear relationship with features like 'Year' and 'Mileage', ensuring the model meets the assumption of homoscedasticity.
- **Categorical Encoding**: Utilized one-hot encoding (dummy variables) for categorical features like 'Brand', 'Body', and 'Engine Type', dropping one category per feature to avoid the dummy variable trap.

### 3. Model Training

- **Train-Test Split**: Divided the cleaned dataset into training (80%) and testing (20%) sets.
- **Feature Scaling**: Scaled inputs using `StandardScaler` to ensure all features contribute equally to the model coefficients.
- **Regression Analysis**: Trained a multiple linear regression model using `sklearn.linear_model`.

## 📈 Key Findings & Performance

- **Predictive Power**: The model achieves an **R-squared of ~0.77** on the training data, indicating that the chosen features explain a significant portion of the variance in car prices.
- **Feature Insights**: Brand prestige and vehicle age ('Year') emerged as the strongest predictors, with mileage showing a clear inverse relationship with price.
- **Evaluation**: Residual analysis confirmed that the errors are normally distributed and centered around zero, validating the model's appropriateness for this dataset.

## 🚀 How to Run

1. Ensure you have Python installed along with the required libraries:
   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn
   ```
2. Clone this repository.
3. Open `script.ipynb` in any Jupyter environment (JupyterLab, VS Code, etc.).
4. Ensure `real_life_example.csv` is in the same directory.
5. Run all cells to reproduce the analysis and model results.

---

_Created as part of the "Advanced Statistical Methods" practical example in Data Science._
