Predicting Unemployment Rates from Community Demographics
📌 Overview

This project analyzes how demographic and socioeconomic factors influence unemployment rates across Arizona counties. Using a combination of data from the U.S. Census Bureau, Bureau of Labor Statistics (BLS), and PolicyMap, a multiple linear regression model was developed to identify key predictors of unemployment.

The analysis focuses on a cross-sectional dataset for 2024, allowing for direct comparison between Arizona’s 15 counties. Results are supported through both statistical modeling in Python and interactive visualization in Power BI.

Key Insights
Higher education levels are associated with lower unemployment
Higher median income correlates with lower unemployment, but moderately
Labor force participation shows a positive relationship with unemployment
Poverty rate did not behave as expected, highlighting complex interactions between variables
🛠️ Technologies Used
Python
pandas
numpy
scikit-learn
matplotlib
JupyterLab (Anaconda)
Power BI
Data Sources
U.S. Census Bureau (ACS 5-Year Estimates)
Bureau of Labor Statistics (LAUS)
PolicyMap
Federal Reserve Economic Data (FRED)
🔁 How to Reproduce the Analysis
1. Clone the repository
git clone https://github.com/your-username/unemployment-analysis.git
cd unemployment-analysis
2. Set up your environment

Install required Python libraries:

pip install pandas numpy scikit-learn matplotlib
3. Load and clean datasets

Run the data cleaning scripts/notebooks to prepare each dataset:

clean_unemployment.csv
clean_income_2024.csv
clean_poverty_2024.csv
clean_education_2024.csv
clean_lfp_2024.csv
clean_population_2024.csv
4. Merge datasets

Run the merge step:

df = unemp.merge(income, on=["county", "year"]) \
          .merge(poverty, on=["county", "year"]) \
          .merge(education, on=["county", "year"]) \
          .merge(lfp, on=["county", "year"]) \
          .merge(population, on=["county", "year"])
5. Save final dataset
df.to_csv("final_capstone_dataset.csv", index=False)
6. Run regression analysis

Use scikit-learn to train a multiple linear regression model:

from sklearn.linear_model import LinearRegression

Evaluate using:

R²
MAE
RMSE
7. Build Power BI dashboard

Import:

final_capstone_dataset.csv

Create:

Choropleth map (unemployment by county)
Scatter plots (income, poverty, education vs unemployment)
Clustered bar chart (with variable selector)
📁 File Structure
📦 unemployment-analysis
│
├── 📂 data
│   ├── clean_unemployment.csv
│   ├── clean_income_2024.csv
│   ├── clean_poverty_2024.csv
│   ├── clean_education_2024.csv
│   ├── clean_lfp_2024.csv
│   ├── clean_population_2024.csv
│   └── final_capstone_dataset.csv
│
├── 📂 notebooks
│   ├── clean_unemployment.ipynb
│   
│
├── 📂 powerbi
│   └── CIS480 Capstone_Steven Coe.pbix
│
├── 📂 report
│   └── final_capstone_report.docx
│
└── README.md
🎯 Project Purpose

This project demonstrates how data analytics can be applied to a real-world economic problem. By combining statistical modeling with visualization, it provides insights that can support:

Workforce planning
Public policy decisions
Economic development strategies
⚠️ Limitations
Small sample size (15 counties)
Cross-sectional (single-year) analysis
Correlation does not imply causation
