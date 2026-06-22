# 🏠 Boston House Price Prediction
### ShadowFox AIML Internship — Beginner Task

![Python](https://img.shields.io/badge/Python-3.11-blue?style=flat&logo=python)
![Sklearn](https://img.shields.io/badge/Scikit--Learn-ML-orange?style=flat&logo=scikit-learn)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat)

> A machine learning project that predicts house prices using regression models trained on the Boston Housing dataset. Built as part of the **ShadowFox AIML Internship** program.

---

## 📌 Problem Statement

Given a set of features about a house and its neighbourhood (crime rate, number of rooms, poverty level, etc.), can we accurately predict the **median house price**?

This is a **supervised regression problem** — we train a model on historical data and use it to predict prices for unseen houses.

---

## 📊 Dataset

| Property | Details |
|----------|---------|
| **File** | `HousingData.csv` |
| **Rows** | 506 houses |
| **Columns** | 14 (13 features + 1 target) |
| **Target** | `MEDV` — Median house price in $1000s |
| **Missing Values** | 120 (filled using column median) |

### 🔑 Features Used

| Column | Description | Type |
|--------|-------------|------|
| `CRIM` | Per capita crime rate by town | Numerical |
| `ZN` | Proportion of residential land zoned for large lots | Numerical |
| `INDUS` | Proportion of non-retail business acres per town | Numerical |
| `CHAS` | Charles River dummy variable (1 if bounds river) | Binary |
| `NOX` | Nitric oxide concentration (air pollution) | Numerical |
| `RM` | Average number of rooms per dwelling | Numerical |
| `AGE` | Proportion of owner-occupied units built before 1940 | Numerical |
| `DIS` | Weighted distance to employment centres | Numerical |
| `RAD` | Index of accessibility to highways | Numerical |
| `TAX` | Property tax rate per $10,000 | Numerical |
| `PTRATIO` | Pupil-teacher ratio by town | Numerical |
| `B` | Proportion of population by town | Numerical |
| `LSTAT` | % of lower income population | Numerical |
| **`MEDV`** | **Median house price — TARGET** | Numerical |

---

## 🧠 ML Models Used

### 1. Linear Regression
A simple model that draws the best straight line through the data. Good baseline.

### 2. Random Forest Regressor ✅ Best Model
An ensemble of 100 decision trees that vote together. Much more accurate than a single line.

---

## 📈 Results

| Model | R² Score | MSE | Verdict |
|-------|----------|-----|---------|
| Linear Regression | 0.66 | 0.56 | Decent baseline |
| **Random Forest** | **0.89** | **0.26** | ✅ Best model |

> **R² Score** = How well the model explains price variation. 1.0 = perfect, 0.0 = random guessing.  
> **MSE** = Average prediction error (lower is better).

### 🔍 Key Insights

- **`LSTAT`** (% lower income population) is the **#1 most important feature** — higher poverty = lower prices
- **`RM`** (number of rooms) is **#2** — more rooms = higher prices  
- **`CRIM`** (crime rate) has a strong negative effect on price
- Random Forest outperformed Linear Regression by **+21% in R² score**

---

## 🗂️ Project Structure

```
ShadowFox/
│
├── HousingData.csv              # Dataset
├── boston_prediction.ipynb      # Main Jupyter Notebook
├── README.md                    # This file
```

---

## ⚙️ How to Run

### Step 1 — Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/ShadowFox.git
cd ShadowFox
```

### Step 2 — Install required libraries
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### Step 3 — Open the notebook in VS Code
```bash
# Open VS Code in current folder
code .
# Then open boston_prediction.ipynb
# Click "Select Kernel" → choose Python 3
```

### Step 4 — Run all cells
- Click on each cell and press `Shift + Enter` to run
- Or press `Run All` from the top menu
- Results and charts will appear below each cell

---

## 📉 Visualisations

The notebook includes the following charts:

| Chart | What it shows |
|-------|--------------|
| Price Distribution Histogram | How house prices are spread across the dataset |
| Rooms vs Price Scatter | More rooms → higher price trend |
| Crime Rate vs Price Scatter | Higher crime → lower price trend |
| LSTAT vs Price Scatter | More poverty → lower price trend |
| Correlation Heatmap | Which features are most related to price |
| Actual vs Predicted (both models) | How close the model guesses were |
| Feature Importance Bar Chart | Which features the Random Forest relies on most |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.11 | Programming language |
| Pandas | Data loading and manipulation |
| NumPy | Numerical operations |
| Matplotlib & Seaborn | Data visualisation |
| Scikit-learn | ML models, scaling, evaluation |
| Jupyter Notebook | Interactive coding environment |
| VS Code | IDE |

---

## 🚀 What I Learned

- How to handle missing values using median imputation
- Difference between Linear Regression and Random Forest
- How to evaluate ML models using R² Score and MSE
- How to identify which features matter most using feature importance
- How to visualise predictions vs actual values

---

## 👤 Author

**Anjali Mulchandani**  
ShadowFox AIML Intern  
[LinkedIn](https://www.linkedin.com/in/anjali-mulchandani-a36829336/) • [GitHub](https://github.com/25032007)

---

*Built with ❤️ as part of the ShadowFox AIML Internship Program*