# 🚨 Fraud Detection Analytics System

> End-to-end data analytics project — SQL · Python · Pandas · Matplotlib · Seaborn

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat&logo=python&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-Workbench-4479A1?style=flat&logo=mysql&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0-150458?style=flat&logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0?style=flat)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat)

---

## 📌 Problem Statement

Financial fraud costs businesses **over $400 billion annually** worldwide.
Early detection requires understanding *when*, *where*, and *how* fraudulent transactions occur.

This project analyzes **50,000 financial transactions** from the PaySim dataset to surface fraud patterns,
build risk segmentation models, and deliver **actionable business recommendations**
using a full SQL + Python analytics pipeline.

---

## 🗂️ Project Structure

```
fraud-detection-analytics/
│
├── data_50k.csv                  # Raw dataset (PaySim — Kaggle)
│
├── analysis_queries.sql          # All SQL queries (16 across 6 sections)
│
├── fraud_analysis.ipynb          # Full Jupyter notebook — run top to bottom
│
├── visuals/
│   ├── 01_fraud_vs_normal.png
│   ├── 02_amount_distribution.png
│   ├── 03_boxplot.png
│   ├── 04_heatmap.png
│   ├── 05_fraud_by_type.png
│   ├── 06_fraud_by_hour.png
│   ├── 07_risk_tiers.png
│   ├── 08_time_of_day.png
│   └── 09_balance_anomaly.png
│
└── README.md
```

---

## 🛠️ Tools & Technologies

| Category | Tools |
|---|---|
| Language | Python 3.10+ |
| Data Manipulation | Pandas, NumPy |
| Database | MySQL Workbench via SQLAlchemy + PyMySQL |
| Visualization | Matplotlib, Seaborn |
| Environment | Jupyter Notebook |
| Dataset | [PaySim — Kaggle](https://www.kaggle.com/datasets/ealaxi/paysim1) |

---

## ⚙️ Setup & Run

```bash
# 1. Clone repository
git clone https://github.com/YOUR_USERNAME/fraud-detection-analytics
cd fraud-detection-analytics

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn sqlalchemy pymysql jupyter

# 3. Add dataset
# → Download from: https://www.kaggle.com/datasets/ealaxi/paysim1
# → Rename to data_50k.csv and place in root folder

# 4. Configure MySQL (in Cell 4 of the notebook)
MYSQL_USER     = "root"
MYSQL_PASSWORD = "your_password"
MYSQL_HOST     = "127.0.0.1"
MYSQL_DB       = "fraud_db"

# 5. Run notebook
jupyter notebook fraud_analysis.ipynb
# → Run all cells top to bottom
# → Visuals auto-saved to /visuals/
```

---

## 📊 Analysis Process

### Phase 1 — Data Loading & SQL Setup
- Loaded 50K PaySim transactions from CSV into pandas
- Pushed dataset to **MySQL Workbench** via SQLAlchemy (industry-standard workflow)
- Ran baseline SQL queries: total counts, fraud rate, average amounts

### Phase 2 — Exploratory Data Analysis
- Visualized fraud vs. normal class distribution
- Analyzed transaction amount patterns via histograms and boxplots
- Built correlation heatmap to identify features most predictive of fraud

### Phase 3 — Advanced Pattern Detection
- **Time-based analysis** — fraud rate by hour and time-of-day bucket
- **Risk segmentation** — transactions categorized into 4 amount tiers
- **Behavioral analysis** — balance anomaly detection unique to fraudulent transactions

---

## 🔍 Key Findings

| Finding | Detail |
|---|---|
| 📉 Fraud Rate | A small fraction of transactions are fraudulent — but high financial impact |
| ⏰ Peak Fraud Window | Late-night hours (0–5 AM) show the highest fraud concentration |
| 💸 High-Value Risk | Critical-tier transactions (>$100K) carry significantly higher fraud rate |
| 🔄 Riskiest Type | TRANSFER and CASH_OUT transaction types account for nearly all fraud |
| 💰 Balance Zeroing | Fraud transactions consistently zero out the origin account balance |
| 🎯 Top Correlation | `old_bal_orig` and `new_bal_dest` most correlated with fraud label |

> 📌 Exact figures reflect actual dataset results — see notebook Cell 15 output.

---

## 💡 Business Recommendations

1. **Flag transactions > $10,000** for secondary review before processing
2. **Enforce step-up authentication** during late-night peak fraud window
3. **Auto-hold CASH_OUT & TRANSFER** above defined risk threshold pending review
4. **Real-time balance monitoring** — alert when origin balance drops to zero post-transaction
5. **ML pipeline opportunity** — heatmap features (`old_bal_orig`, `new_bal_dest`) are strong candidates for a fraud classifier

---

## 📈 Visualizations (9 Charts)

| # | Chart | Key Insight |
|---|---|---|
| 01 | Fraud vs Normal Count | Class imbalance — fraud is rare but impactful |
| 02 | Amount Distribution | Fraud clusters in mid-to-high amount range |
| 03 | Boxplot Comparison | Fraud has higher median amount + more outliers |
| 04 | Correlation Heatmap | Identifies top predictive features |
| 05 | Fraud by Txn Type | TRANSFER / CASH_OUT dominate fraud cases |
| 06 | Fraud by Hour | Clear spike in specific night hours |
| 07 | Risk Tier Segmentation | Critical tier carries highest fraud rate |
| 08 | Time-of-Day Buckets | Late-night window most dangerous |
| 09 | Balance Anomaly | Fraud zeroes out origin balance every time |

---

## 🧠 Skills Demonstrated

- ✅ **SQL Analytics** — 16 queries covering basic stats, time analysis, risk segmentation, anomaly detection
- ✅ **MySQL Workbench** — real database workflow, not just CSV in pandas
- ✅ **Python / Pandas** — data wrangling, feature engineering, aggregation
- ✅ **Data Visualization** — 9 dark-theme charts using Matplotlib + Seaborn
- ✅ **Business Intelligence** — findings translated into actionable recommendations
- ✅ **End-to-End Pipeline** — CSV → MySQL → SQL Queries → Python → Visuals → Insights

---

## 📁 Dataset

**PaySim Synthetic Financial Dataset** — Kaggle
→ Based on real mobile money transaction logs
→ Contains fraud labels, transaction types, amounts, and balance data
→ [Download here](https://www.kaggle.com/datasets/ealaxi/paysim1)

---

## 👤 Author

**[AKASH NAGAR]**
Aspiring Data Analyst | SQL · Python · MySQL · Visualization
[LinkedIn](https://linkedin.com/in/akash-nagar-b06b20244) · [GitHub](https://github.com/techakash32/fraud-detection-analytics)

---

*Built as a portfolio project to demonstrate real-world data analytics skills.*
