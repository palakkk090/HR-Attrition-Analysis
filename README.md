# HR-Attrition-Analysis
Using SQL + Power BI

## Business Question
Which employees are we losing, why, and what is it costing the company?

## Key Findings
- Overall attrition rate: 16.1% (237 of 1,470 employees)
- Overtime is the strongest attrition driver: 30.5% vs 10.4% (non-overtime)
- Combined with low job satisfaction, attrition rises to 36.6%
- Estimated cost of attrition: $6.8M (note: i have used 50% of annual salary replacement-cost model for this analysis)
- 97 currently active employees match the high-risk profile, projecting $1.54M in expected avoidable cost (full replacement cost × the segment's own 36.6% observed attrition rate)

## Cost Model Methodology
- Historical cost (actual leavers): full replacement cost = 50% of annual salary, no discounting needed since it already happened.
- Projected at-risk cost (currently active employees): expected cost = full replacement cost × the segment's own observed attrition rate (36.6%), not a mismatched lower rate — this was a bug in the original v1 model, now fixed in SQL 13 (see `hr_attrition.sqbpro`).
- Sensitivity: costs range from $771K (25% replacement assumption) to $3.08M (100% replacement assumption) at the 50% baseline used above.
- Intervention ROI: a program that cuts this segment's attrition rate by 10 points would avoid ~$421K in expected cost — see SQL 15 in `hr_attrition.sqbpro` for the full table.

## Tools Used
SQL (SQLite/DB Browser) for analysis
 Power BI for visualization

## Files
- `/sql/attrition_analysis.sql` — all analysis queries
- `/dashboard/HR_Attrition_Dashboard.pbix` — full interactive dashboard
- `/data/Analysed_dataset.csv` — enriched dataset used in Power BI
- - `hr_attrition.sqbpro` — DB Browser for SQLite project file containing all analysis queries (SQL 1–10 original diagnostics, SQL 11–15 fixed cost model with sensitivity and intervention ROI)
- `hr_attrition.db` — working SQLite database (import RealDataset.csv into an `employee` table to rebuild if needed)

## Approach
1. Explored the IBM HR Analytics dataset (1,470 employees) in SQL
2. Tested attrition rate across department, role, tenure, income, overtime, and satisfaction
3. Identified overtime + low satisfaction as the strongest actionable combination
4. Built a cost-of-attrition model to translate headcount loss into dollar impact
5. Flagged currently active employees matching the high-risk profile for proactive retention outreach

## Dataset Source
[IBM HR Analytics Employee Attrition dataset](Kaggle link) (public)

-`/data/Real_dataset.csv` - real dataset got from kaggle link
