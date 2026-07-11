# HR-Attrition-Analysis
Using SQL + Power BI

## Business Question
Which employees are we losing, why, and what is it costing the company?

## Key Findings
- Overall attrition rate: 16.1% (237 of 1,470 employees)
- Overtime is the strongest attrition driver: 30.5% vs 10.4% (non-overtime)
- Combined with low job satisfaction, attrition rises to 36.6%
- Estimated cost of attrition: $6.8M (note: i have used 50% of annual salary replacement-cost model for this analysis)
- 97 currently active employees match the high-risk profile that projects $1.28M as avoidable future cost

## Tools Used
SQL (SQLite/DB Browser) for analysis
Power BI for visualization

## Files
- `/sql/attrition_analysis.sql` — all analysis queries
- `/dashboard/HR_Attrition_Dashboard.pbix` — full interactive dashboard
- `/data/Analysed_dataset.csv` — enriched dataset used in Power BI

## Approach
1. Explored the IBM HR Analytics dataset (1,470 employees) in SQL
2. Tested attrition rate across department, role, tenure, income, overtime, and satisfaction
3. Identified overtime + low satisfaction as the strongest actionable combination
4. Built a cost-of-attrition model to translate headcount loss into dollar impact
5. Flagged currently active employees matching the high-risk profile for proactive retention outreach

## Dataset Source
[IBM HR Analytics Employee Attrition dataset](Kaggle link) (public)
-`/data/Real_dataset.csv` - real dataset got from kaggle link
