# Bank Loan Performance \& Risk Analysis

**KPIs, Good vs Bad Loans, and Repayment Across 38,576 Loans in Power BI** | Power BI, DAX, Dashboard Design


I turned 2021 loan data for 38,576 applications into a three-page Power BI dashboard that tracks applications, funded amount, amount received, interest rate, and DTI, and shows which loans are good or bad, where borrowers come from, and how much money each group brings back.


**Objective:** To monitor the health of the loan book by tracking five KPIs with month-to-date (MTD) and month-over-month (MoM) change, to split good and bad loans, and to find where the risk sits.


Dashboard Preview
---

**Summary**

!\[Bank Loan Report Summary page](dashboard/Summary.png)


**Overview**

!\[Bank Loan Report Overview page](dashboard/Overview.png)


**Details**

!\[Bank Loan Report Details page](dashboard/Details.png)


Full case study (15 slides): [Bank\_Loan\_Report\_Case\_Study.pdf](report/Bank_Loan_Report_Case_Study.pdf)


Business Questions
---

1. How is the loan book performing: volume, funding, repayment, interest rate, and DTI?
2. What share of loans are good or bad, and how much money does each bring back?
3. Where do applications come from: state, purpose, term, employment length, and home ownership?
4. How did volume change month by month, and what does the latest month signal?


Dataset
---

[Bank loan data (Google Drive)](https://drive.google.com/drive/folders/1wjjTBUg2SHXJQwVNjI5vHLk6DjI2W7y7) from the **Data Tutorials** channel: 38,576 loan applications issued in 2021. Fields used include loan ID, purpose, home ownership, grade, subgrade, issue date, state, term, employment length, funded amount, interest rate, installment, DTI, loan status (Fully Paid, Current, Charged Off), and amount received. The raw data is not included in this repository; download it from the link above. All amounts are in USD. The data has no income or credit score fields, so the analysis shows differences between loans, not the reasons borrowers default.

## 

## Approach

1. **Define KPIs:** total loan applications, total funded amount, total amount received, average interest rate, and average DTI, each with MTD (December) and MoM change measures in DAX.
2. **Split loans:** good loans (Fully Paid and Current) against bad loans (Charged Off), with count, funded amount, and received amount for each.
3. **Build:** three pages: Summary (KPI cards, good vs bad split, loan status table), Overview (monthly trend and top 7 by state, term, employment length, purpose, and home ownership), and Details (loan-level table).
4. **Filter:** slicers for State, Grade, and Good vs Bad Loan on every page, plus a Select Measure switch on Overview and Details.
5. **Read:** the results, then write findings, limits, and recommendations.

## 

## Key Findings

* 38.6K applications, $435.8M funded, and $473.1M received, so the book returned $37.3M (8.6%) above the funded amount. The average interest rate is 12.0%, and the average DTI is 13.3%.
* Good loans are 86.2% of applications (33.2K, $370.2M funded). Bad loans are 13.8% (5.3K, $65.5M funded) but 15.0% of funded money, because their average loan ($12.3K) is above Fully Paid ($10.9K).
* Charged Off loans paid back only 56.9% ($37.3M received on $65.5M funded), a $28.2M gap. Fully Paid loans returned 17.1% above funded.
* Charged-off loans sit higher on both rate (13.88% against 11.64% for Fully Paid) and DTI (14.00% against 13.17%).
* Applications grew from 2.3K in January to 4.3K in December (+87%), with no month falling. December funded amount grew 13.0% MoM, faster than applications (6.9%), so loans are getting bigger.
* December interest rate (12.4%) and DTI (13.7%) sit above the full-year 12.0% and 13.3%, while volume grew.
* California is 17.9% of applications (6.9K), 1.9x New York (3.7K). The top 4 states (CA, NY, FL, TX) hold 42%.
* Debt consolidation is 47% of applications (18.2K); with credit card (5.0K), it is 60%.
* 73.2% of loans are 36-month, and 26.8% are 60-month. Renters are 47.7% of applications and mortgage holders 44.6%. Borrowers with 10+ years of employment are 23%.
* The biggest returns in the Details table are $35,000 loans in grades E to G with rates of about 19% to 23%. The best row (ID 989285) returned $58,564 on $35,000 (+67%).

## 

## Recommendations

* Review credit rules for higher-rate, higher-DTI loans, because charged-off loans sit higher on both.
* Track bad loans in dollars, not only count: they are 15.0% of money against 13.8% of loans.
* Watch the December risk signals: rate and DTI rose above the full year while volume grew.
* Set risk checks for debt consolidation and credit card loans, which are 60% of applications together.
* Add default rate by grade to the dashboard, and check E to G loans before treating high returns as safe.

## 

## Limits

* One year of data (2021), so there is no multi-year trend.
* 1,098 Current loans are still paying, so their result is not final.
* No income or credit score, so the dashboard shows differences, not causes of default.
* Average loan size and recovery rates are calculated from the Summary table, not shown as dashboard measures.
* The Details table does not show the Charged Off rate of the high-return loans.

## 

## Tools and Skills

**Tools:** Power BI, DAX (MTD and MoM measures), Dashboard Design

**Skills:** Data Analysis, Data Visualization, Dashboard Design, KPI Design, Risk Analysis, Data Storytelling

## 

## Repository Structure

```
bank-loan-analysis/
├── README.md
├── dashboard/   (Summary, Overview, and Details images)
└── report/      (case study PDF)
```

## 

## Author

Umair Khalil | Senior Data Analyst

## 

## Disclaimer

Independent portfolio project, not affiliated with Data Tutorials. Project built with guidance from the Data Tutorials channel. Dataset credit: Data Tutorials. All figures come from the Power BI dashboard (38,576 loans, 2021, USD).

