# Obesity Risk Analysis

## Project Overview
This study analyzes various factors that influence an individual's risk of obesity. The objective is to identify common characteristics among high-risk groups to assist healthcare institutions in developing effective prevention and treatment strategies. We use **Random Forest** for modeling and apply **SMOTE** to address class imbalance. Additionally, we perform **Pearson correlation analysis and Kruskal-Wallis tests** to examine variable relationships and ensure model stability.

## 📂 Project Structure
```bash
├── 📄 README.md # This documentation  
├── 📄 EDA.ipynb # Jupyter Notebook of exploratory data analysis 
├── 📄 model.ipynb # Model training and evaluation 
├── 📄 requirements.txt # List of dependencies
```

## Methodology
### 1️. **Dataset**
- The dataset is sourced from [Kaggle](https://www.kaggle.com/competitions/playground-series-s4e2/data) and contains **20,758 samples** with **17 feature variables + 1 target variable**. It includes individual demographics, lifestyle habits, and dietary patterns.

### 2️. **Exploratory Data Analysis (EDA)**
- **Variable Type Analysis**: 9 categorical and 8 continuous variables
- **Data Distribution Visualization**: Histograms, box plots
- **Handling Missing and Outlier Values**
- **Correlation Analysis**:
  - **Between continuous variables**: Pearson correlation
  - **Between categorical variables**: Chi-square test and Cramer’s V
  - **Between categorical & continuous variables**: Point-biserial correlation
  - **Between multi-category & continuous variables**: Kruskal-Wallis test

### 3️. **Data Preprocessing**
- Removed irrelevant variables (`id`)
- **One-Hot Encoding for categorical variables**
- **Standardization of continuous variables (StandardScaler)**
- **Split dataset into training (80%) and test (20%) sets**
- **Addressed class imbalance using SMOTE** to generate synthetic minority samples

### 4️. **Model Development**
- **Classification Algorithm**: Random Forest
- **Hyperparameter Settings**:
  - `n_estimators=100`
  - `criterion='gini'`
  - `max_depth=None`
  - `min_samples_split=2`
  - `min_samples_leaf=1`
- **Feature Importance Analysis**
- **Evaluation Metrics**:
  - **Accuracy**
  - **AUC Score**
  - **Confusion Matrix**
  - **Classification Report**

## Results
- **Model Accuracy: 88.7%**
- **Average AUC: 0.98**
- **Key Features Influencing Obesity Risk**:
  1. **Weight**
  2. **Age**
  3. **Height**
- **ROC Curve Analysis confirms strong predictive performance**

## Environment Setup
Ensure Python 3.8+ is installed and install dependencies using:
```bash
pip install -r requirements.txt
```
## Future Improvements
- **Incorporate additional individual characteristics (e.g., genetic data, psychological factors) to enhance prediction accuracy**
- **Explore deep learning models (e.g., CNN, LSTM) for improved performance**
- **Compare results with other classification models (e.g., XGBoost, LightGBM)**

## References
- **Kaggle. Multi-Class Prediction of Obesity Risk (2024). Dataset Link**
- **Ma, N. (2018). Adjusting Significance Levels in Big Data Analysis. Journal of Smart Technology and Applied Statistics, 16(2), 19-36.***
