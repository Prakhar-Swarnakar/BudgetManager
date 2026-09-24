# Budget Rules

## Budget period

- A budget period is a **calendar month**, from the 1st to the last day.
- A transaction belongs to the month of its date, not the month it was entered.

## Setting budgets

- Each category has its own budget amount for each month.
- Budgets can be edited at any time during the month.
- A new month starts with last month's amounts copied in as a starting point *(assumed)*.

## Calculations

- **Spent** = the sum of that category's transactions in the month.
- **Remaining** = budget minus spent.
- **Percent used** = spent divided by budget.

Remaining can be negative. For example, a Food budget of ₹5,000 with ₹7,000 spent shows **-₹2,000**. Nothing caps or hides the negative value.

## No rollover

- Unspent money does not move to the next month.
- Overspending does not reduce the next month's budget.
- Each month is judged only against its own budget.

## Messages that are not accepted

- A message that is not assigned or is rejected does **not** count towards any category.
- Only a saved transaction affects the numbers.

## Alerts

| Alert | When it fires |
|---|---|
| 80% reached | Spending in a category reaches 80% of its budget |
| Overspent | Spending in a category goes over 100% of its budget |

Assumptions to confirm:

- Alerts are checked whenever a transaction is saved, whether it was entered manually or accepted from a message.
- Each alert is sent **once per category per month**.
- If one transaction jumps from below 80% straight to over 100%, only the overspent alert is sent.
- Editing or deleting a transaction does not send new alerts.
