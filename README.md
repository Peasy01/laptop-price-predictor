# Laptop Price Predictor 💻

A machine learning system that predicts the market price of a laptop based on its hardware specifications (such as RAM, CPU, Storage, Brand, and Screen Size). 

This project solves the problem of price uncertainty for buyers and sellers by analyzing historical marketplace data to provide highly accurate valuation estimates.

## 📊 Dataset Overview
The dataset used for this project contains technical specifications and prices for **1,303 laptops**, consisting of **16 different features**. 

### Key Features Analyzed:
* **Brand & Type:** `Company`, `TypeName` (e.g., Gaming, Notebook, Ultrabook)
* **Screen Properties:** `Inches`, `Touchscreen`, `Ips` display, and `PPI` (Pixels Per Inch)
* **Core Hardware:** `Ram`, `Weight`, `CPU_brand`, `Gpu_brand`
* **Storage Configuration:** `SSD`, `HDD`, `Flash_storage`, `Hybrid`
* **Operating System:** `OpSys`
* **Target Variable:** `Price`

## 🛠️ Tech Stack & Workflow
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Data Visualization:** Seaborn, Matplotlib
* **Machine Learning Framework:** Scikit-Learn, XGBoost

### Engineering Highlights:
* **Preprocessing Experimentation:** Evaluated the performance impact of **One-Hot Encoding (OHE)** vs. **Label Encoding (LE)** on categorical features.
* **Pipelines & ColumnTransformers:** Used to bundle preprocessing and model training into a clean, repeatable workflow.
* **Data Splitting:** Separated data into **70% Training** and **30% Testing** sets (`test_size=0.3`) to ensure robust evaluation.

## 📈 Model Performance & Evaluation
I trained four different regression models and compared their performance across both encoding techniques using **R² Score**, **Mean Absolute Error (MAE)**, and **Root Mean Squared Error (RMSE)**.

| Model | R² (OHE) | MAE (OHE) | RMSE (OHE) | R² (LE) | MAE (LE) | RMSE (LE) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **XGBRegressor (Best)** | 0.8798 | 0.1585 | 0.2120 | **0.8911** | **0.0138** | **0.0187** |
| Random Forest | 0.8621 | 0.1723 | 0.2270 | 0.8760 | 0.0149 | 0.0200 |
| Linear Regression | 0.8259 | 0.1971 | 0.2551 | 0.6427 | 0.0254 | 0.0339 |
| Decision Tree | 0.7722 | 0.2130 | 0.2918 | 0.7799 | 0.0193 | 0.0266 |

### Key Engineering Insights:
* **XGBoost with Label Encoding** yielded the absolute best results, achieving an **R² score of 0.8911** and the lowest overall error rates.
* **Tree-based models** (XGBoost, Random Forest, Decision Tree) scaled significantly better with Label Encoding, likely due to reduced dimensionality compared to OHE.
* **Linear Regression** heavily penalized Label Encoding (R² dropped to 0.6427), demonstrating that linear models assume artificial numerical ordering in label-encoded categories, whereas tree models do not.

## 💻 How to Run This Project Locally

1. **Clone or download** this repository to your computer.
2. Open your terminal or command prompt and install the required libraries:
   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn xgboost
   ```
3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
4. Open the `.ipynb` file and run all the cells to see the data analysis and model training in action!

---
📩 **Let's Connect!**
* **GitHub:** [Peasy01](https://github.com)
