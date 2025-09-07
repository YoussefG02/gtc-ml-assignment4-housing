# Housing Price Prediction – Data Cleaning, Preprocessing & Modeling

## Project Overview
This project focuses on **data cleaning, preprocessing, and modeling** for the **California Housing dataset** (`housing.csv`).  
The objective is to build machine learning models that predict **median house values** based on demographic, geographic, and economic features.  
Two models were trained and compared: **Linear Regression** and **Random Forest Regressor**.  

---

## Repository Contents
- **`Housing.ipynb`** → Jupyter Notebook containing the entire workflow (EDA → Cleaning → Feature Engineering → Modeling).  
- **`housing.csv`** → Dataset provided.  
- **`README.md`** → Project documentation (this file).  

---

## Workflow

### Phase 1: Exploratory Data Analysis (EDA)
- Displayed dataset shape, info, and summary statistics  
- Checked for missing values and duplicates  
- Visualized missingness using **Missingno**  
- Detected outliers with **boxplots** and **Z-score method**  
- Identified skewed numeric features that required transformation  

### Phase 2: Data Cleaning
1. **Missing Values**
   - Replaced `null`, `NaN`, and empty strings with proper `NaN` values  
   - Dropped rows with missing values (dataset size allowed this)  
   - Removed duplicate rows  

2. **Outliers**
   - Applied **log-transformation** for skewed features:  
     `total_rooms`, `total_bedrooms`, `population`, `households`, `median_income`  
   - Applied **percentile capping (1st–99th)** to reduce the influence of extreme values  

3. **Categorical Encoding**
   - Encoded `ocean_proximity` using **One-Hot Encoding** with `drop_first=True` to avoid multicollinearity  

---

### Phase 3: Modeling & Evaluation
Two machine learning models were trained and evaluated:

| Model               | RMSE     | MAE     | R²   |
|----------------------|----------|---------|------|
| Linear Regression    | 70,665   | 53,207  | 0.63 |
| Random Forest        | 49,076   | 31,954  | 0.82 |

**Conclusion**: Random Forest significantly outperformed Linear Regression in predictive accuracy.  

---

## Technologies Used
- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn, Missingno (for EDA/visualization)  
- Scikit-learn (for preprocessing and modeling)  

---

## How to Use
1. Clone this repository:  
   ```bash
   git clone https://github.com/YoussefG02/gtc-ml-assignment4-housing.git
   
