# HR Attrition Analysis

**SQL + Power BI | HR Analytics | Retention & Cost Analysis**

## Business Question

**Which employee groups experience higher attrition, what patterns are associated with employee exits, and what is the potential financial exposure?**

This project analyzes employee attrition using SQL and Power BI to identify meaningful patterns across overtime, job satisfaction, tenure, income, department, and job role, and translates those findings into a financial cost model.

---

## Key Findings

- **16.1% overall attrition:** 237 of 1,470 employees have left.
- **Overtime shows the largest observed attrition gap:** 30.5% among employees working overtime vs. 10.4% among those not working overtime.
- **Overtime + low job satisfaction:** Employees with overtime and low job satisfaction have an observed historical attrition rate of **36.6%**.
- **$6.8M historical replacement-cost impact:** Using a replacement-cost assumption of **50% of annual salary** for the 237 historical leavers.
- **97 active employees match the identified risk profile:** These employees currently have overtime = Yes and job satisfaction ≤ 2.
- **$4.21M full replacement-cost exposure:** If all 97 active employees matching the profile were to leave, using the 50% replacement-cost assumption.
- **$1.54M expected at-risk cost:** Applying the historical 36.6% attrition rate of this employee segment to the replacement-cost exposure.

> **Important:** The identified pattern represents an observed historical association, not an individual-level prediction or causal estimate.

---

## Cost Model
The analysis uses a replacement-cost assumption of 50% of annual salary.

### Historical Replacement Cost

Replacement Cost = Annual Salary × 50%
Applying this to the 237 historical leavers results in an estimated
$6.8M historical replacement-cost impact.

### Expected At-Risk Cost
For the 97 currently active employees matching the identified risk profile:
Full Replacement-Cost Exposure = Σ(Annual Salary × 50%)
Expected At-Risk Cost = Full Replacement-Cost Exposure × 36.6%
This results in:
- 97 active employees
- $4.21M full replacement-cost exposure
- $1.54M expected at-risk cost
## Cost Sensitivity
The expected at-risk cost was tested under different replacement-cost assumptions:
| Replacement-Cost Assumption | Expected At-Risk Cost |
|---:|---:|
| 25% | $771K |
| 50% | $1.54M |
| 75% | $2.31M |
| 100% | $3.08M |

The **50% replacement-cost assumption** is used as the project's baseline.
---

## Potential Cost Avoidance

| Reduction in Segment Attrition | Potential Cost Avoidance |
|---:|---:|
| 5 percentage points | $211K |
| 10 percentage points | $421K |
| 15 percentage points | $632K |
| 20 percentage points | $843K |

These figures represent **potential cost exposure avoided**, not ROI, because the cost of implementing a retention intervention is not included.

---
## Dashboard
### 1. Overview
- Overall attrition
- Employees who left
- Historical replacement cost
- Department-level attrition
- Department-level cost impact

### 2. Evidence
- Overtime
- Tenure
- Job satisfaction
- Income quartiles
- Overtime + satisfaction analysis

### 3. Retention Risk & Financial Exposure
- 97 active employees matching the risk profile
- 36.6% historical segment attrition
- $4.21M full replacement-cost exposure
- $1.54M expected at-risk cost
- Cost sensitivity
- Potential cost avoidance
- Employee-level exposure table
---

## Tools Used

- **SQL / SQLite** — data exploration, segmentation, attrition analysis and cost calculations
- **Power BI** — dashboard development, visualization and financial analysis
- **DAX** — calculated measures and financial metrics
- **Excel/CSV** — dataset preparation and supporting analysis

---

## Repository Structure

HR-Attrition-Analysis/
│
├── data/
│   ├── RealDataset.csv
│   └── Analysed_dataset.csv
│
├── dashboard/
│   ├── HR_Attrition_Dashboard.pbix
│   └── HR_Attrition_Dashboard.pdf
│
├── sql/
│   └── attrition_analysis.sql
│
├── hr_attrition.db
├── hr_attrition.sqbpro
└── README.md
## Dataset
**IBM HR Analytics Employee Attrition & Performance dataset**
The dataset contains information on employee demographics, compensation, job characteristics, satisfaction, overtime, tenure and attrition status.

Records: 1,470 employees
Target field: Attrition
Source: Public IBM HR Analytics dataset available through Kaggle

## Business Interpretation

- Overtime and low job satisfaction show strong historical association with employee attrition.
- The analysis helps identify employee segments for further retention investigation.
- The financial model translates these patterns into potential business exposure.

## Limitations

- Historical, observational data does not establish causation.
- 36.6% is a segment-level rate, not an individual prediction.
- Financial estimates depend on the 50% replacement-cost assumption.
- Potential cost avoidance is not ROI because intervention costs are excluded.
