<h1 align="center">🧠 Behavioral Risk Factors & Stroke Hospitalization in Ontario</h1> <p align="center"> Data analytics project examining how smoking, physical inactivity, heavy drinking and nutrition relate to stroke hospitalization rates across Ontario Public Health Units. </p> <p align="center"> <img src="https://img.shields.io/badge/Python-Programming-3776AB?style=flat&logo=python&logoColor=white" alt="Python"> <img src="https://img.shields.io/badge/Pandas-Data%20Wrangling-E67E22?style=flat&logo=pandas&logoColor=white" alt="Pandas"> <img src="https://img.shields.io/badge/Seaborn-Visualization-4CAF50?style=flat" alt="Seaborn"> <img src="https://img.shields.io/badge/Statsmodels-Regression-8E44AD?style=flat" alt="Statsmodels"> <img src="https://img.shields.io/badge/Scikit--learn-ML-E74C3C?style=flat&logo=scikitlearn&logoColor=white" alt="Scikit-learn"> <img src="https://img.shields.io/badge/Jupyter-Notebooks-F37626?style=flat&logo=jupyter&logoColor=white" alt="Jupyter"> </p>
📌 Overview

Stroke is a major cause of hospitalization and long-term disability in Ontario, and many of its risk factors are modifiable at the population level. This project analyzes how behavioral risk factors relate to stroke hospitalization rates across Ontario Public Health Units (PHUs), using publicly available data from Public Health Ontario.

It is built as an end-to-end analytics pipeline:

Raw public health data ingestion
Data cleaning and panel dataset construction
Exploratory data analysis
Statistical and machine learning modeling
Policy-driven recommendations

The analysis extends the original proposal, which covered 2016 only, by adding 2017 data to strengthen the findings.

🎯 Project Motivation
Understand how behavioral risk factors vary across Ontario PHUs
Identify which factors are most strongly associated with stroke hospitalization
Determine which regions should be prioritized for intervention
Turn model results into practical public health recommendations
🗂️ Dataset
Item	Details
Source	Public Health Ontario (Hospitalization, Smoking, Alcohol Use, Physical Activity, and Nutrition & Healthy Weights Snapshots)
Unit of analysis	Public Health Unit (PHU)
Time frame	2016 and 2017
Final dataset	44 observations: 22 PHUs × 2 years, no missing values
Measure	All values are age-standardized rates for both sexes
Variables
Variable	Role	Description
stroke_hosp_rate	🎯 Target	Hospitalization for stroke
smoking_rate	Predictor	Self-reported adult daily smoking
no_pa_minutes_rate	Predictor	Self-reported no adult physical activity minutes
low_fv_rate	Predictor	Vegetables and fruit consumed four or fewer times per day
heavy_drinking_rate	Predictor	Self-reported heavy drinking exceeding low-risk guidelines
📁 Project Structure
├── data_raw/            # Raw Excel files from Public Health Ontario
├── data_processed/      # Cleaned panel dataset and model outputs
├── notebooks/
│   ├── 01_build_panel_dataset.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_exploratory_data_analysis.ipynb
│   ├── 04_statistical_modeling.ipynb
│   └── 05_recommendations_and_conclusion.ipynb
├── outputs/             # Charts, model summaries, final results
└── README.md
🔄 Workflow
<details open> <summary><b>1️⃣ Build Panel Dataset</b></summary>
Loaded multiple Excel files from Public Health Ontario
Extracted the relevant indicators from each source
Standardized PHU names, years and variable structure
Merged outcome and risk factor data into one PHU-year panel
</details> <details open> <summary><b>2️⃣ Data Cleaning</b></summary>
Fixed column names and data types
Handled missing values
Validated consistency and year alignment across PHUs
</details> <details open> <summary><b>3️⃣ Exploratory Data Analysis</b></summary>
Distribution analysis
Correlation heatmaps
PHU comparisons
Year-over-year comparisons
</details> <details open> <summary><b>4️⃣ Statistical Modeling</b></summary>
Model	Why it was used
Multiple Linear Regression	Measures the relationship between stroke hospitalization and all risk factors together
Regression with Year Effect	Checks whether 2016 vs 2017 differences improve the model
Ridge Regression	Reduces coefficient instability when predictors are correlated
Lasso Regression	Identifies the strongest predictors by shrinking weaker ones

Diagnostics: VIF for multicollinearity, residual analysis, QQ plots

</details> <details open> <summary><b>5️⃣ Recommendations & Conclusion</b></summary>
Converted model results into actionable public health recommendations
Ranked risk factors by importance
Highlighted high-priority PHUs for targeted intervention
Summarized limitations and future work
</details>
📊 Key Results
Model Performance
Model	R²
⭐ OLS with Year Effect	≈ 0.435
Lasso Regression	≈ 0.431
Ridge Regression	≈ 0.416
Behavioral risk factors explain about 43% of the variation in stroke hospitalization rates.
Adding a year effect gave minimal improvement, so regional variation dominates time variation.
Ridge and Lasso results align with OLS, indicating a stable model that is not overfitting.
All VIF values are below 5, so multicollinearity is not a concern.
Predictor Findings
Predictor	Finding
🚬 Smoking rate	Strongest and only significant predictor (coefficient ≈ 3.44, p < 0.01)
🏃 Physical inactivity	Moderate effect, not statistically significant
🍺 Heavy drinking	Weak association
🥦 Low fruit & vegetable intake	Minimal effect

💡 A 1 percentage point increase in the smoking rate is associated with about 3.4 additional stroke hospitalizations per 100,000 population.

📈 Visualizations
<!-- Replace the file names below with the actual image names in your outputs/ folder --> <p align="center"> <img src="outputs/correlation_matrix.png" alt="Correlation Matrix" width="48%"> <img src="outputs/smoking_vs_stroke.png" alt="Smoking vs Stroke Hospitalization" width="48%"> </p>

Generated outputs include regression coefficient plots, residual diagnostics, correlation matrices, top-PHU charts and a smoking vs. stroke scatter plot, all stored in outputs/.

🏥 Recommendations
Priority	Area	Actions
🔴 High	Smoking reduction	Expand cessation programs, target high-risk PHUs, strengthen awareness campaigns
🟠 Medium	Physical activity	Community programs and workplace initiatives
🟠 Medium	Alcohol risk	Targeted awareness in high-risk regions
🟢 Lower	Nutrition	Improve access to healthy food and continue education efforts
⚠️ Limitations
Small dataset (44 observations)
Only two years of data
Ecological, PHU-level analysis, so results do not apply to individuals
No demographic or socioeconomic controls
Some variables assumed constant across years
🚀 Future Work
Add more years of PHU data
Include demographic and socioeconomic variables
Apply panel fixed-effects models
Test classification and other machine learning models
Build a dashboard for public health use
🛠️ Tech Stack

Python · Pandas · NumPy · Matplotlib · Seaborn · Statsmodels · Scikit-learn · SciPy · Jupyter Notebook

▶️ How to Run

1. Clone the repository

bash
git clone https://github.com/krishnanpatel09/Analysis-of-Behavioral-Risk-Factors-for-Stroke-Hospitalization-in-Ontario-Public-Health-Units.git
cd Analysis-of-Behavioral-Risk-Factors-for-Stroke-Hospitalization-in-Ontario-Public-Health-Units

2. Install dependencies

bash
pip install pandas numpy matplotlib seaborn statsmodels scikit-learn scipy openpyxl

3. Run the notebooks in order

01_build_panel_dataset.ipynb
02_data_cleaning.ipynb
03_exploratory_data_analysis.ipynb
04_statistical_modeling.ipynb
05_recommendations_and_conclusion.ipynb
📚 References
Public Health Ontario. Chronic Disease Hospitalization Snapshot
Public Health Ontario. Alcohol Use Snapshot
Public Health Ontario. Smoking Snapshot
Public Health Ontario. Physical Activity Snapshot
Public Health Ontario. Nutrition and Healthy Weights Snapshot
👤 Author

Krishna Nikunjkumar Patel GitHub
