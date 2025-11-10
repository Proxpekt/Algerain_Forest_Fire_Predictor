# 🔥 Algerian Forest Fire Prediction using Machine Learning

This project develops and evaluates several linear regression models to accurately predict the **Fire Weather Index (FWI)** — a critical measure of forest fire risk — using meteorological data from Algerian forest regions.  
The model aims to assist in **fire prevention strategies** and **efficient resource allocation**.

---

## 📋 Project Overview

### 🎯 Objective
The primary goal is to **predict the continuous-variable Fire Weather Index (FWI)** using environmental and meteorological factors.  
This is formulated as a **Supervised Regression Problem**.

---

## 📊 Dataset

**Dataset Used:** [Algerian Forest Fires Dataset (UCI Repository)](https://archive.ics.uci.edu/ml/datasets/Algerian+Forest+Fires+Dataset)

- **Regions Covered:** Bejaia (Northeast) and Sidi-Bel Abbes (Northwest), Algeria  
- **Time Period:** June – September 2012  
- **Target Variable:** Fire Weather Index (**FWI**)

### 🌦️ Feature Overview

| Feature Category | Example Attributes |
|------------------|--------------------|
| **Weather Data** | Temperature (Temp), Relative Humidity (RH), Wind Speed (Ws), Rain |
| **FWI Components** | Fine Fuel Moisture Code (FFMC), Drought Code (DC), Initial Spread Index (ISI), Buildup Index (BUI) |

---

## 🛠️ Methodology

### 1. Data Cleaning & EDA (`data_cleaner.ipynb`)
- **Initial Cleaning:** Fixed data entry errors, including a misplaced row combining two regions.  
- **Feature Engineering:** Converted categorical variable `Classes` ("fire", "not fire") into numeric labels (`1`, `0`) for analysis.  
- **Exploratory Data Analysis (EDA):**  
  - Identified August–September as the **peak fire months** for both regions.  
  - Visualized feature correlations to understand relationships between weather variables and fire risk.

---

### 2. Model Training & Selection (`model_training.ipynb`)
- **Feature Selection:**  
  - Removed `DC` due to high multicollinearity with `BUI` (correlation > 0.85).  
- **Data Preparation:**  
  - Split dataset into **75% training** and **25% testing** sets.  
  - Standardized features using `StandardScaler`.  
- **Trained Regression Models:**  
  - Linear Regression  
  - Ridge Regression  
  - Lasso Regression  

---

## ✅ Results and Performance

| Model | Mean Absolute Error (MAE) | R² Score |
|--------|-----------------------------|-----------|
| **Linear Regression** | **0.867** | **97.62%** |
| Ridge Regression | 0.885 | 97.56% |
| Lasso Regression | 1.576 | 93.52% |

📈 **Linear Regression** achieved the best overall performance, with an impressive **R² score of 97.62%**, making it the most reliable model for predicting the Fire Weather Index (FWI).

---

## 📁 Repository Structure
│  <br>
├── data_cleaner.ipynb # Data loading, cleaning, and EDA  <br>
├── model_training.ipynb # Model implementation, training, and evaluation  <br>
├── CLEANED_Algerian_forest_fires_dataset_.csv # Cleaned dataset used for model training  <br>
└── README.md # Project documentation  <br>


---

## 💡 Future Improvements
- Incorporate **non-linear models** (e.g., Random Forest, Gradient Boosting) for comparison.  
- Perform **feature importance analysis** to identify the strongest predictors of fire risk.  
- Extend the study using **real-time meteorological data** for live fire risk prediction.

---

## 🧠 Tech Stack
- **Language:** Python  
- **Libraries:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn  
- **Tools:** Jupyter Notebook, StandardScaler, Ridge/Lasso Regression  
