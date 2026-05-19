# 📊 B2B SaaS Funnel Analytics Dashboard

A full-stack analytics project that explores a synthetic B2B SaaS sales funnel — from raw lead data to an interactive Streamlit dashboard. Built as a data science portfolio project covering EDA, funnel analysis, and business intelligence visualization.

---

## 🚀 Live Demo

> Coming soon — deploy link will be added after Streamlit Cloud deployment.

---

## 📌 Project Overview

This project simulates a real-world B2B SaaS sales pipeline and answers key business questions:

- Where are leads dropping off in the funnel?
- Which company sizes convert the best?
- Does speed from MQL → Demo Booking affect win rate?
- Which months/quarters drive the most revenue?

The project is split into two scripts:

| File | Purpose |
|---|---|
| `quick_eda.py` | Exploratory Data Analysis — terminal-based, quick insights |
| `app.py` | Interactive Streamlit dashboard with Plotly visualizations |

---

## 📁 Project Structure

```
saas-funnel-analytics/
│
├── app.py                    # Streamlit dashboard (main app)
├── quick_eda.py              # EDA script (run in terminal)
├── requirements.txt          # Python dependencies
├── .gitignore
├── README.md
│
├── Dataset/
│   └── saas_funnel_data.csv  # Synthetic B2B SaaS funnel dataset
│
└── assets/
    ├── Company size.png
    ├── Demo booking.png
    ├── Funnel Breakdown.png
    └── Monthly Funnel Trend.png
```

---

## 🔍 Features

### EDA (`quick_eda.py`)
- Dataset shape, dtypes, null values
- Funnel stage distribution with drop-off percentages
- Lead source breakdown and source × stage cross-tab
- Revenue stats (total, avg, median, max deal size)
- Sales rep lead distribution
- Speed-to-demo analysis (days MQL → Demo Booking)

### Dashboard (`app.py`)
- **Sidebar filters** — Date range, Company Size, Sales Rep
- **KPI bar** — Total Leads, Closed Won, Total Revenue, Win Rate, Churn Rate
- **Funnel chart** — Full 6-stage funnel with % drop-off labels
- **Company size chart** — Lead volume + win rate dual-axis bar chart
- **Speed analysis** — Fast vs. Slow follow-up comparison table + histogram
- **Monthly trend** — Q4 highlighted bar chart with win rate overlay

---

## 🛠️ Tech Stack

| Tool | Use |
|---|---|
| Python 3.10+ | Core language |
| Pandas | Data wrangling |
| NumPy | Numerical operations |
| Streamlit | Dashboard framework |
| Plotly | Interactive charts |
| Matplotlib / Seaborn | EDA static plots |

---

## ⚙️ Setup & Run

### 1. Clone the repo
```bash
git clone https://github.com/mdshafi-786/saas-funnel-analytics.git
cd saas-funnel-analytics
```

### 2. Create a virtual environment (recommended)
```bash
python -m venv venv
source venv/bin/activate        # Mac/Linux
venv\Scripts\activate           # Windows
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Dataset
The dataset is already included in the repo at:
```
Dataset/saas_funnel_data.csv
```
> See the [Dataset Schema](#-dataset-schema) section below for column details.

### 5. Run EDA
```bash
python quick_eda.py
```

### 6. Launch the dashboard
```bash
streamlit run app.py
```

---

## 📂 Dataset Schema

The dataset (`saas_funnel_data.csv`) is synthetic and contains the following columns:

| Column | Type | Description |
|---|---|---|
| `lead_id` | string | Unique lead identifier |
| `created_date` | date | Date lead was created |
| `mql_date` | date | Date lead became MQL (nullable) |
| `demo_booked_date` | date | Date demo was scheduled (nullable) |
| `demo_completed_date` | date | Date demo was held (nullable) |
| `trial_start_date` | date | Date trial began (nullable) |
| `closed_date` | date | Date deal was closed (nullable) |
| `current_stage` | string | Final stage: Lead / MQL / Demo Booked / Trial Started / Closed Won / Churned |
| `company_size` | string | Startup / SMB / Mid-Market / Enterprise |
| `lead_source` | string | Organic / Paid / Referral / Outbound etc. |
| `sales_rep` | string | Assigned sales representative |
| `deal_value` | float | Revenue from closed deals (0 for open/lost) |
| `days_mql_to_demo_booked` | float | Days between MQL and demo booking (nullable) |

> ⚠️ This dataset is **synthetic** — generated for educational/portfolio purposes only.

---

## 📈 Key Insights (Sample Findings)

- **Fastest conversion segment:** Enterprise leads have the highest win rate despite lower volume
- **Speed matters:** Leads contacted within 4 days of becoming MQL convert significantly better
- **Q4 effect:** October–December shows elevated lead volume and win rate
- **Top lead source:** Referrals close at a higher rate than paid acquisition channels

---

## 🙋‍♂️ Author

**Mohammed Shafiulla**
BCA Data Science · Aditya Degree College, Visakhapatnam

[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?style=flat&logo=github)](https://github.com/mdshafi-786)


---

## 📄 License

This project is open source under the [MIT License](LICENSE).

---

> ⭐ If you found this useful, consider starring the repo!
