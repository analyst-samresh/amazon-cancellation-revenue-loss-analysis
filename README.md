# Amazon India— Cancellation & Revenue Loss Analysis(2022)

The analysis is focused on identifying the scale of financial impact - cancellation and revenue loss across Amazon India's full year 2022 sales data.ales data.

---

## Business Problem

**The Revenue Assurance Manager at Amazon India is concerned about revenue leakage from cancelled orders despite overall business growth. He wants to understand the scale of financial loss with actual numbers, "how many orders are being cancelled", "what is the total financial impact", and an assessment of whether the Cancellation & Revenue Loss rates are at an alarming stage or within a manageable range. He also needs to identify which geographies, product categories, sizes, and shipping types require priority attention.**

The goal is not to build a model — it is to understand the hidden pattern, scale of financial impact and area of improvement for business to action on it. work with.

---

## Dataset

- **Source:** Amazon India Sales Data — Full Year 2022 (Kaggle)
- **Size:** 1,28,975 orders (Jan 1 – Dec 31, 2022)
- **Key Fields:** Order ID, Date, Status, Category, Size, Fulfilment Type,
  Courier Status, Amount, Ship State

---

## Tools Used

- Python (Pandas, NumPy, Matplotlib, Seaborn)
- Jupyter Notebook
- Google Docs (Documentation)
- Excel (Initial data inspection)

---

## Data Cleaning Highlights

- Found 69 unique state values (expected ~28-36 Indian states), cleaned variations (e.g., "rajeshthan" → "Rajasthan", “ap” → “Arunachal Pradesh”, “pb” → “Punjab”) 
- Missing states are flagged as “Unknown”, final states 37 including “Unknown” 
- Missing amount is considered as cancelled if “status” contains (Cancelled, Returned and Rejected) 
- **Cancellation defined as:** Cancelled, Returned, Damaged, or Rejected orders

---

## Key Findings

### Overall Impact
| Metric | Value |
|---|---|
| Total Orders | 1,28,975 |
| Cancelled Orders | 20,441 (15.85%) |
| Revenue Expected | ₹7,85,92,678 |
| Revenue Lost | ₹82,96,548 (10.57%) |
| Avg. Loss per Cancellation | ₹406 |

### Where is the problem? (Geographic)
- Top 5 states — **Maharashtra, Karnataka, UP, Telangana, Tamil Nadu** — drive
  **54% of cancellations** and **53% of revenue loss**.
- These states have *lower* cancellation rates (14–17%) than remote areas,
  but their volume makes them the priority.
- Remote/hill states (Lakshadweep, Ladakh, Mizoram) show higher rates (18–30%)
  but minimal business impact

### Which categories? (Categorical)
- **Top 3 categories — Set, Kurta, Western Dress — account for 91% of
  cancellations and 92% of revenue loss**
- *Set* alone = 50% of total revenue loss (₹41.7L)
- Fixing the Set category would solve half the problem

### Is it getting worse/stable/improving? (Trend)
- Cancellation rate is **stable at 15–16% throughout the year** — this is a
  process/structural issue, not a seasonal one
- April–June shows a **7x spike in absolute cancellation numbers** — likely
  due to peak order volumes, not a rate change

---

## Recommendations

1. **Prioritise Top 5 states** — fixing Maharashtra and Karnataka alone addresses
   over 25% of revenue loss
2. **Deep-dive into Set category** — 50% revenue impact from one category is
   a clear starting point
3. **Investigate April–June spike** — understand if it's driven by promotions,
   demand surges, or fulfillment strain
4. **Add cancellation reason codes** — current data cannot differentiate
   customer-initiated vs system/logistics-initiated cancellations

---

## Project Structure
```
├── Amazon-raw-data-1.xlsx # Raw dataset
├── Initial_analysis.ipynb # Main analysis notebook
├── Initial-Analysis-Report.pdf # Full findings report
├── Project-Tracking.pdf # Project scope and tracking
├── charts/
│ ├── chart1_cancellation_revenue_overview.png
│ ├── chart2_top10_states.png
│ ├── chart3_monthly_trend.png
│ └── chart4_top3_categories.png
└── README.md
```

---

## Limitations

- ~6% of amounts are missing — treated conservatively (only counted as revenue
  loss when status confirmed cancellation)
- No cancellation reason codes available in raw data
- Cannot determine whether cancellations were customer-initiated or system-initiated

---

## Author

**Samresh Mandal** — Data Analyst  
LinkedIn : [https://www.linkedin.com/in/samresh-mandal/](#) |
GitHub : [https://github.com/analyst-samresh?tab=repositories](#)  
*Analysis completed: March 2026*
