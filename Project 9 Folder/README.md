🛢️ OilyGiant — Oil Reserve Prediction & Investment Risk Analysis

Project 9 — Linear Regression, Profit Modeling, and Bootstrapping

📌 Project Overview

OilyGiant is preparing a major $100M investment to drill 200 new oil wells. The goal of this project is to determine which of three regions offers the safest and most profitable opportunity — while staying within the company’s strict 2.5% maximum risk‑of‑loss threshold.

Using geological data from Regions 0, 1, and 2, I:

- Explored and validated the datasets

- Trained linear regression models

- Predicted reserves for each region

- Calculated expected profit

- Ran a 1,000‑iteration bootstrapping risk analysis

- Identified the region that meets both profitability and risk tolerance requirements
  


🧠 Business Constraints

| Requirement               | Value                |
|---------------------------|----------------------|
| Budget                    | $100,000,000         |
| Wells to develop          | 200                  |
| Revenue per 1k barrels    | $4,500               |
| Model type                | Linear Regression    |
| Max acceptable risk       | 2.5%                 |


🔍 Data Exploration

Each dataset contains:

- 100,000 wells

- 3 geological features (f0, f1, f2)

- Target variable: product (oil reserves in thousand barrels)

Duplicate well IDs were found in all regions, but the measurements differed significantly — indicating real geological variation, not errors.
To preserve valuable information, all rows were retained.


🤖 Modeling Approach

Linear Regression was chosen because:

- It was required by the project

- Each region showed linear relationships between features and reserves

- Region 1 had an exceptionally strong correlation (f2 → product, r ≈ 0.999)

- Linear models are interpretable and ideal for ranking wells

- Each region was split into 75% train / 25% validation.
  

📈 Model Performance (RMSE)

| Region | RMSE  | Interpretation              |
|--------|-------|-----------------------------|
| 0      | 37.76 | Moderate accuracy           |
| 1      | 0.89  | Extremely accurate, stable  |
| 2      | 40.15 | Moderate accuracy           |

Region 1’s model is dramatically more reliable than the others.


💰 Profit Estimation

For each region:

- Select top 200 wells by predicted reserves

- Calculate actual reserves

- Compute profit:

💲 Profit = (Total Reserves × 4500) − 100,000,000


📊 Profit Results

| Region | Profit    |
|--------|-----------|
| 0      | $33.59M   |
| 1      | $24.15M   |
| 2      | $25.99M   |

Region 0 has the highest profit — but profit alone is not enough.
We must evaluate risk.

🎲 Bootstrapping Risk Analysis
A reusable bootstrap_profit() function was implemented to avoid code duplication.
Each region was simulated 1,000 times using random sampling.

⭐ Bootstrapping Results
| Region | Avg Profit | 95% CI                  | Risk of Loss |
|--------|------------|--------------------------|---------------|
| 0      | $3.99M     | –$1.10M to $8.97M        | 6.0% ❌        |
| 1      | $4.52M     | $0.62M to $8.45M         | 1.5% ✅        |
| 2      | $3.75M     | –$1.45M to $8.88M        | 8.0% ❌        |

Region 1 is the only region below the 2.5% risk threshold.

🏆 Final Recommendation
Region 1 is the recommended region for oil well development.

It provides:

- The most accurate predictions (RMSE 0.89)

- The lowest risk of loss (1.5%)

- A positive confidence interval entirely above zero

- A strong, consistent profit estimate

Region 1 is the only region that meets OilyGiant’s strict 2.5% maximum risk‑of‑loss requirement, confirming that it satisfies both the profitability and risk criteria for investment.

📁 Project Structure

- [Project 9.ipynb](Project%209.ipynb) — Full analysis, modeling, and bootstrapping  
- [geo_data_0.csv](./geo_data_0.csv) — Region 0 dataset  
- [geo_data_1.csv](./geo_data_1.csv) — Region 1 dataset  
- [geo_data_2.csv](./geo_data_2.csv) — Region 2 dataset  
- [README.md](./README.md) — Project documentation  

             

🛠️ Technologies Used
Python

Pandas

NumPy

Scikit‑learn

Matplotlib

Bootstrapping (custom implementation)

💬 Summary
Region 1 is the safest, most stable, and most financially responsible choice for OilyGiant’s $100M investment.
This project demonstrates end‑to‑end data science workflow: exploration, modeling, evaluation, risk analysis, and business‑driven decision‑making.
