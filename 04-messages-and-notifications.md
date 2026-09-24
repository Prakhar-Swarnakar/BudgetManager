# Messages and Notifications

## What counts as a message

A message is created from an incoming bank SMS that looks like a **debit** (money spent). Other SMS such as OTPs, promotions, balance alerts, and credits are ignored in v1 (credit handling is proposed as a backlog item).

Because several banks are used, the app cannot rely on one fixed SMS format. Parsing should look for common patterns such as "debited", "spent", "paid", and "UPI", along with an amount and a merchant name.

**If the amount or merchant cannot be read:** a message that clearly looks like a spend (it has a debit word and a rupee amount) but cannot be fully parsed is still saved. It appears on the Messages page with its original text, and the missing fields are left blank for the user to fill in when accepting. A message with no debit word, or with an OTP, is never saved. OTP text is never stored.

## Message fields

| Field | Notes |
|---|---|
| Sender | The SMS sender ID, such as a bank's short code |
| Amount | Extracted from the SMS. Blank if it could not be read |
| Merchant | Extracted from the SMS; used as the default note |
| Date and time | From the SMS |
| Original text | Full SMS text, shown when the message is opened |
| Status | Not assigned, accepted, or rejected |
| New flag | True until the user has opened the Messages page and left it. Drives the red circle on the tab and the bold text and blue dot on the row |
| Unique key | Built from the SMS's own id, time, and text, so the same SMS is never saved twice |
| Suggested category | From keyword matching, may be empty |
| Linked transaction | Set when the message is accepted and saved. Cleared, and the status returns to Not assigned, if that transaction is deleted |

## Statuses and colours

| Status | Colour | Meaning |
|---|---|---|
| Not assigned | White | Received, no decision yet |
| Accepted | Green | User accepted it and saved a transaction |
| Rejected | Red | User rejected it; no transaction was created |

## Messages page

- Reachable from the app's navigation. Its icon shows a **small red circle** when there are new messages.
- Lists all received messages, newest first *(assumed)*.
- Each row is coloured by its status.
- Accepted and rejected messages stay in the list. The filter chips (All, Not assigned, Accepted, Rejected) keep the list manageable. Archiving old messages is in the backlog.
- The red circle on the tab clears when the user opens the Messages page. Rows keep their bold text and blue dot until the user leaves the page, so they can see which ones were new.
- The Home line "N messages to review" counts messages that are still **Not assigned**, which is different from the "new" flag.

### Gestures

| Gesture | Result |
|---|---|
| Swipe right | Accept and edit. Opens Add Transaction pre-filled *(direction assumed)* |
| Swipe left | Reject *(direction assumed)*. A short Undo bar appears |
| Tap | Open the message and show the full SMS, with Accept and Reject buttons |

A rejected message can still be accepted later, by swiping right on it or with the Accept button on its detail page. There is no separate "restore" action.

### Accepting

Accepting opens the **Add Transaction** page with these fields pre-filled:

- Amount from the SMS
- Date from the SMS
- Note set to the merchant
- Category set to the keyword suggestion, or empty if nothing matched

The user can change any field. The message becomes green when the transaction is saved.

## Category suggestion

- A keyword list maps words to categories, for example a food-delivery merchant to Food.
- The suggestion is only a pre-fill. The user always sees it and can change it.
- If nothing matches, no category is suggested.
- Learning from past choices and user-editable keyword rules are in the backlog.

## Notifications

### New messages

- When new spend messages arrive, the app shows a simple notification such as "3 new spends detected".
- Tapping it opens the Messages page *(assumed)*.
- There are no action buttons in v1 (backlog).
- Grouping many messages that arrive together (SMS bursts) is in the backlog.

### Budget alerts

- **80% reached:** a notification when a category's spending reaches 80% of its budget.
- **Overspent:** a notification when spending in a category goes over its budget.
- Details are in [05-budget-rules.md](05-budget-rules.md).

## Permissions the app needs

- Read SMS.
- Post notifications.
- Being exempt from battery optimisation may be needed on some phones so notifications are not delayed.
