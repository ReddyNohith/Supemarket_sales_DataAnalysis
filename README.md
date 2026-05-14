# Supermarket Sales Analysis

A data analysis project that explores **100 supermarket transactions** across 3 branches and 3 cities in Myanmar (January – March 2019).

This project includes:
- A **Power BI dashboard** with interactive filters and KPI tiles
- A **Python Jupyter Notebook** built from scratch using only `pandas`, `numpy`, and `matplotlib`

---

## 📁 Project Structure

```
supermarket-sales-analysis/
│
├── supermarket_sales_data.csv        ← Raw dataset (100 rows, 13 columns)
├── supermarket_analysis.ipynb        ← Python notebook (16 steps, fully documented)
├── Supermarket_Sales_Analysis.pdf    ← Power BI dashboard export (2 pages)
└── README.md                         ← This file
```

---

## 📦 Dataset Overview

| Property | Details |
|----------|---------|
| Source | Supermarket point-of-sale (POS) records |
| Time Period | January 2019 – March 2019 |
| Total Rows | 100 transactions |
| Total Columns | 13 |
| Missing Values | None — dataset is fully clean |

### Column Reference

| Column | Type | Description |
|--------|------|-------------|
| `Invoice ID` | Text | Unique transaction identifier |
| `Branch` | Category | Store branch — A, B, or C |
| `City` | Category | City of the branch — Yangon, Mandalay, Naypyitaw |
| `Customer type` | Category | Member (loyalty card) or Normal (walk-in) |
| `Gender` | Category | Male or Female |
| `Product line` | Category | One of 6 product categories |
| `Unit price` | Numeric | Price per single item ($) |
| `Quantity` | Numeric | Number of items purchased |
| `Tax 5%` | Numeric | 5% tax on the subtotal (derived column) |
| `Total` | Numeric | Final amount paid including tax ($) |
| `Date` | Date | Transaction date |
| `Time` | Time | Transaction time (HH:MM) |
| `Payment` | Category | Cash, Credit card, or Ewallet |

### Unique Values per Category

| Column | Values |
|--------|--------|
| Branch | A (Yangon), B (Naypyitaw), C (Mandalay) |
| City | Yangon, Mandalay, Naypyitaw |
| Customer type | Member, Normal |
| Gender | Male, Female |
| Payment | Credit card, Ewallet, Cash |
| Product line | Food and Beverages, Health and Beauty, Sports and Travel, Fashion Accessories, Electronic Accessories, Home and Lifestyle |

---

## 📊 Power BI Dashboard

The dashboard is exported as a 2-page PDF and covers all major dimensions of the dataset with interactive slicers.

### Page 1 — Overview & KPIs

**KPI Tiles (top row)**

| Metric | Full Dataset | Filtered View* |
|--------|-------------|----------------|
| Total Sales | $31,271.51 | $17.48K |
| Average Sales | $312.72 | $336.09 |
| Total Transactions | 100 | 52 |
| Total Quantity | 565 | 312 |
| Total Tax | $1,489.17 | $832.29 |

> *The dashboard screenshot was captured with the **Product line = Home and Lifestyle** slicer active, which explains the lower filtered values shown in the PDF.

**Charts on Page 1**

| Chart | Type | What It Shows |
|-------|------|---------------|
| Total Sales by Date | Line chart | Day-by-day revenue trend across Jan–Mar |
| Total Sales by Product Line | Horizontal bar | Revenue comparison across all 6 product categories |
| Total Sales by Branch | Bar chart | Revenue for Branch A, B, and C side by side |
| Total Sales by City | Pie chart | City-wise revenue share — Yangon 40.65%, Mandalay 33.93%, Naypyitaw 25.43% |
| Total Transactions by Payment | Donut chart | Payment method split — Credit card 48%, Ewallet 30.77%, Cash 21.15% |
| Total Sales by Customer Type | Horizontal bar | Member vs Normal customer spend comparison |

### Page 2 — Customer & Time Analysis

**Charts on Page 2**

| Chart | Type | What It Shows |
|-------|------|---------------|
| Total Transactions by Gender | Pie chart | Female 57.14% vs Male 42.86% of all transactions |
| Total Sales by Time Category | Bar chart | Evening vs Morning sales volume comparison |
| Total Sales by Month | Area chart | Monthly revenue trend — January, February, March |

**Slicers available on Page 2:** Month, Payment, Gender, City, Product line, Branch

---

## 🐍 Jupyter Notebook Walkthrough

**File:** `supermarket_analysis.ipynb`
**Libraries:** `pandas` · `numpy` · `matplotlib` only

The notebook is written in 16 clear steps, each with a short explanation and a chart or printed output. No external libraries or dashboards are needed.

### Step-by-Step Breakdown

| Step | Title | What Happens |
|------|-------|--------------|
| 1 | Import Libraries | Loads `pandas`, `numpy`, `matplotlib` and sets global chart style |
| 2 | Load the Dataset | Reads the CSV file and prints shape and first 5 rows |
| 3 | Understand the Columns | Shows all column names, data types, and missing value counts |
| 4 | Basic Statistics | Uses `numpy` to calculate total revenue, mean, median, std, min, max |
| 5 | Prepare Date & Time | Converts `Date` column to datetime; extracts `Month`, `Day`, `Hour` |
| 6 | Sales by Product Line | Groups by product line, sorts by revenue → horizontal bar chart |
| 7 | Sales by Branch & City | Branch bar chart + City pie chart side by side |
| 8 | Customer Type & Gender | Customer type bar chart + Gender pie chart |
| 9 | Payment Methods | Payment count bar chart + pie chart |
| 10 | Sales by Month | Monthly totals reindexed in calendar order → bar chart |
| 11 | Sales by Day of Week | Day-of-week totals ordered Mon–Sun → bar chart |
| 12 | Sales by Hour | Hourly revenue line chart with shaded fill area |
| 13 | Transaction Distribution | Histogram of all transaction totals with mean & median lines |
| 14 | Unit Price vs Total | Scatter plot + `numpy` correlation coefficient between price and total |
| 15 | Average Quantity per Product Line | Avg quantity horizontal bar chart |
| 16 | Summary of Key Findings | Printed summary of all top-level stats and performers |

### Chart Types Used

| Chart Type | Used In Steps |
|------------|--------------|
| Horizontal bar chart | 6, 7, 8, 15 |
| Vertical bar chart | 7, 9, 10, 11 |
| Pie chart | 7, 8, 9 |
| Line chart with fill | 12 |
| Histogram | 13 |
| Scatter plot | 14 |

---

## 💡 Key Insights

### Sales & Revenue

| # | Insight | Numbers |
|---|---------|---------|
| 1 | **Food & Beverages is the top product line** | $7,693 — nearly 2× the lowest category |
| 2 | **Home & Lifestyle is the weakest product line** | Only $3,947 across all 100 transactions |
| 3 | **Branch C (Mandalay) leads in total sales** | All three branches are competitive, but C edges ahead |
| 4 | **March shows a sharp revenue drop** | Jan: $14.5K → Feb: $15.6K → Mar: $1.1K (partial month data) |

### Customer Behaviour

| # | Insight | Numbers |
|---|---------|---------|
| 5 | **Normal customers spend more than Members** | Normal: $17,942 vs Member: $13,328 |
| 6 | **Male and Female transactions are nearly equal** | Male: 51, Female: 49 out of 100 |
| 7 | **Evening is the peak shopping time** | Highest hourly sales recorded around 19:00 |
| 8 | **Midday sees a sales dip** | Hours 12–14 consistently underperform |

### Transactions & Payment

| # | Insight | Numbers |
|---|---------|---------|
| 9 | **Credit card dominates payments** | 41 out of 100 transactions — 41% |
| 10 | **All three payment methods are widely used** | No single method has an overwhelming share |
| 11 | **Average transaction is $312.72** | Median is lower at $243 — distribution is right-skewed |
| 12 | **Unit price and quantity both drive totals** | Moderate positive correlation confirmed via `numpy` |

---

## 🚀 How to Run the Notebook

### Requirements

```bash
pip install pandas numpy matplotlib jupyter
```

### Steps

1. **Download both files** into the same folder:
   ```
   supermarket_sales_data.csv
   supermarket_analysis.ipynb
   ```

2. **Open the notebook:**
   ```bash
   jupyter notebook supermarket_analysis.ipynb
   ```

3. **Run all cells:**
   Go to `Kernel` → `Restart & Run All`

> Each cell is self-contained and runs in order from top to bottom. No additional setup is needed.

---

## 📌 Important Notes

- The `Tax 5%` column is a calculated field (5% of pre-tax subtotal). It was not used as an independent analysis variable in the notebook.
- The dashboard PDF was captured with a **slicer filter active** (Product line = Home and Lifestyle on Page 2), so its KPI numbers are lower than the notebook's full-dataset figures.
- The notebook analyses the **complete unfiltered dataset** (all 100 rows) to give an accurate overall picture.
- `Month`, `Day`, and `Hour` columns are created inside the notebook from the existing `Date` and `Time` columns — they are not in the original CSV.

---

## 👤 Author

| Field | Details |
|-------|---------|
| **Name** |P Reddy Nohith |
| **Email** |mailto.nohith@gmail.com |
| **GitHub** |https://github.com/ReddyNohith |
| **LinkedIn** |https://www.linkedin.com/in/reddynohith/ |

> Feel free to reach out for questions, feedback, or collaboration.
