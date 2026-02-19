# 🏠 House Price Prediction — Linear Regression

A supervised Machine Learning project that predicts California house prices using **Linear Regression**. Built with Python in Google Colab, this project covers the full ML pipeline — from data loading and exploration to model training, evaluation, and feature engineering.

---

## 📌 Project Overview

| Item | Details |
|------|---------|
| **Type** | Supervised Machine Learning — Regression |
| **Algorithm** | Linear Regression |
| **Dataset** | California Housing (built into `sklearn`) |
| **Target Variable** | House Price (in $100,000s) |
| **Features** | 8 (MedInc, HouseAge, AveRooms, AveBedrms, Population, AveOccup, Latitude, Longitude) |
| **Dataset Size** | 20,640 rows × 9 columns |
| **Platform** | Google Colab |

---

## 🧰 Tech Stack

- **Python 3**
- **NumPy** — numerical computations
- **Pandas** — data manipulation
- **Matplotlib** — data visualization
- **Scikit-learn** — ML model, dataset, and metrics

---

## 📁 Project Structure

```
house-price-prediction/
│
├── Project_2.ipynb                  # Main Jupyter Notebook
├── house_price_predictions.csv      # Model output (Actual vs Predicted)
└── README.md                        # Project documentation
```

---

## 🔄 ML Pipeline (Step-by-Step)

### Step 1 — Import Libraries
```python
import numpy as np, pandas as pd, matplotlib.pyplot as plt
from sklearn.datasets import fetch_california_housing
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, r2_score
```

### Step 2 — Load Dataset
Uses sklearn's built-in **California Housing** dataset — no download or URL required.

### Step 3 — Data Understanding
- Shape: `(20640, 9)` — 20,640 records, 9 columns
- All features are `float64`, zero null values

### Step 4 — Check Missing Values
No missing values found across all 9 columns.

### Step 5 — Feature / Target Split
```python
X = df.drop("Price", axis=1)   # 8 input features
y = df["Price"]                 # Target: house price
```

### Step 6 — Train-Test Split
```python
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)
# Training: 16,512 samples | Testing: 4,128 samples
```

### Step 7 — Train the Model
```python
model = LinearRegression()
model.fit(X_train, y_train)
```

### Step 8 — Make Predictions
```python
y_pred = model.predict(X_test)
```

### Step 9 — Evaluate the Model
| Metric | Score |
|--------|-------|
| **RMSE** | 0.7456 |
| **R² Score** | 0.5758 |

> **RMSE** — average prediction error (lower = better)  
> **R²** — how well the model explains variance in the data (closer to 1 = better)

### Step 10 — Visualization: Actual vs Predicted
Scatter plot showing predicted prices against actual prices. Dots close to the diagonal line indicate better predictions.

### Step 11 — Residual Plot (Error Analysis)
Scatter plot of residuals (`actual − predicted`) vs predicted values. A good model shows residuals randomly scattered around zero.

### Step 12 — Feature Importance (Coefficients)
| Feature | Coefficient | Impact |
|---------|------------|--------|
| AveBedrms | +0.783 | ↑ Increases price |
| MedInc | +0.449 | ↑ Increases price |
| HouseAge | +0.010 | ↑ Slight increase |
| Population | −0.000002 | ↓ Negligible |
| AveOccup | −0.004 | ↓ Slight decrease |
| AveRooms | −0.123 | ↓ Decreases price |
| Latitude | −0.420 | ↓ Decreases price |
| Longitude | −0.434 | ↓ Decreases price |

### Step 13 — Feature Engineering (Log Transform)
Applied `np.log1p()` on the target variable to reduce skewness.

| Metric | Before Log | After Log |
|--------|-----------|----------|
| RMSE | 0.7456 | **0.2244** |
| R² Score | 0.5758 | **0.6006** |

### Step 14 — Save Output
Predictions saved to `house_price_predictions.csv` with `Actual` and `Predicted` columns.

---

## 📊 Key Results

- The baseline Linear Regression model achieved **R² = 0.576**, meaning it explains ~57.6% of price variance.
- After applying a **log transformation** on the target, the model improved to **R² = 0.601**.
- The most influential feature is **AveBedrms** (positive) and **Longitude** (negative).

---

## 🚀 How to Run

1. Open `Project_2.ipynb` in [Google Colab](https://colab.research.google.com/) or Jupyter Notebook
2. Run all cells top to bottom
3. No dataset download needed — uses `sklearn.datasets.fetch_california_housing`

**Install dependencies (if running locally):**
```bash
pip install numpy pandas matplotlib scikit-learn
```

---

## 🧠 Concepts Demonstrated

- Supervised learning with Linear Regression
- Train-test split strategy (`80/20`)
- Regression metrics: RMSE and R² Score
- Feature importance via model coefficients
- Feature engineering with log transformation
- Visualization: Actual vs Predicted & Residual plots
- Saving predictions to CSV

---

## 🙋 Author

**Your Name**  
[GitHub](https://github.com/DeveloperSomnath) • [LinkedIn](https://www.linkedin.com/in/somnath-das-02527a26b/)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
