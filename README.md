# 📊 Enterprise Lead Data Cleaning & Quality Control Dashboard

An end-to-end data cleaning, normalization, and quality assurance framework built entirely in Microsoft Excel. This project ingests raw CRM intake records, runs automated validation checks, normalizes data formats (including E.164 phone standards and deduplication), and presents key lead metrics on an Apple-inspired dark studio dynamic dashboard.

---

## 🎯 Key Capabilities & Architecture

The workbook is structured across three core processing layers:

1. **`Raw_Input`**:
   * Simulates direct CRM intake streams with unformatted text, inconsistent case formatting, mixed phone number inputs, syntax errors in email addresses, and duplicate entries.

2. **`Cleaning_Engine`**:
   * **Text Standardization**: Standardizes full names, first names, and last names into `Proper Case` via string manipulation (`TRIM`, `PROPER`, `TEXTJOIN`).
   * **Email Validation**: Evaluates syntax accuracy using string search logic (`SEARCH`, `ISNUMBER`) to flag invalid formats (`INVALID SYNTAX`).
   * **Deduplication Engine**: Flags primary vs. duplicate lead records dynamically.
   * **E.164 Phone Normalization**: Cleans whitespace and structures digits into standardized international format (`+1555XXXXXXX`).
   * **Lead Health Scoring**: Generates an automated 0–100 data quality score per record based on complete syntax compliance, phone presence, and duplicate checks.

3. **`Data_QualityDashboard`**:
   * High-end Dark Mode UI (`#121212` Obsidian canvas with `#1E293B` Slate card containers).
   * Key Metric KPI Summary Cards (**Total Leads**, **Valid Leads**, **Duplicates**, and overall **Data Health %**).
   * **Interactive Segment Filter Matrix**: Allows real-time table filtering (`All Records`, `Duplicates Only`, `Invalid Emails Only`, `Low Health (<70%)`) using dynamic `LET` and `FILTER` array logic without empty-row trailing zeros.

---

## 🛠️ Excel Formulas & Techniques Applied

* **Dynamic Array Formulas**: `FILTER`, `LET`, `SORT`, `INDEX`
* **Data Parsing & String Functions**: `TRIM`, `PROPER`, `LEN`, `SUBSTITUTE`, `LEFT`, `RIGHT`, `MID`
* **Logic & Error Handling**: `IF`, `AND`, `OR`, `ISNUMBER`, `SEARCH`, `IFERROR`
* **Aggregation**: `COUNTIF`, `COUNTIFS`, `COUNTA`, `AVERAGE`
* **UI/UX Design**: Custom Conditional Formatting (Red alert badges `#3B1212`), un-gridlined canvas, dark slate borders (`#334155`), and custom number formatting (`0;-0;;@`).

---

## 🖼️ Dashboard Preview

*(Add your screenshots under the `/assets` directory to render previews)*

| Sheet | Description |
| :--- | :--- |
| **Data Quality Dashboard** | Real-time monitoring cards and dynamic filtered output table. |
| **Cleaning Engine** | Line-by-line formula parsing and rule-based validation matrix. |
| **Raw Intake** | Uncleaned incoming CRM data stream. |

---

## 🚀 How to Run / Explore

1. Download or clone this repository:
   ```bash
   git clone [https://github.com/YOUR-Anish-85179/excel-lead-data-cleaning-dashboard.git](https://github.com/YOUR-USERNAME/excel-lead-data-cleaning-dashboard.git)
