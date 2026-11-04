PROJECT TITLE
Analysis of Behavioral Risk Factors Associated with Stroke Hospitalization in Ontario Public Health Units


PROJECT OVERVIEW
This project analyzes how behavioral risk factors influence stroke hospitalization rates across Ontario Public Health Units (PHUs).

We built an end to end data analytics pipeline:
- Raw public health data ingestion
- Data cleaning and panel dataset construction
- Exploratory data analysis
- Statistical and machine learning modeling
- Policy driven recommendations

The analysis extends my original proposal by incorporating both 2016 and 2017 data to strengthen insights.


PROBLEM STATEMENT
Stroke is a major contributor to hospitalization and long term disability in Ontario.

I aim to answer:
- How do behavioral risk factors vary across PHUs?
- Which factors are most strongly associated with stroke hospitalization rates?
- Which regions should be prioritized for intervention?


DATA DESCRIPTION
Source - Public Health Ontario datasets

Unit of Analysis - Public Health Unit (PHU)

Time Frame - 2016 and 2017

Final Dataset
- 44 observations
- 22 PHUs
- 2 years

Variables
Target: stroke_hosp_rate

Predictors:
smoking_rate
no_pa_minutes_rate
low_fv_rate
heavy_drinking_rate

All values are age standardized rates.


PROJECT STRUCTURE

cohort_project/

data_raw/
Raw Excel files from Public Health Ontario

data_processed/
Cleaned dataset and model outputs

notebooks/
01_build_panel_dataset.ipynb
02_data_cleaning.ipynb
03_exploratory_data_analysis.ipynb
04_statistical_modeling.ipynb
05_recommendations_and_conclusion.ipynb

outputs/
Charts, model summaries, final results

README.md


WORKFLOW

Notebook 1. Build Panel Dataset
- Loaded multiple excel files
- Standardized structure
- Combined datasets into PHU year panel

Notebook 2. Data Cleaning

- Fixed column formats
- Handled missing values
- Validated consistency across PHUs

Notebook 3. Exploratory Data Analysis

- Distribution analysis
- Correlation heatmaps
- PHU comparisons
- Year comparison insights

Notebook 4. Statistical Modeling

Models Applied:

- Multiple Linear Regression
- Regression with Year Effect
- Ridge Regression
- Lasso Regression

Diagnostics:

- VIF For multicollinearity
- Residual analysis
- QQ Plots

Notebook 5. Recommendations and Conclusion

- Converted model results into actionable public health recommendations
- Identified key predictors and ranked risk factors by importance
- Highlighted high priority PHUs for targeted intervention
- Generated final summary, limitations, and future work sections


KEY RESULTS

1. Model Performance

OLS with year effect:
R² ≈ 0.435

Interpretation:
Risk factors explain about 43 percent of variation in stroke hospitalization rates.

Adding year:
Minimal improvement
Regional variation dominates time variation

2. Significant Predictor

Smoking rate:
Coefficient ≈ 3.44
p-value < 0.01

Interpretation:
A 1 percent increase in smoking is associated with about 3.4 additional stroke hospitalizations per 100000 population.

3. Other Predictors

Physical inactivity:
Moderate effect
Not statistically significant

Heavy drinking:
Weak association

Low fruit and vegetable consumption:
Minimal effect

4. Multicollinearity

All VIF values below 5
No instability in predictors

5. Machine Learning Models

Ridge:
R² ≈ 0.416

Lasso:
R² ≈ 0.431

Interpretation:
Lasso performs slightly better
Results align with OLS
Model is stable and not overfitting

6. Key Insights

- Smoking is the dominant risk factor
- Other behavioral variables show weaker signals in this dataset
- Differences across PHUs matter more than differences across years


RECOMMENDATIONS

1. High Priority

Smoking reduction
- Expand cessation programs
- Target high risk PHUs
- Strengthen awareness campaigns


2. Medium Priority

Physical activity
- Community programs
- Workplace initiatives
  
Alcohol risk
- Targeted awareness in high risk regions

3. Lower Priority
   
Nutrition
- Improve access to healthy food
- Continue education efforts


OUTPUTS

Generated assets include:
- Regression coefficient plots
- Residual diagnostics
- Correlation matrices
- Top PHU charts
- Smoking vs stroke scatter plot
  
All stored in:
outputs/


LIMITATIONS

- Small dataset
- Only two years of data
- PHU level analysis
- No demographic controls
- Some variables assumed constant across years


FUTURE WORK

- Add more years of data
- Include socioeconomic variables
- Use panel fixed effects models
- Build dashboard
- Apply classification models


TECH STACK

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Statsmodels
- Scikit-learn


HOW TO RUN

Install dependencies
pip install pandas numpy matplotlib seaborn statsmodels scikit-learn scipy openpyxl

Run notebooks in order
1. 01_build_panel_dataset
2. 02_data_cleaning
3. 03_exploratory_data_analysis
4. 04_statistical_modeling
5. 05_recommendations_and_conclusion