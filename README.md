# LoanVista
### Project: LoanVista offers an in-depth analysis of bank lending through Power BI dashboards. It tracks loan applications, funded amounts, repayments, interest rates, and borrower DTI. Key SQL queries support metrics for loan performance, distinguishing between good and bad loans.

**Dashboard :-**

![Screenshot 2024-08-01 214422](https://github.com/user-attachments/assets/7a3bd4fd-6e7b-4725-8bc0-8b64d3379c22)

Total Loan Applications: Count of applications received.

Total Funded Amount: Sum of disbursed loan amounts.

Total Amount Received: Sum of repayments from borrowers.

Average Interest Rate: Average interest rate of issued loans.

Average Debt-to-Income Ratio (DTI): Average DTI of borrowers.

Monthly Trends: Line chart for loan applications, funded amounts, and received amounts over time.


**Key Metrics for Loan Quality:-**
Good Loans - Loans fully paid or currently active.
Bad Loans - Loans charged off.

**SQL Queries:-**
The project is powered by MSSQL queries to extract and calculate essential metrics:

Total Loan Applications: SELECT COUNT(id) AS Total_Applications FROM bank_loan_data

MTD Loan Applications: SELECT COUNT(id) AS Total_Applications FROM bank_loan_data WHERE MONTH(issue_date) = 12

Total Funded Amount: SELECT SUM(loan_amount) AS Total_Funded_Amount FROM bank_loan_data

Total Amount Received: SELECT SUM(total_payment) AS Total_Amount_Collected FROM bank_loan_data

Average Interest Rate: SELECT AVG(int_rate)*100 AS Avg_Int_Rate FROM bank_loan_data

Average DTI: SELECT AVG(dti)*100 AS Avg_DTI FROM bank_loan_data

Loan Status Distribution: SELECT loan_status, COUNT(id) AS LoanCount, SUM(total_payment) AS Total_Amount_Received, SUM(loan_amount) AS Total_Funded_Amount, AVG(int_rate * 100) AS Interest_Rate, AVG(dti * 100) AS DTI FROM bank_loan_data GROUP BY loan_status


