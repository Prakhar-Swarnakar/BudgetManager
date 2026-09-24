# Features (v1)

Anything not listed here is in [06-backlog.md](06-backlog.md).

## F1. Categories

- Create, rename, and archive categories.
- Each category has a **name** and an **icon**, and the icon can be an emoji.
- Archived categories disappear from pickers but keep their history.

## F2. Monthly budget

- Set an amount per category for each calendar month.
- The budget can be edited at any time during the month.
- A new month starts as a copy of the previous month's budgets (assumed; see [07-open-questions.md](07-open-questions.md)).
- Nothing rolls over between months.

## F3. Manual transactions

- Add a transaction with amount, category, date, and an optional note.
- Edit or delete a transaction later.
- The same Add Transaction page is used when accepting an SMS, with the fields pre-filled.

## F4. SMS reading

- The app reads incoming bank SMS on the phone.
- It keeps only messages that look like a debit (money spent) and extracts the amount, merchant, and date.
- Each one is stored as a message on the Messages page.
- Works across many banks, so parsing has to cope with different formats.

## F5. Messages page

- A page listing every SMS-derived message the app received.
- The page's icon shows a small red circle when there are new messages.
- Each message is coloured by its status: white (not assigned), green (accepted), red (rejected).
- Swipe to accept or reject, or tap to open the message.
- Full detail in [04-messages-and-notifications.md](04-messages-and-notifications.md).

## F6. Notification for new messages

- When new spend messages arrive, the app shows a simple notification such as "3 new spends detected".
- No action buttons in v1.

## F7. Category suggestion

- When a message is accepted, the Add Transaction page opens with a category suggested from keywords in the merchant or SMS text.
- The user can change it before saving.
- If no keyword matches, the category is left empty.

## F8. Budget tracking

- For each category: **remaining = budget minus spent**.
- Remaining can be negative, and negative values are clearly marked.

## F9. Budget alerts

- Notify when a category reaches 80% of its budget.
- Notify when a category goes over its budget.

## F10. Home overview

- Shows the current month with remaining budget per category.

## F11. Trends

- Month-over-month spending, in total and per category.

## F12. Backup

- Export all data to a file and import it back, so a lost or replaced phone does not lose history.
