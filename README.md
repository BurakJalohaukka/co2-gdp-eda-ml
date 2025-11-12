# 🌍 Global GDP–CO₂ Analysis
Exploring Economic Growth, Emissions, and Efficiency (1960–2024)

## 📘 Overview

This notebook explores the relationship between global GDP, population, and CO₂ emissions.
The focus is on understanding patterns and trends, rather than making definitive claims — it’s a learning project in **data analysis and machine learning**.

The analysis includes:

* Data cleaning, merging and exploratory data analysis (EDA)
* Visualization of historical trends and global efficiency metrics
* Machine learning modeling to explore predictive relationships
* Feature interpretation and residual analysis to understand model behavior

Link to notebook : [GDP CO2](https://github.com/BurakJalohaukka/co2-gdp-eda-ml/blob/main/co2_vs_gdp.ipynb)


| Aspect                 | Observation                                                                                                            |
| :--------------------- | :--------------------------------------------------------------------------------------------------------------------- |
| **CO₂ vs GDP**         | Shows a strong log–log relationship. GDP is generally a dominant factor in emissions.                                  |
| **CO₂ per GDP Trends** | Sharp peaks (~1970, ~1993) may reflect historical energy shocks and industrial transitions.                            |
| **Global Dips in CO₂** | Dips before 2010 and in 2020 likely reflect the 2008 financial crisis and COVID-19 lockdowns.                          |
| **Feature Importance** | In total GDP models, GDP dominates; in GDP per capita models, population becomes more prominent.                       |
| **Residual Patterns**  | Total GDP models show residuals related to GDP level; per-capita models reduce this bias while overall spread remains. |




| Model                      | Features                             | Scale | R²   | MAE  | Notes                                                     |
| :------------------------- | :----------------------------------- | :---- | :--- | :--- | :-------------------------------------------------------- |
| **Linear Regression**      | log(GDP), log(Population)            | log   | 0.84 | 0.83 | Baseline model; captures core log–log trend               |
| **Random Forest**          | log(GDP), log(Population)            | log   | 0.87 | 0.66 | Flexible nonlinear model; slightly better fit             |
| **GDP per Capita Variant** | log(GDP_per_capita), log(Population) | log   | 0.88 | 0.63 | Explores per-person effects; residual bias by GDP reduced |



## 🧩 Data & Processing

CO2: https://github.com/owid/co2-data?tab=readme-ov-file  
GDP annual : https://data.worldbank.org/indicator/NY.GDP.MKTP.KD.ZG?end=2024&start=1960

* Cleaning:
    * Removed rows with missing or zero values
    * Log-transformed GDP, population, and emissions

* Derived metrics:
    * CO₂ per GDP
    * GDP per capita

⚠️ Note: This is an exploratory analysis — patterns observed here are for learning purposes, probably not useful for policy recommendations :D.

## 🧪 Tools & Libraries

* Python, Pandas, NumPy
* Matplotlib, Seaborn
* Scikit-learn
* Jupyter Notebook

## 🧭 Next Steps / Ideas for Exploration

* Compare different regions or income groups
* Test additional machine learning models
* Explore time-series forecasting or policy impact effects
* Deep dive into carbon efficiency trends per sector or country