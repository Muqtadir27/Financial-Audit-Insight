# **📊 Financial Audit Insight**
A Precision-Driven **Audit Trail for Financial Transactions** Using Excel

## **🔍 Project Overview**
**Financial Audit Insight** is an Excel-based audit tool that performs transaction-level validation of financial data, with a focus on reconciling and verifying entries involving journal entries, purchases, liabilities, and expense recognition. This project emulates how real-world financial audits are carried out, using a structured, logic-driven method to determine what entries should be included in audit reports and how transaction timing impacts financial records.

Whether you're a data analyst, financial auditor, or aspiring data scientist, this project showcases your attention to detail, domain understanding, and data validation logic in a real-world accounting context.


## **✅ Audit Logic: Inclusion Criteria**
A row is included in the final audit report only when the following conditions are met:

**🔹 Rule 1:** Correct Journal Entry Matching
- Must be a journal_entry type row             
- Must be followed by a matching purchase entry of the same amount (opposite sign) within a reasonable time window

**🔹 Rule 2:** Expense Recognition Flow
- When a journal entry debits an expense account and credits Accrued Expenses, the purchase that offsets the liability is expected afterward             
- The journal entry date is recognized as the period of expense booking          

**🔹 Rule 3:** Vendor Name Consistency
- Vendor fields (Name, Memo, Vendor) should not conflict
- Mismatched or missing values are flagged for manual review

## **❌ Exclusion Scenarios**
The row is excluded when:
- It is a standalone purchase with no matching journal entry
- The purchase date precedes the journal entry, violating the accrual principle
- Entries are duplicates or reversals of existing entries
- Amounts mismatch (even with matching vendors)
- Vendor/Memo inconsistency across pairings

## **📅 Treatment of Dates:**          
**How to Decide Start Date and End Date**
**✅ 1. When Start Date = End Date**
Use this when:
- A single transaction (like a purchase or journal entry) represents an instant booking.
- There’s no need to spread it across a time period.
- Common in:     
  1. Adjustments 
  2. Reversals 
  3. Final actual payments after prior accruals       
Example:
```
Transaction Type	Date	Start Date	End Date
Purchase	2024-07-12	2024-07-12	2024-07-12
```
**✅ 2. When End Date = Start Date + 1 month      
Use this when:           
- A journal entry is made for monthly accruals.       
- Expense is spread across a full month (like software usage, salaries, etc.).
- You're matching it to a future purchase/payment.        
Example:        
```
Transaction Type	Date	Start Date	End Date
Journal Entry	2024-10-30	2024-10-01	2024-10-31
```
Even if the entry date is 30th Oct, the expense is for the full month of October.        
 
**✅ 3. When Start Date = 1st of the month, End Date = end of the month**
Use this when:
- The entry is related to a month-end accrual.
- Payment will happen after the month ends (usually next month).
- Used for recurring monthly services (like software, rent, consulting).
Example:
```
Transaction Type	Date	Start Date	End Date
Accrual (JE)	2024-11-30	2024-11-01	2024-11-30
Payment (Purchase)	2024-12-11	2024-12-11	2024-12-11
```
This shows that the expense is for November, and payment happened in December.

**✅ Why We Included Journal Entries and Purchases:**
- Journal Entries show when the expense or liability was recorded.     
- Purchases show when the actual payment happened.           
Including both helps us track whether the expense was properly booked and paid, following standard accounting rules.


**❌ Why We Excluded Other Transactions:**             
- Other types (like standalone purchases or entries with no match) don't follow the expected accounting flow.        
- If we can't match an expense with a payment, or dates don’t make sense, it's safer to exclude them.        

This keeps the audit clean and reliable.         
## **🎯 Skills Demonstrated**       
Skill	Description                 
- Excel for Data Auditing	Used functions like VLOOKUP, IF, FILTER, conditional formatting
- Financial Logic Mapping	Applied accrual accounting principles for validation
- Vendor and Entry Matching	Handled inconsistent vendor naming across fields
- Transaction Reconciliation	Matched journal entries with purchases across dates and amounts
- Audit Trail Documentation	Wrote decision rules and audit summary for transparency

## **🧭 When to Use This Approach**     
Use this type of logic-driven financial audit when:            

- You’re working with general ledger dumps or QuickBooks exports       
- Trying to reconcile accrued expenses or deferred revenue          
- Ensuring data integrity in vendor payments          
- Preparing for a financial year-end close, audit, or reporting period        

## **📌 Tools Used**         
- Microsoft Excel (primary tool)           
- Manual tagging and logic tracking — no scripts or external code used

## **💼 Ideal For**
- Showcasing understanding of data accuracy, accounting workflows, and reconciliation logic

## **📝 License**
This project is licensed under the MIT License. Feel free to use, adapt, or build upon it.

## **Author**
👨‍💻 Developed by **Mohammed Abdul Muqtadir**

* [GitHub](https://github.com/Muqtadir27)
