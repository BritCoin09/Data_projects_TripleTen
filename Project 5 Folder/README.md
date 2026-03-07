🎮 Video Game Sales Analysis

📌 Project Overview

This project analyzes global video game sales to identify patterns that influence a game’s commercial success. As an analyst for the online store Ice, the goal is to understand which factors — such as platform, genre, release year, and review scores — drive higher sales and can guide future advertising strategy.

The dataset includes 16,715 records of games released between 1980–2016, with regional sales, critic/user reviews, and ESRB ratings.

🧹 Data Preparation

✔️ Key Cleaning Steps

- Standardized column names

- Converted year_of_release to Int64

- Converted user_score to numeric (handling "tbd" automatically)

- Created total_sales as the sum of all regional sales

- Added review‑status categories to preserve meaning in missing values

✔️ Missing Value Insights

- Over 50% of games lack critic or user reviews

- Missing reviews are not random — older games and low‑visibility titles are less likely to have them

- Games with both critic and user reviews have significantly higher average sales

- Missing values were kept as‑is because the absence of reviews is itself meaningful

📈 Key Findings

🎮 1. Game Releases Over Time

- Releases peaked between 2005–2011, with over 1,000 games per year

- After 2011, releases dropped by 56%, but critic scores improved, suggesting higher quality

- Nintendo dominated peak years (Wii + DS = 2,374 games)

🎭 2. Genre Trends

Genres with the highest releases and sales during peak years:

- Action

- Sports

- Miscellaneous (e.g., Wii Party, Just Dance)

- Shooter

🌍 3. Regional Sales Patterns

- North America consistently leads in sales volume

- Europe follows closely

- Japan shows strong preference for RPGs and Nintendo platforms

🎮 PS4 Review Score Analysis

To understand how reviews affect sales on a modern platform, I analyzed PS4 games separately.

🔍 Correlation Results

- Critic Score vs Sales: 0.432

- User Score vs Sales: 0.024

📝 Interpretation

- Critic reviews have a moderate positive relationship with sales

- User reviews have almost no relationship with sales

- Critic scores likely influence early purchasing decisions and marketing

- User scores accumulate later and vary widely in reliability

🧠 Conclusions

The video game market experienced a major boom from 2005–2011, followed by consolidation

Fewer releases after 2011 corresponded with higher average critic scores

Action, Sports, Misc, and Shooter genres consistently dominate sales

Critic reviews matter far more than user reviews for predicting sales

Nintendo platforms played a major role in shaping the peak years of the industry

🛠️ Tools & Libraries

Python

Pandas

NumPy

Matplotlib

Seaborn

SciPy

## 📁 Project Files

- [Project 5.ipynb](Project%205.ipynb) — Full analysis notebook  
- [games.csv](games.csv) — Dataset used for this project  
- [README.md](README.md) — Project documentation  

