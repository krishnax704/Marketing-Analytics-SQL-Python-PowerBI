# 📊 Marketing Analytics Portfolio Project
 
> A comprehensive end-to-end marketing analytics solution covering **conversion analysis**, **social media performance**, **customer sentiment**, and **data-driven recommendations** across 2023–2025.
 
---
 
## 🗂️ Project Overview
 
This project analyzes multi-year marketing performance for a sports & outdoor equipment brand. It combines SQL data extraction, Python-based sentiment analysis, and Power BI dashboards to uncover actionable insights across the customer journey — from awareness to purchase.
 
---
 
## 📁 Repository Structure
 
```
📦 Marketing_Analytics_Portfolio_Project
├── 📓 sentiment_analysis.ipynb          # Python notebook: VADER sentiment scoring
├── 📄 customer_reviews.csv              # Raw customer review data
├── 📄 fact_customer_reviews_with_sentiment.csv  # Enriched reviews with sentiment scores
├── 📄 engagement_data.csv               # Social media engagement metrics
├── 📄 customer_journey.csv              # Funnel data (View → Click → Purchase)
├── 📄 dim_product.csv                   # Product dimension table
├── 📄 dim_customer.xlsx                 # Customer dimension table
└── 📋 Marketing_Analytics_Portfolio_Project.pdf  # Full dashboard report
```
 
---
 
## 🛠️ Tech Stack
 
| Tool | Purpose |
|------|---------|
| 🐍 **Python** | Sentiment analysis (NLTK VADER) |
| 🗄️ **SQL Server** | Data storage & querying |
| 📊 **Power BI** | Interactive dashboards |
 
---
 
## 🔍 Key Analyses
 
### 1. 📈 Conversion Funnel Analysis
Tracks the customer journey across three stages: **View → Click → Purchase**
 
| Year | Conversion Rate | Views | Purchases | Purchase Rate |
|------|----------------|-------|-----------|---------------|
| 2023 | 51.0% | 708 | 82 | 11.58% |
| 2024 | 45.0% | 672 | 57 | 8.48% |
| 2025 | 45.0% | 690 | 59 | 8.55% |
 
> 💡 **Insight:** The largest drop-off occurs between the **click and purchase stages** — a prime area for optimization.
 
---
 
### 2. 📱 Social Media Performance
 
| Year | Views | Clicks | Likes |
|------|-------|--------|-------|
| 2023 | ~5M | ~1M | 336K |
| 2024 | ~3M | 458K | 73.6K |
| 2025 | ~1M | 68K | 4.3K |
 
> ⚠️ **Trend:** Significant year-over-year decline in reach and engagement — urgent need to revamp social media strategy.
 
---
 
### 3. 💬 Sentiment Analysis (VADER)
 
Sentiment scores are computed using **NLTK's VADER** model and combined with star ratings to produce nuanced sentiment categories:
 
| Category | Description |
|----------|-------------|
| ✅ **Positive** | Score > 0.05 AND Rating ≥ 4 |
| 🟡 **Mixed Positive** | Score > 0.05 AND Rating = 3, OR Score < -0.05 AND Rating ≥ 4 |
| 🔴 **Negative** | Score < -0.05 AND Rating ≤ 2 |
| 🟠 **Mixed Negative** | Score > 0.05 AND Rating ≤ 2, OR Score < -0.05 AND Rating = 3 |
| ⬜ **Neutral** | Score between -0.05 and 0.05 AND Rating = 3 |
 
**Sentiment Buckets:**
- `0.5 to 1.0` — Strongly positive
- `0.0 to 0.49` — Mildly positive
- `-0.5 to -0.01` — Mildly negative
- `-1.0 to -0.5` — Strongly negative
---
 
### 4. ⭐ Customer Review Trends
 
| Year | Avg Rating | Positive Reviews | Negative Reviews |
|------|-----------|-----------------|-----------------|
| 2023 | 3.73 / 5 | 273 | 63 |
| 2024 | 3.67 / 5 | 275 | 82 |
| 2025 | 3.66 / 5 | ~270+ | 81 |
 
> 🏆 **Top Products by Rating (2023):** Climbing Rope, Soccer Ball, Surfboard  
> 🏆 **Top Products by Rating (2025):** Ski Boots, Cycling Helmet, Climbing Rope
 
---
 
## 🚀 Getting Started
 
### Prerequisites
 
```bash
pip install pandas nltk openpyxl pyodbc
```
 
### Running Sentiment Analysis
 
```bash
# Open the Jupyter notebook
jupyter notebook sentiment_analysis.ipynb
```
 
The notebook will:
1. Connect to SQL Server and fetch `customer_reviews`
2. Apply VADER sentiment scoring to each review
3. Categorize sentiment using both score + star rating
4. Export results to `fact_customer_reviews_with_sentiment.xlsx`
### SQL Server Connection
 
Update the connection string in the notebook to match your environment:
 
```python
conn_str = (
    'Driver={ODBC Driver 18 for SQL Server};'
    'Server=(local);'
    'Database=PortfolioProject_MarketingAnalytics;'
    'Trusted_Connection=yes;'
    'TrustServerCertificate=yes;'
)
```
 
---
 
## 🏆 Top Performing Products (by Conversion Rate)
 
| Rank | 2023 | 2024 | 2025 |
|------|------|------|------|
| 🥇 1st | Hockey Stick (25.8%) | Ski Boots (24.0%) | Climbing Rope (27.1%) |
| 🥈 2nd | Ski Boots (20.8%) | Kayak (18.5%) | Surfboard (24.1%) |
| 🥉 3rd | Ice Skates / Tennis Racket (19.4%) | Surfboard / Volleyball (16.1%) | Hockey Stick (23.8%) |
 
---
 
## 💡 Key Recommendations
 
1. 🎯 **Double down on high-converting products** — Ski Boots, Hockey Stick, Climbing Rope, Surfboard
2. 📅 **Fix mid-year slumps** — Launch seasonal campaigns and limited-time offers in slow months
3. 📲 **Revamp social media** — Invest in short-form video, influencer collabs, and UGC campaigns
4. 🛒 **Optimize the click-to-purchase funnel** — Simplify checkout, add cart abandonment retargeting
5. ⭐ **Leverage positive reviews** — Use them in ads, banners, and email campaigns
6. 📝 **Scale blog & social content** — These channels outperform video consistently
7. 🔁 **Personalized retargeting** — Re-engage users who clicked but didn't convert
8. 📊 **Continuous A/B testing** — Test creatives, CTAs, and landing pages regularly
9. 🤝 **Build loyalty programs** — Rewards, referrals, and exclusive offers for repeat buyers
10. 📡 **Real-time performance tracking** — Monitor product and campaign KPIs monthly
---
 
## 📌 Seasonal Patterns Observed
 
- 📈 **January & September** consistently show the **highest conversion rates** across all years
- 📉 **May–July** is typically the **weakest period** for conversions and engagement
- 🎄 **Q4 recovery** is visible each year, likely driven by festive/holiday demand
---
