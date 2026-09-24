# User Flows

Flows marked *(assumed)* contain a step I filled in that needs your confirmation. See [07-open-questions.md](07-open-questions.md).

## 1. First launch and setup

1. The user opens the app for the first time.
2. The app asks for permission to read SMS and to send notifications.
3. The app asks the user to create categories (name plus emoji) and set a budget for the current month.
4. The user lands on the Home screen.

## 2. Start of a new month *(assumed)*

1. On the first open in a new calendar month, the app offers to set up the month.
2. Last month's budgets are shown as a starting point.
3. The user adjusts any amounts and confirms.
4. Spending for the new month starts at zero, and nothing carries over from last month.

## 3. Add a transaction manually

1. The user taps Add.
2. They enter an amount, choose a category, and confirm the date. A note is optional.
3. They save.
4. The category's remaining amount updates, and a budget alert fires if a threshold is crossed (see flow 8).

## 4. An SMS arrives

1. A bank SMS arrives on the phone.
2. The app checks whether it is a debit message. If not, it is ignored.
3. If it is, the app extracts the amount, merchant, and date, and saves it as a message with status **not assigned**.
4. The Messages page icon shows a small red circle.
5. The app shows a simple notification, for example "3 new spends detected".
6. Tapping the notification opens the Messages page *(assumed)*.

## 5. Review messages

1. The user opens the Messages page and sees the list of received messages, newest first *(assumed)*.
2. Each row is coloured by status: white (not assigned), green (accepted), red (rejected).
3. The user can:
   - **Swipe right** to accept *(direction assumed)*
   - **Swipe left** to reject *(direction assumed)*
   - **Tap** the message to open it and read the full SMS

## 6. Accept a message

1. The user accepts a message by swiping.
2. The Add Transaction page opens with the details pre-filled: amount, date, merchant as the note, and a suggested category if a keyword matched.
3. The user edits anything they want and saves.
4. The message turns green (accepted) and the transaction is added to the category *(status changes on save, assumed)*.
5. If the user leaves without saving, the message stays white (not assigned).

## 7. Reject a message

1. The user swipes to reject.
2. The message turns red (rejected) and no transaction is created.
3. It stays in the list so it is still visible.

## 8. Budget alerts

1. Whenever a transaction is saved, the app recalculates that category.
2. If spending has just reached **80%** of the budget, the app sends a notification.
3. If spending has just gone **over 100%** of the budget, the app sends a notification.
4. Each alert is sent once per category per month *(assumed)*.

## 9. Daily check

1. The user opens the app and sees the Home screen.
2. They see remaining budget per category for the current month, with overspent categories clearly marked.
3. The Messages icon shows a red circle if there is anything new to review.

## 10. Month-end review

1. The user opens the Trends view.
2. They compare this month with previous months, in total and per category.
3. They see which categories were overspent.

## 11. Manage categories

1. The user opens category management.
2. They add a category with a name and an emoji, rename one, change its icon, or archive one.
3. Archived categories keep their past transactions and no longer appear when choosing a category.

## 12. Back up and restore

1. The user exports all data to a file from the settings area.
2. On a new or reset phone, they import that file to restore everything.
