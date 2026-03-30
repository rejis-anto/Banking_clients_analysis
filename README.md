# 🏦 Banking Client Behavior Analysis

> An end-to-end data analytics project analyzing 3,000 banking clients to uncover insights on loyalty segmentation, risk profiling, income distribution, financial product holdings, and relationship patterns.

---

## 🧰 Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-3776AB?style=for-the-badge&logo=python&logoColor=white)

---

## 📌 Project Overview

This project follows a complete data analytics pipeline on real-world banking client data:

1. **Data Cleaning & EDA** — Python, Pandas, Matplotlib & Seaborn in Jupyter Notebook
2. **Feature Engineering** — Income Band classification, date conversion, snake_case standardization
3. **Database Integration** — Loaded cleaned data into MySQL via SQLAlchemy + pymysql
4. **SQL Analysis** — 10 business queries to answer key banking and client questions
5. **Dashboard** — Interactive Power BI dashboard with KPI cards, 7 visuals, and 6 slicers

---

## 📂 Repository Structure

```
banking-client-behavior-analysis/
│
├── data/
│   └── Banking_dataset.csv                           # Raw dataset (3,000 records, 28 features)
│
├── notebooks/
│   └── banking_analysis.ipynb                        # Full EDA + MySQL integration notebook
│
├── dashboard/
│   └── banking_analysis_dashboard.pbix               # Power BI dashboard file
│
├── report/
│   └── Banking_Client_Behavior_Analysis_Report.docx  # Full project report
│
└── README.md
```

---

## 📊 Dataset Summary

| Attribute | Details |
|-----------|---------|
| Total Records | 3,000 banking clients |
| Total Features | 28 columns |
| Missing Data | None — fully complete dataset |
| Age Range | 17 – 85 years (Mean: 51) |
| Estimated Income | $15,919 – $522,330 (Mean: $171,305) |
| Bank Loans | $0 – $2,667,557 (Mean: $591,386) |
| Bank Deposits | $0 – $3,890,598 (Mean: $671,560) |
| Gender Split | Female: 1,512 (50.4%) \| Male: 1,488 (49.6%) |

**Feature Groups:**
- **Demographics** — Client ID, Name, Age, Gender, Nationality, Occupation, Location ID, Joined Bank
- **Banking Relationship** — Banking Contact, Relationship Type, Investment Advisor, Fee Structure, Loyalty Classification
- **Financial Holdings** — Estimated Income, Superannuation Savings, Credit Card Balance, Bank Loans, Bank Deposits, Checking/Saving Accounts, Foreign Currency Account, Business Lending
- **Risk & Property** — Risk Weighting (1–5), Properties Owned (0–3), Amount of Credit Cards

---

## 🔬 Exploratory Data Analysis (Python)

Performed in `banking_analysis.ipynb`:

- ✅ Loaded dataset using `pandas.read_csv()`
- ✅ Confirmed 3,000 rows × 28 columns with `df.shape` and `df.info()`
- ✅ **No missing values** found across all 28 columns
- ✅ Standardized all column names to `snake_case` using `.str.strip()`, `.str.lower()`, `.str.replace()`
- ✅ Converted `joined_bank` from string to proper datetime using `pd.to_datetime()`
- ✅ Engineered `income_band` column (Low / Mid / High) using `pd.cut()` on `estimated_income`
- ✅ Conducted univariate analysis with histograms (KDE) for all 9 numerical financial columns
- ✅ Generated countplots for 9 categorical columns including Risk Weighting, Nationality, Fee Structure
- ✅ Built a full correlation heatmap using Seaborn for all numerical features
- ✅ Created 7 regression scatter plots (sns.regplot) for key financial column pairs
- ✅ Exported cleaned DataFrame to MySQL using `SQLAlchemy` + `pymysql`

---

## 🗄️ SQL Analysis (MySQL)

10 business queries executed in MySQL on the `banking_analysis` database:

| # | Query | Key Finding |
|---|-------|-------------|
| 1 | Loyalty Classification Distribution | Jade: 44.4% — Platinum: only 10.6% |
| 2 | Revenue by Fee Structure | 49.2% of clients are on High fee structure |
| 3 | Banking Relationship Breakdown | Private Bank leads at 45.1% of clients |
| 4 | Risk Profile Distribution | 68.6% are at Risk Level 1 or 2 (low risk) |
| 5 | Income Band vs Avg. Bank Deposits | High earners deposit 3× more than Low earners |
| 6 | Nationality Breakdown | European 43.6%, Asian 25.1%, American 16.9% |
| 7 | Credit Card Holding Distribution | 64% of clients hold only 1 credit card |
| 8 | Properties Owned Distribution | Evenly split across 0–3 properties (~750 each) |
| 9 | Superannuation by Age Group | Seniors hold 2.5× more savings than young clients |
| 10 | High-Risk Clients with High Loans | 278 clients flagged for enhanced risk monitoring |

---

## 📈 Power BI Dashboard

The dashboard (`banking_analysis_dashboard.pbix`) includes:

**KPI Cards**
- 👥 Total Clients: **3,000**
- 💰 Avg Estimated Income: **$171,305**
- 🏦 Avg Bank Deposits: **$671,560**
- 📉 Avg Bank Loans: **$591,386**
- 💳 Avg Credit Card Balance: **$3,176**

**Visuals**
- Loyalty Classification — Donut Chart
- Income Band — Bar Chart (Low / Mid / High)
- Banking Relationship Type — Bar Chart
- Nationality Distribution — Chart
- Risk Weighting Distribution — Bar Chart
- Financial Holdings Comparison — Grouped Bar Chart
- Fee Structure Breakdown — Proportional Chart

**Slicers (Filters)**
- Gender, Nationality, Loyalty Classification, Fee Structure, Banking Relationship, Risk Weighting

---

## 💡 Key Findings

- 📌 **Only 10.6% of clients are Platinum tier** — 70% are still in Jade or Silver, a major loyalty upgrade opportunity
- 📌 **64% of clients hold just 1 credit card** — significant cross-sell potential for premium card products
- 📌 **45% of clients are Private Bank clients** — strong positioning in the high-net-worth segment
- 📌 **High income band clients deposit 3× more** ($1.21M vs $362K) than Low income clients
- 📌 **278 high-risk clients also carry above-average loans** — concentrated portfolio risk requiring monitoring
- 📌 **Business Lending and Bank Loans are most strongly correlated** — business borrowers carry multi-product debt
- 📌 **Superannuation savings grow 2.5× from young to senior clients** — clear opportunity for retirement product targeting

---

## 🚀 Business Recommendations

| Recommendation | Action |
|----------------|--------|
| 🏆 Loyalty Upgrade Program | Target Jade/Silver clients with milestone rewards to advance tiers |
| 💳 Cross-Sell Credit Cards | Campaign for premium second cards to 1,922 single-card clients |
| ⚠️ High-Risk Monitoring | Enhanced oversight for 278 clients with Risk 4-5 + high loans |
| 💼 Wealth Management Expansion | Build out services for high income band / Private Bank clients |
| 🏠 Retirement Products for Seniors | Push pension and estate planning for the 55+ age segment |
| 🌍 Multilingual Regional Strategy | Tailor services for European (43.6%) and Asian (25.1%) segments |
| 📈 Target High-Income Deposits | Develop term deposit and investment products for $300K+ earners |

---

## ▶️ How to Run

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn sqlalchemy pymysql jupyter
```

### Steps

1. Clone the repository
```bash
git clone https://github.com/your-username/banking-client-behavior-analysis.git
cd banking-client-behavior-analysis
```

2. Launch Jupyter Notebook
```bash
jupyter notebook notebooks/banking_analysis.ipynb
```

3. Set up MySQL — update the connection string in the notebook with your credentials:
```python
engine = create_engine("mysql+pymysql://<username>:<password>@localhost:3306/banking_analysis")
```

4. Open the Power BI dashboard
```
dashboard/banking_analysis_dashboard.pbix
```
> Requires Power BI Desktop (free download from Microsoft)

---

## 👤 Author

REJIS ANTO.M

Aspiring Data Analyst

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/rejisanto)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/rejis-anto)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
