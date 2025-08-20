# 🏦 Bank Loan Marketing Data Cleaning Project

## 📌 Overview
This project focuses on cleaning and preparing customer data from a **bank marketing campaign** aimed at promoting personal loans.  
The dataset (`bank_marketing.csv`) was transformed into structured, analysis-ready tables, making it easy to store in a **PostgreSQL database** and reuse for future campaigns.

---

## 📊 Dataset Description
The original dataset contained customer demographics, campaign contact history, and economic indicators.  
It was cleaned, reformatted, and split into **three tables**:

### 1. `client.csv`
| Column | Data Type | Description | Cleaning |
|--------|-----------|-------------|----------|
| client_id | integer | Unique client ID | N/A |
| age | integer | Client's age | N/A |
| job | object | Client's type of job | Replaced `.` with `_` |
| marital | object | Client's marital status | N/A |
| education | object | Client's level of education | Replaced `.` with `_`, converted `"unknown"` → `NaN` |
| credit_default | bool | Credit default | Converted `"yes"` → 1, else 0 |
| mortgage | bool | Mortgage flag | Converted `"yes"` → 1, else 0 |

---

### 2. `campaign.csv`
| Column | Data Type | Description | Cleaning |
|--------|-----------|-------------|----------|
| client_id | integer | Unique client ID | N/A |
| number_contacts | integer | Contacts in current campaign | N/A |
| contact_duration | integer | Duration of last contact (seconds) | N/A |
| previous_campaign_contacts | integer | Contacts in previous campaign | N/A |
| previous_outcome | bool | Outcome of previous campaign | `"success"` → 1, else 0 |
| campaign_outcome | bool | Outcome of current campaign | `"yes"` → 1, else 0 |
| last_contact_date | datetime | Last contact date | Combined **day, month, year=2022** → `YYYY-MM-DD` |

---

### 3. `economics.csv`
| Column | Data Type | Description |
|--------|-----------|-------------|
| client_id | integer | Unique client ID |
| cons_price_idx | float | Consumer price index |
| euribor_three_months | float | Euribor 3-month rate |

---

## 🛠️ Tools & Libraries
- **Python** (pandas, numpy)
- **Jupyter Notebook**
- **PostgreSQL** (target storage)
- **GitHub** (version control)

---

## 🚀 How to Reproduce
1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/python_data_cleaning.git
   cd python_data_cleaning

