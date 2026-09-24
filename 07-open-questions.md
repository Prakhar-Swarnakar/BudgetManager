# Open Questions and Next Steps

## Assumptions to confirm

These are defaults I filled in from what you described. Correct any that are wrong.

1. **Swipe directions:** swipe right accepts and swipe left rejects.
2. **Accepted means saved:** a message turns green only after the transaction is saved on the Add Transaction page. If you back out, it stays white.
3. **Tapping the notification** opens the Messages page.
4. **Red circle behaviour:** it appears when there are new messages and clears once you open the Messages page.
5. **Message order:** newest first.
6. **New month budgets:** copied from the previous month as a starting point.
7. **Credits in v1:** credit SMS are ignored entirely and no message is created.
8. **Alert frequency:** each alert (80% and overspent) fires once per category per month.
9. **Currency:** Indian rupee (₹).
10. **Distribution:** the app is installed directly on your phone, so Google Play's SMS restrictions do not apply.

## Questions still open

- Can a rejected message be restored, or is rejection final?
- When a message is opened by tapping it, should it also have Accept and Reject buttons?
- Should accepted and rejected messages stay in the list forever, or move to a separate view after some time?
- What should happen if an accepted message's transaction is later deleted?

## Pages mentioned so far (not yet designed)

- Home (remaining budget per category)
- Messages (with the red circle icon)
- Message detail (full SMS)
- Add and edit transaction
- Monthly budget setup
- Category management
- Trends
- Settings, including backup and permissions

## Next step

Discuss the app's pages: navigation structure, side panels, and UI components for each page above.
