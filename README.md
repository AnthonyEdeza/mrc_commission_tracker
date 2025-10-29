# 💰 MRC Commission Tracker
### Automating the Processing of Monthly Recurring Commission Reports

**Tech Stack:** Python · Pandas · NumPy · XlsxWriter · Regex · Calendar · Google Colab

---

## 🔍 Executive Summary
The **MRC Commission Tracker** automates the monthly consolidation and calculation of **recurring commission payments** across multiple CSV reports.  
It was designed to eliminate repetitive manual work in tracking multi-month payment cycles and determining expected future commission dates.

Using **Python (Pandas)** inside **Google Colab**, this workflow:
- Reads all monthly commission CSVs in the working directory.  
- Cleans and filters data to exclude inactive or zero-balance accounts.  
- Calculates **future MRC payment dates** (2nd MRC → +48 days, 3rd MRC → +96 days, 4th MRC → +144 days).  
- Compiles all processed data into a single Excel workbook with separate sheets per period.  

This automation replaced a repetitive spreadsheet process and provided a repeatable, structured method to forecast MRC payouts with improved accuracy and speed.

---

## 💼 Business Problem
Commission analysts previously relied on manually combining exported reports, which led to:
- Inconsistent date calculations across months.  
- Difficulty identifying active vs. deactivated accounts.  
- Frequent formula and copy-paste errors.  
- Hours of repetitive cleanup for every commission cycle.

---

## 💡 Solution
The **MRC Commission Tracker** automates the entire workflow:  

1. **Import:** Reads all `.csv` files in the current working directory.  
2. **Clean:** Filters out entries with `0 Total Commissions to Date`, null `Deactivation Date`, or `ACP` plans.  
3. **Transform:** Calculates subsequent MRC payment milestones based on the first payment date.  
4. **Load:** Outputs a single consolidated Excel file with three sheets — 2nd MRC, 3rd MRC, and 4th MRC forecasts.  
5. **Export:** Downloads the combined workbook directly from Google Colab.

---

## 🧰 Tools and Methods

| Stage | Purpose | Libraries / Tools |
|-------|----------|-------------------|
| Data Ingestion | Read multiple CSV files | `pandas`, `os`, `re` |
| Data Filtering | Remove inactive / zero-commission entries | `pandas` queries |
| Date Calculations | Compute 2nd → 4th MRC payment dates | `pandas`, `datetime`, `timedelta` |
| Data Output | Write multi-sheet Excel file | `xlsxwriter`, `pandas.ExcelWriter` |
| Environment | Notebook automation / file download | `Google Colab` |

---

## 📂 Input Data

This notebook expects CSV files exported from a commission reporting system.  
Each file typically follows this naming pattern:

mmmYYYYHHMM.csv

For testing purposes, **three sanitized CSVs** are included in this repository:  
jun20230905_SANITIZED.csv
jul20230915_SANITIZED.csv
aug20230915_SANITIZED.csv
---

## 🧾 Example Output
> 🧩 **Output:** `combined_mrc_sheets.xlsx`  
> A consolidated Excel workbook generated automatically by the script.  
> Each sheet (e.g., `Jan_2nd MRC`, `Jan_3rd MRC`, `Jan_4th MRC`) contains all qualifying accounts and projected commission dates.
> ⚠️ *Note:* These are **fully sanitized test files** that contain randomly generated, non-identifiable data.  
> They are safe for public demonstration and reproduce the same structure as the original datasets.

---

## ⚙️ How to Run

### Option 1 — Google Colab
1. Upload `mrc_commission_tracker.ipynb` to your Google Drive.  
2. Open in **Google Colab**.  
3. Upload your monthly CSV files into the Colab working directory.  
4. Run all cells.  
5. When complete, the combined Excel file will automatically download to your device.

### Option 2 — Local Execution (optional)
You can also run it locally with:
```bash
python mrc_commission_tracker.ipynb
(requires Python ≥ 3.9, pandas, xlsxwriter)

🧠 Skills Demonstrated
Data Cleaning & Filtering with Pandas

Date-based Forecasting Logic for commission cycles

Excel Automation using multi-sheet output

Regex and String Parsing for file identification

Scalable Notebook Design for Google Colab automation

🧭 Next Steps
Integrate a summary sheet showing total commissions per brand / rep.

Automate file retrieval from Google Drive API or SFTP folder.

Add Power BI visualizations for monthly commission trend tracking.

⚖️ Notes
All data in this repository is synthetic and privacy-safe.
No proprietary or confidential client information is included.
This project exists solely for educational and portfolio demonstration purposes.

👤 Created by Anthony Edeza
📧 AnthonyEdeza.Data@gmail.com

## 🧩 Recruiter Note

If you’re evaluating this portfolio:

This project demonstrates how Python scripting and data automation can streamline repetitive operational reporting.  
It highlights practical skills in **data wrangling**, **business rule logic**, and **Excel automation** using real-world commission workflows.  
It reflects analytical thinking and automation design applied to everyday operational problems—exactly the kind of bridge between IT and data analytics that drives process improvement.

---

## 🏁 Summary

The **MRC Commission Tracker** automates recurring commission tracking and forecasting, eliminating hours of manual spreadsheet work.  
It demonstrates how structured data logic can replace repetitive human tasks while preserving accuracy and consistency across reporting cycles.  
This project showcases the foundation of scalable automation—turning operational bottlenecks into clean, reusable, and data-driven solutions.
