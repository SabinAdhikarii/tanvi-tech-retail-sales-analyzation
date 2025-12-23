# 🛒 Retail Sales Analysis & Prediction

## 📌 Project Overview
This project explores **retail sales data** to uncover insights and build predictive models.  
It combines **exploratory data analysis (EDA)**, **feature engineering**, and **machine learning regression** to evaluate how well transaction totals can be predicted from customer and product features.

The repository contains:
- `retail_sales_dataset.csv` → Dataset used for analysis  
- `retail_sales_analysis.ipynb` → Jupyter Notebook with full workflow (EDA, preprocessing, modeling, evaluation)  
- `report.pdf` → Formal project report with conclusions and recommendations  

---

## 🎯 Objectives
- Perform **exploratory data analysis** to understand sales trends, customer demographics, and product categories.
- Engineer meaningful features (e.g., age groups, weekend flag, product popularity).
- Build and evaluate **predictive models** for retail sales amounts.
- Interpret results and highlight **data leakage risks** when targets are deterministic.
- Provide recommendations for **future modeling directions** (e.g., classification tasks, forecasting).

---

## 📊 Exploratory Data Analysis
Key visualizations include:
- **Daily Sales Trends** → Line plots of total sales over time.  
- **Sales by Product Category** → Bar charts showing category contributions.  
- **Gender Distribution** → Pie chart of customer demographics.  
- **Pairplots** → Relationships between `Quantity`, `Price per Unit`, and `Total Amount`.  
- **Age Distribution** → Histogram of customer ages.  
- **Outlier Detection** → Z-score and IQR methods applied to `Total Amount`.

---

## ⚙️ Feature Engineering
- **Date Features**: Year, Month, Day, Day of Week, Weekend flag.  
- **Age Grouping**: Binned into `<20`, `20–40`, `40–60`, `>60`.  
- **Gender Encoding**: Male → 0, Female → 1.  
- **Product Popularity**: Frequency of product category purchases.  
- **Average Price per Category**: Mean unit price per product category.  

⚠️ Note: `Total Amount = Quantity × Price per Unit`.  
Including this interaction feature leads to **data leakage** and artificially perfect predictions.

---

## 🤖 Modeling
- **Algorithm**: Random Forest Regressor (200 trees, `random_state=42`)  
- **Pipeline**:  
  - OneHotEncoder for categorical features  
  - Pass-through for numeric features  
  - Random Forest for regression  

---

## 📈 Evaluation
Metrics used:
- **RMSE (Root Mean Squared Error)** → 1.79  
- **MAE (Mean Absolute Error)** → ~0 (negligible)  
- **R² Score** → 0.99999  

### Interpretation
- The model predicts `Total Amount` almost perfectly because the target is **deterministically defined** by `Quantity × Price per Unit`.  
- This validates the pipeline but shows that regression on deterministic targets is trivial.  
- Future work should focus on **non-deterministic targets** (e.g., product category prediction, customer segmentation, or time-series forecasting).

---

## 📂 Repository Structure
├── retail_sales_analysis.ipynb   # Jupyter Notebook with code
├── retail_sales_dataset.csv      # Dataset
├── report.pdf                     # Project report
└── README.md                      # Project documentation


---

## 🚀 Future Directions
- **Classification tasks**: Predict product category or customer segment.  
- **Forecasting**: Predict monthly or weekly sales totals.  
- **Customer analytics**: Identify high-value customers or churn risk.  
- **Noise & external features**: Add promotions, discounts, or seasonal effects for realistic modeling.


## 📜 License
This project is released under the MIT License.  
Feel free to use, modify, and share with attribution.

### ✍️ Author
Created by **Sabin Adhikarii** ("https://github.com/SabinAdhikarii") as part of a personal learning journey in AI and workflow automation.  
AI/ML Intern at Tanvi Tech Pvt. Ltd. | Islington College (London Metropolitan University)  
Feedback and suggestions are always welcome!
