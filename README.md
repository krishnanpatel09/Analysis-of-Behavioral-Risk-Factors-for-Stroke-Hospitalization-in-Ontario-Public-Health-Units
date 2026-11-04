<h1 align="center">🧠 Analysis of Behavioral Risk Factors for Stroke Hospitalization in Ontario</h1>

<p align="center">
  Data analytics project examining how behavioral risk factors relate to stroke hospitalization rates across Ontario Public Health Units.
</p>

<p align="center">
  <a href="https://www.python.org/" target="_blank"><img src="https://img.shields.io/badge/Python-Programming-blue" alt="Python"></a>
  <a href="https://pandas.pydata.org/" target="_blank"><img src="https://img.shields.io/badge/Pandas-Data%20Wrangling-orange" alt="Pandas"></a>
  <a href="https://seaborn.pydata.org/" target="_blank"><img src="https://img.shields.io/badge/Seaborn-Visualization-green" alt="Seaborn"></a>
  <a href="https://www.statsmodels.org/" target="_blank"><img src="https://img.shields.io/badge/Statsmodels-Regression-purple" alt="Statsmodels"></a>
  <a href="https://scikit-learn.org/" target="_blank"><img src="https://img.shields.io/badge/Scikit--learn-ML-red" alt="Scikit-learn"></a>
  <a href="https://jupyter.org/" target="_blank"><img src="https://img.shields.io/badge/Jupyter-Notebooks-yellow" alt="Jupyter"></a>
</p>

## 📌 Overview

This project analyzes how behavioral risk factors are associated with stroke hospitalization rates across Ontario Public Health Units (PHUs). The data is sourced from Public Health Ontario and includes age-standardized rates for stroke hospitalization, smoking, physical inactivity, heavy drinking and low fruit and vegetable consumption.

The objective is to identify which modifiable risk factors are most strongly linked to stroke hospitalization and which regions should be prioritized for public health intervention.

## 🎯 Project Motivation

- Stroke is a major cause of hospitalization and long-term disability in Ontario
- Many stroke risk factors are modifiable at the population level
- Understand how behavioral risk factors vary across PHUs
- Support targeted, data-driven prevention strategies

## ❓ Research Questions

- How do behavioral risk factors vary across Ontario PHUs?
- Which factors are most strongly associated with stroke hospitalization rates?
- Which regions should be prioritized for intervention?

## 🚀 Key Features

- End-to-end data analytics pipeline
- Raw data ingestion from multiple Excel files
- Panel dataset construction (PHU × year)
- Data cleaning and validation
- Exploratory data analysis
- Statistical and machine learning modeling
- Policy-driven recommendations

## 📊 Dataset

The dataset is obtained from **Public Health Ontario** snapshots:

- Chronic Disease Hospitalization Snapshot
- Smoking Snapshot
- Alcohol Use Snapshot
- Physical Activity Snapshot
- Nutrition and Healthy Weights Snapshot

Dataset details:

- **Unit of analysis:** Public Health Unit (PHU)
- **Time frame:** 2016 and 2017
- **Final dataset:** 44 observations (22 PHUs × 2 years)
- **Missing values:** None
- **Measure:** Age-standardized rates for both sexes

Variables:

- `stroke_hosp_rate` – stroke hospitalization rate (**target variable**)
- `smoking_rate` – adult daily smoking
- `no_pa_minutes_rate` – no adult physical activity minutes
- `low_fv_rate` – fruit and vegetables consumed four or fewer times per day
- `heavy_drinking_rate` – heavy drinking exceeding low-risk guidelines

## 🏗️ Build Panel Dataset

- Loaded multiple Excel files from Public Health Ontario
- Extracted relevant indicators from each source
- Standardized PHU names, years and variable structure
- Merged outcome and risk factor datasets into one PHU-year panel

## 🧹 Data Cleaning and Preprocessing

- Fixed column names and data types
- Handled missing values
- Checked consistency across PHUs
- Validated year alignment and variable matching
- Prepared a clean dataset for EDA and modeling

## 📈 Exploratory Data Analysis

- Distribution analysis
- Correlation heatmaps
- Scatter plots of each risk factor vs stroke hospitalization
- PHU comparisons
- Year comparison (2016 vs 2017)

Key observations:

- Smoking shows the strongest positive correlation with stroke hospitalization (r ≈ 0.61)
- Heavy drinking shows a moderate positive correlation (r ≈ 0.43)
- Smoking and heavy drinking are strongly correlated with each other (r ≈ 0.78)

<!-- To show graphs, add images from the outputs folder, for example:
<p align="center">
  <img src="outputs/correlation_matrix.png" width="48%">
  <img src="outputs/smoking_vs_stroke.png" width="48%">
</p>
-->

## 🤖 Models Used

- Multiple Linear Regression
- Regression with Year Effect
- Ridge Regression
- Lasso Regression

## 📏 Model Evaluation

- **R² Score** – variance explained
- **Coefficients and p-values** – strength and significance of predictors
- **VIF** – multicollinearity check
- **Residual plots** – model assumptions
- **QQ plots** – normality of residuals

## 📊 Results and Comparison

| Model                       | R²     |
|-----------------------------|--------|
| Regression with Year Effect | 0.435  |
| Lasso Regression            | 0.431  |
| Ridge Regression            | 0.416  |

Regression with year effect performed best, explaining about 43% of the variation in stroke hospitalization rates.

Predictor findings:

- **Smoking rate** – strongest and statistically significant predictor (coefficient ≈ 3.44, p < 0.01)
- **Physical inactivity** – moderate effect, not statistically significant
- **Heavy drinking** – weak association
- **Low fruit and vegetable intake** – minimal effect
- **Multicollinearity** – all VIF values below 5

## 🧰 Tech Stack

| Category         | Tools                       |
|------------------|-----------------------------|
| Language         | Python                      |
| Data Processing  | Pandas, NumPy               |
| Visualization    | Matplotlib, Seaborn         |
| Statistics       | Statsmodels, SciPy          |
| Machine Learning | Scikit-learn                |
| Environment      | Jupyter Notebook            |

## 📁 Project Structure

```
Analysis-of-Behavioral-Risk-Factors-for-Stroke-Hospitalization/
├── data_raw/                 # Raw Excel files from Public Health Ontario
├── data_processed/           # Cleaned dataset and model outputs
├── notebooks/
│   ├── 01_build_panel_dataset.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_exploratory_data_analysis.ipynb
│   ├── 04_statistical_modeling.ipynb
│   └── 05_recommendations_and_conclusion.ipynb
├── outputs/                  # Charts, model summaries, final results
└── README.md                 # Documentation
```

## 🛠️ Installation

```
pip install pandas numpy matplotlib seaborn statsmodels scikit-learn scipy openpyxl
```

## ▶️ Usage

Open the notebooks folder in Jupyter and run the notebooks in order:

```
1. 01_build_panel_dataset.ipynb
2. 02_data_cleaning.ipynb
3. 03_exploratory_data_analysis.ipynb
4. 04_statistical_modeling.ipynb
5. 05_recommendations_and_conclusion.ipynb
```

## 📊 Key Insights

- Smoking is the dominant risk factor for stroke hospitalization
- A 1 percentage point increase in smoking is associated with about 3.4 additional stroke hospitalizations per 100,000 population
- Other behavioral variables show weaker signals in this dataset
- Differences across PHUs matter more than differences across years
- Ridge and Lasso results align with OLS, so the model is stable

## 🏥 Recommendations

**High priority – Smoking reduction**
- Expand smoking cessation programs
- Target high-risk PHUs
- Strengthen awareness campaigns

**Medium priority – Physical activity and alcohol**
- Community physical activity programs
- Workplace wellness initiatives
- Targeted alcohol awareness in high-risk regions

**Lower priority – Nutrition**
- Improve access to healthy food
- Continue nutrition education efforts

## 📚 Key Learnings

- Building a panel dataset from multiple public data sources
- Importance of data cleaning and validation
- Applying and comparing regression and regularization models
- Checking model assumptions with diagnostics
- Translating statistical results into policy recommendations

## ⚠️ Limitations

- Small dataset (44 observations)
- Only two years of data
- PHU-level (ecological) analysis – results do not apply to individuals
- No demographic or socioeconomic controls
- Some variables assumed constant across years

## 🔮 Future Work

- Add more years of PHU data
- Include demographic and socioeconomic variables
- Use panel fixed effects models
- Apply classification and advanced ML models
- Build a dashboard for public health use

## 💡 Why This Project Matters

This project demonstrates practical public health analytics using real-world data. It shows the ability to build a dataset from raw sources, apply statistical and machine learning models, and turn results into actionable recommendations for stroke prevention.

## 👤 Author

Krishna Nikunjkumar Patel

### If you found this project useful, consider giving it a star.
