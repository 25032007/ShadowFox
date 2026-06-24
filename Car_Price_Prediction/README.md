# 🚗 Car Selling Price Prediction
### ShadowFox AIML Internship — Intermediate Task

![Python](https://img.shields.io/badge/Python-3.11-blue?style=flat&logo=python)
![Sklearn](https://img.shields.io/badge/Scikit--Learn-ML-orange?style=flat&logo=scikit-learn)
![RandomForest](https://img.shields.io/badge/Random%20Forest-R²%200.96-brightgreen?style=flat)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat)

> A machine learning project that predicts the **selling price of used cars** based on features like showroom price, kilometers driven, fuel type, age, and more. Built as part of the **ShadowFox AIML Internship** program.

---

## 📌 Problem Statement

When selling a used car, how do you know what price to ask?

This project builds an ML model that takes in details about a car and predicts its **approximate selling price in lakhs (₹)**. The system can help both buyers and sellers make informed decisions about fair car pricing.

This is a **supervised regression problem** — we train on historical car sale data and predict prices for unseen cars.

---

## 📊 Dataset

| Property | Details |
|----------|---------|
| **File** | `car data.csv` |
| **Rows** | 301 cars |
| **Columns** | 8 (7 features + 1 target) |
| **Target** | `Selling_Price` — Car selling price in ₹ Lakhs |
| **Missing Values** | None |

### 🔑 Features Used

| Column | Description | Type |
|--------|-------------|------|
| `Present_Price` | Current showroom price of the car (₹ Lakhs) | Numerical |
| `Kms_Driven` | Total kilometers driven | Numerical |
| `Fuel_Type` | Type of fuel — Petrol / Diesel / CNG | Categorical |
| `Seller_Type` | Dealer or Individual seller | Categorical |
| `Transmission` | Manual or Automatic | Categorical |
| `Owner` | Number of previous owners | Numerical |
| `Car_Age` | Age of car in years (derived from Year column) | Numerical |
| **`Selling_Price`** | **Selling price in ₹ Lakhs — TARGET** | Numerical |

---

## ⚙️ Data Preprocessing

- **Feature Engineering:** Created `Car_Age` column from the `Year` column (`Car_Age = Current Year - Year`)
- **Label Encoding:** Converted text columns (`Seller_Type`, `Transmission`) to numbers using `LabelEncoder`
- **No missing values** found in this dataset

---

## 🧠 ML Models Used

### 1. Linear Regression
A simple baseline model that draws the best straight line through the data.

### 2. Random Forest Regressor ✅ Best Model
An ensemble of 100 decision trees that vote together for a final prediction. Handles non-linear relationships much better than a straight line.

---

## 📈 Results

| Model | R² Score | RMSE | Verdict |
|-------|----------|------|---------|
| Linear Regression | 0.85 | ₹1.88 lakh | Good baseline |
| **Random Forest** | **0.96** | **₹0.96 lakh** | ✅ Best model |

> **R² Score** = How well the model explains price variation. 1.0 = perfect predictions.
> **RMSE** = Average error in predicted price. Lower is better.

### 🔍 Key Insights

- **`Present_Price`** (showroom price) is the **#1 most important feature** — higher showroom price = higher resale value
- **`Car_Age`** has strong negative effect — older car = lower selling price
- **`Kms_Driven`** also reduces price — more km driven = more wear = lower price
- Random Forest achieved **₹0.96 lakh average error** — less than 1 lakh off on average!
- Random Forest outperformed Linear Regression by **+11% in R² score**

---

## 🗂️ Project Structure

```
ShadowFox/
│
├── Car_Price_Prediction/
│   ├── car data.csv                   # Dataset
│   ├── car_price_prediction.ipynb     # Main Jupyter Notebook
│   └── README.md                      # This file
```

---

## ⚙️ How to Run

### Step 1 — Clone the repository
```bash
git clone https://github.com/25032007/ShadowFox.git
cd ShadowFox/Car_Price_Prediction
```

### Step 2 — Install required libraries
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### Step 3 — Open the notebook in VS Code
```bash
code .
# Open car_price_prediction.ipynb
# Click "Select Kernel" → choose Python 3
```

### Step 4 — Run all cells
Press `Shift + Enter` on each cell in order, or click **Run All** from the top menu.

---

## 📉 Visualisations

| Chart | What it shows |
|-------|--------------|
| Selling Price Histogram | How car prices are distributed |
| Showroom Price vs Selling Price | Higher showroom price = higher resale |
| KMs Driven vs Selling Price | More km = lower price trend |
| Car Age vs Selling Price | Older car = lower price trend |
| Owners vs Selling Price | More owners = lower price |
| Correlation Heatmap | Which features are most related to price |
| Actual vs Predicted (both models) | How close the model's guesses were |
| Feature Importance Bar Chart | Present_Price is the top predictor |

---

## 🔮 Predict Your Own Car Price

The notebook includes **Cell 14** where you can input any car's details and get an instant predicted selling price:

```python
new_car = pd.DataFrame([{
    'Present_Price': 6.5,   # showroom price in lakhs
    'Kms_Driven'  : 45000,  # km driven
    'Fuel_Type'   : 1,      # 1=Diesel
    'Seller_Type' : 0,      # 0=Dealer
    'Transmission': 0,      # 0=Manual
    'Owner'       : 0,      # no previous owners
    'Car_Age'     : 5       # 5 years old
}])
# Output: 🚗 Predicted Selling Price: ₹X.XX lakh
```

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.11 | Programming language |
| Pandas | Data loading and manipulation |
| NumPy | Numerical operations |
| Matplotlib & Seaborn | Data visualisation |
| Scikit-learn | ML models, encoding, evaluation |
| Jupyter Notebook | Interactive coding environment |
| VS Code | IDE |

---

## 🚀 What I Learned

- How to do **feature engineering** (creating Car_Age from Year)
- How to **encode categorical variables** (text → numbers) using LabelEncoder
- Difference between **Linear Regression and Random Forest**
- How to evaluate regression models using **R² Score and RMSE**
- How to identify **top predictive features** using feature importance
- How to build a **price prediction system** for real-world use

---

## 👤 Author

**Anjali Mulchandani**
ShadowFox AIML Intern
[LinkedIn](https://www.linkedin.com/in/anjali-mulchandani-a36829336/) • [GitHub](https://github.com/25032007)

---

*Built with ❤️ as part of the ShadowFox AIML Internship Program*