# Fuse AI Fellowship — Week 1 Session Guide
**Aaradhya Dev Tamrakar | AI Fellowship 2026**
**Deadline: May 4, 2026 — 23:59**

---

## What This Week Is

Week 1 is called **Data Wrangling** but it's actually testing two things at once:

1. Can you think like a data scientist — not just execute code, but justify decisions?
2. Can you use AI tools as a real workflow accelerator, not a crutch?

You have **two graded deliverables** and one self-paced checklist to progress through at your own pace.

---

## Deliverable 1 — Data Wrangling Notebook (Python)

### The Scenario
You are a Data Scientist at a Regional Health Center. You have three messy CSV files from separate systems that need to be cleaned and merged into one analysis-ready dataset.

| File | System | What it contains |
|---|---|---|
| `patient_demo.csv` | Administrative | Patient demographics — IDs, age, gender, admission info |
| `clinical_data.csv` | Lab | Clinical measurements — blood pressure, glucose, etc. |
| `lifestyle_factors.csv` | Lifestyle | Patient lifestyle data — smoking, exercise, diet, etc. |

### Your Job
1. **Inspect** each file — shape, columns, dtypes, nulls, sample rows
2. **Clean** — handle missing values, fix anomalies, resolve format issues (e.g., BP stored as "120/80" string)
3. **Standardize** — consistent date formats, categorical values, numeric ranges
4. **Merge** — join the three datasets on Patient ID into one clean master table
5. **Document** — every decision gets a markdown cell explaining *why*

### The Decision Framework (this is what separates good from average)

For every cleaning step, ask and answer inside the notebook:
- *What is the problem?*
- *What are my options?*
- *What did I choose and why?*

Example for missing age values:
> "3.2% of age values are missing. Options: drop rows, impute with mean, impute with median, or flag as unknown. I chose **median imputation** because the age distribution shows right skew (mean pulled up by elderly outliers), making median more representative of the typical patient."

That one paragraph puts you above 80% of submissions.

### Blood Pressure Parsing (the technical trick they're testing)
BP is stored as a string like `"120/80"`. You need to split it:

```python
df[['bp_systolic', 'bp_diastolic']] = df['blood_pressure'].str.split('/', expand=True).astype(float)
```

Watch for: nulls, malformed entries like `"--"` or `"N/A"`, values outside physiological range (systolic < 50 or > 250 is suspicious).

### Notebook Structure Template

```
1. Setup & Imports
2. Load Data
   - Load each CSV
   - Print shape, dtypes, .head(), .info(), .describe()
   - Document observations
3. Structural Inspection
   - Check for duplicates
   - Check column name consistency across files
   - Check Patient ID format across files
4. Cleaning — Patient Demographics
   - [decisions with justification]
5. Cleaning — Clinical Data
   - [BP parsing + decisions]
6. Cleaning — Lifestyle Factors
   - [decisions]
7. Merge
   - Join strategy (inner/left/outer — justify your choice)
   - Post-merge validation (row count check, null check)
8. Final Dataset Validation
   - Shape, nulls, dtypes of final df
   - .describe() on key columns
9. Export
   - Save as clean_patient_data.csv
10. Summary
    - What was messy, what you did, key decisions made
```

---

## Deliverable 2 — SQL Fundamentals (Classic Models DB)

### Setup
```sql
-- In MySQL terminal
mysql> source C:/path/to/mysqlsampledatabase.sql;
```

The database has 8 tables: `customers`, `orders`, `orderdetails`, `products`, `productlines`, `employees`, `offices`, `payments`.

### Key Tasks to Complete

**CASE statements — data cleaning/transformation:**
```sql
-- Example: Classify customers by credit limit
SELECT customerName,
  CASE
    WHEN creditLimit >= 100000 THEN 'High Value'
    WHEN creditLimit >= 50000 THEN 'Mid Value'
    ELSE 'Low Value'
  END AS customer_tier
FROM customers;
```

**JOINs — connecting customers to orders:**
```sql
-- Customers with their total orders and payment amounts
SELECT c.customerName, COUNT(o.orderNumber) AS total_orders,
       SUM(p.amount) AS total_paid
FROM customers c
LEFT JOIN orders o ON c.customerNumber = o.customerNumber
LEFT JOIN payments p ON c.customerNumber = p.customerNumber
GROUP BY c.customerNumber, c.customerName
ORDER BY total_paid DESC;
```

**Aggregations — business metrics:**
```sql
-- Top 5 employees by revenue generated
SELECT e.firstName, e.lastName,
       SUM(od.quantityOrdered * od.priceEach) AS revenue
FROM employees e
JOIN customers c ON e.employeeNumber = c.salesRepEmployeeNumber
JOIN orders o ON c.customerNumber = o.customerNumber
JOIN orderdetails od ON o.orderNumber = od.orderNumber
GROUP BY e.employeeNumber
ORDER BY revenue DESC
LIMIT 5;
```

### Log Your SQL Errors
Keep a running log in a `.md` or `.txt` file:
```
ERROR: Column 'salesRepEmployeeNumber' doesn't exist
FIX: Checked schema with DESC customers; — correct column name confirmed
LEARNING: Always DESC the table before writing JOINs cold
```
This journal is explicitly required and signals you're learning, not just copy-pasting.

---

## Self-Paced Checklist — Where Week 1 Fits

The fellowship has a 19-section Data Lifecycle checklist. Week 1 covers primarily:

- **Section 7: Clean and Preprocess Data** ← this week's core
- **Section 6: Model Data with Clear Schemas** ← SQL assignment
- **Section 1: Understand the Full Data Lifecycle** ← background context

Don't try to complete the full checklist this week. Tick what you genuinely understand after completing the two assignments. Honesty in self-assessment matters — Fusemachines will evaluate against it.

---

## AI Tools the Fellowship Wants You To Use

| Tool | Use it for |
|---|---|
| **Gemini Gem (Data Architect)** | Simulate scenarios, get step-by-step guidance when stuck on a cleaning decision |
| **NotebookLM (Data Wrangling)** | Ask targeted questions, self-quiz on concepts |
| **Me (Claude)** | Code review, decision justification, SQL query building, concept explanation |

You are **explicitly encouraged** to use AI. The differentiation is in your reasoning and documentation, not in writing code from scratch.

---

## The One Thing That Wins This Week

Most fellows will submit a notebook that runs cleanly with some comments.

You will submit a notebook where **every non-obvious decision has a written justification**. Same technical work, 10x better signal to the reviewers that you think like a data scientist.

---

## This Week's Timeline (May 4 deadline)

| Day | Task |
|---|---|
| Today (Apr 29) | Download files, set up environment, do initial inspection of all 3 CSVs |
| Apr 30 | Clean each CSV individually, document decisions |
| May 1 | Merge + validate + export clean dataset |
| May 2 | SQL setup + complete all 3 SQL tasks + error log |
| May 3 | Review notebook documentation, polish, double-check submission format |
| May 4 | Submit before 23:59 |

---

## Quick Reference — Key Pandas Commands for Inspection

```python
import pandas as pd

df = pd.read_csv('patient_demo.csv')

# Initial inspection
print(df.shape)
print(df.dtypes)
print(df.head())
print(df.info())
print(df.describe())

# Missing values
print(df.isnull().sum())
print(df.isnull().mean() * 100)  # as percentage

# Duplicates
print(df.duplicated().sum())

# Value counts for categorical
print(df['gender'].value_counts())
```

---

*Generated: April 29, 2026 | Next update: after files are inspected*
