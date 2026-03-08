# 📊 Project 3: Megaline Telecom Data Analysis

Understanding Customer Behavior & Revenue Performance

This project analyzes customer usage patterns for Megaline’s two mobile plans — Surf and Ultimate — using 12 months of call, message, internet, and billing data. The goal is to determine which plan is more profitable, how customers behave on each plan, and whether certain regions generate different revenue patterns.

🧭 Project Objectives

- Clean and prepare five datasets (users, calls, messages, internet, plans)

- Aggregate monthly usage per user

- Calculate monthly revenue based on plan limits and overage charges

- Analyze customer behavior across plans

- Test hypotheses about revenue differences

- Provide recommendations for Megaline’s commercial team

🗂️ Datasets Used

- users — customer demographics, plan type, registration/churn dates

- calls — individual call records with duration

- messages — SMS activity

- internet — MB used per session

- plans — plan limits and pricing

🛠️ Data Preparation & Cleaning

✔️ Key Fixes

- Converted all date columns to datetime

- Removed zero‑duration calls

- Created year_month for monthly aggregation

- Checked for missing values and duplicates

- Standardized city names

- Rounded call durations per project rules

- Converted MB → GB after monthly aggregation

- Ensured no negative overages using np.maximum(0, …)

✔️ Merging Strategy

All monthly usage tables were merged on user_id + year_month, then enriched with plan details to calculate revenue accurately.

📈 Monthly Revenue Calculation

For each user-month:

- Base monthly fee

- Extra minutes × per‑minute rate

- Extra messages × per‑message rate

- Extra GB × per‑GB rate

This produced a final total_revenue column used for analysis and hypothesis testing.

🔍 Behavioral Analysis

📞 Call Usage

- Average monthly minutes are similar between plans

- Ultimate has more extreme outliers

- Surf users with high usage may benefit from upgrading

- Ultimate’s 3000‑minute limit is far above actual usage patterns

💬 Message Usage

Total records analyzed: 2,293

- Surf: 1,573

- Ultimate: 720

- Ultimate users send more messages on average

- Both distributions are right‑skewed

Top 10% thresholds:

- Surf: >76 messages

- Ultimate: >83 messages

Surf’s 50‑message limit is too low for heavy texters

🌐 Internet Usage

- Surf users exceed the 15GB limit more often

- Ultimate’s 30GB limit is generous and rarely exceeded

🧪 Hypothesis Testing

1️⃣ Revenue: Surf vs Ultimate

- H₀: No difference in average revenue

- H₁: Revenue differs between plans

Result: Interpretation based on your p‑value output

2️⃣ Revenue: NY–NJ vs Other Regions

- H₀: No difference in average revenue

- H₁: Revenue differs between regions

Result: Interpretation based on your p‑value output

📝 Conclusions & Recommendations

Surf users frequently exceed message and data limits → opportunity to upsell

Ultimate users rarely hit limits → plan may be too generous

Revenue differences between plans and regions provide insight for targeted marketing

Megaline should consider adjusting Surf’s message allowance and reviewing Ultimate’s high included minutes

Project 3 Folder/
│
├── megaline_calls.csv
├── megaline_messages.csv
├── megaline_internet.csv
├── megaline_users.csv
├── megaline_plans.csv
│
├── project_3_analysis.ipynb
└── README.md
