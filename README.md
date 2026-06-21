# 🏠 House Price Prediction
**Internship Project — Week 1**

A machine learning regression project that predicts house prices based on property features such as area, number of rooms, location access, and amenities. Built using Python, Pandas, Scikit-learn, Matplotlib, and Seaborn.

---

## 📁 Project Structure

```
HousePricePrediction_[YourName]/
│
├── analysis.ipynb                   # Complete Jupyter Notebook (all 5 tasks)
├── Housing.csv                      # Dataset used for training & testing
├── summary.docx                     # 1-page written summary of findings
├── README.md                        # This file
│
└── charts/
    ├── chart1_price_distribution.png    # Histogram of house prices
    ├── chart2_correlation_heatmap.png   # Feature correlation heatmap
    └── chart3_actual_vs_predicted.png   # Actual vs Predicted prices (both models)
```

---

## 📦 Dataset

- **Source:** [Housing Prices Dataset — Kaggle (yasserh)](https://www.kaggle.com/datasets/yasserh/housing-prices-dataset)
- **File:** `Housing.csv`
- **Rows:** 545 | **Columns:** 13
- **Target:** `price` (house price in Indian Rupees)

### Features

| Column | Type | Description |
|--------|------|-------------|
| `price` | Numeric | 🎯 Target — house price (₹) |
| `area` | Numeric | Property size in square feet |
| `bedrooms` | Numeric | Number of bedrooms |
| `bathrooms` | Numeric | Number of bathrooms |
| `stories` | Numeric | Number of floors |
| `parking` | Numeric | Number of parking spaces |
| `mainroad` | Categorical | Connected to main road? (yes/no) |
| `guestroom` | Categorical | Has guest room? (yes/no) |
| `basement` | Categorical | Has basement? (yes/no) |
| `hotwaterheating` | Categorical | Has hot water heating? (yes/no) |
| `airconditioning` | Categorical | Has air conditioning? (yes/no) |
| `prefarea` | Categorical | In a preferred area? (yes/no) |
| `furnishingstatus` | Categorical | furnished / semi-furnished / unfurnished |

---

## ✅ Tasks Completed

### Task 1 — Data Loading & Exploration
- Loaded CSV with Pandas
- Displayed first 10 rows, shape, and column types
- Identified target (`price`) and feature columns
- Checked for missing values

### Task 2 — Data Cleaning
- Handled missing values (median for numeric, mode for categorical)
- Removed duplicate rows
- Applied **one-hot encoding** to all 7 categorical columns
- Converted boolean columns to integer (0/1)

### Task 3 — Model Building
- 80/20 train-test split (`random_state=42`)
- Trained **Linear Regression** and **Random Forest Regressor**
- Evaluated both models using MAE, RMSE, and R²

### Task 4 — Visualization
- **Chart 1:** Histogram of house price distribution
- **Chart 2:** Correlation heatmap (numeric features vs price)
- **Chart 3:** Actual vs Predicted prices — side-by-side scatter plot for both models

### Task 5 — Insights & Summary
- Written analysis inside the notebook covering key findings, model accuracy, surprises, and a business recommendation

---

## 📊 Model Results

| Metric | Linear Regression | Random Forest |
|--------|:-----------------:|:-------------:|
| MAE | ₹3,55,305 | ₹4,61,389 |
| RMSE | ₹4,47,404 | ₹5,98,911 |
| **R² Score** | **0.9550 ✅** | 0.9194 |

> **Linear Regression outperformed Random Forest**, suggesting the price-feature relationship in this dataset is largely linear.

---

## 🔍 Key Findings

- **Area** is by far the most dominant predictor of house price (90%+ feature importance in Random Forest)
- **Bathrooms**, **stories**, and **bedrooms** are the next most influential numeric features
- **Air conditioning**, **preferred area**, and **furnishing status** add a meaningful price premium
- The model explains **~95.5% of price variance**, making it highly reliable for estimation

**Business Recommendation:** Prioritize property area and bathroom count as primary pricing levers. Air conditioning and preferred-area listings can command a 10–15% premium and should be highlighted in marketing materials.

---

## 🛠️ Setup & Running the Notebook

### Prerequisites
Make sure you have Python 3.x installed, then install the required libraries:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

### Run the Notebook

```bash
# Unzip the project folder, then:
cd HousePricePrediction_[YourName]
jupyter notebook analysis.ipynb
```

Run all cells top to bottom (`Kernel → Restart & Run All`).

> **Note:** `Housing.csv` must be in the same directory as `analysis.ipynb`. The `charts/` folder will be created automatically when the notebook runs.

---

## 📚 Libraries Used

| Library | Version | Purpose |
|---------|---------|---------|
| `pandas` | ≥1.3 | Data loading and cleaning |
| `numpy` | ≥1.21 | Numerical operations |
| `scikit-learn` | ≥1.0 | ML models and evaluation metrics |
| `matplotlib` | ≥3.4 | Base plotting |
| `seaborn` | ≥0.11 | Statistical visualizations |
| `jupyter` | ≥1.0 | Interactive notebook environment |

---

## 📈 Results Summary

The project successfully demonstrated that house prices can be predicted with high accuracy using simple tabular features. Linear Regression proved to be the better model on this dataset, achieving an R² of **0.955** — meaning property size, bathroom count, and stories together are strong enough signals for reliable price estimation without needing a complex ensemble model.

The Random Forest model, while slightly less accurate here, provided the added benefit of **feature importance scores**, which revealed that `area` alone accounts for over 90% of predictive power — a critical insight for any real estate pricing strategy.

---

## 🚀 Future Improvements

- Incorporate **geospatial data** (latitude/longitude, neighbourhood-level pricing) for richer location features
- Try **XGBoost** or **Gradient Boosting** for potentially better accuracy
- Add **cross-validation** (K-Fold) for more robust model evaluation
- Build an interactive **price estimation web app** using Streamlit or Flask
- Collect more data points to reduce model variance and improve generalizability# House_Price_Prediction
