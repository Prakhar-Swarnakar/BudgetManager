# Decisions and Open Items

Earlier this file listed assumptions and open questions. On 24 September 2026 you asked me to clear them so implementation can start. Everything below is now settled with a default. **These defaults stand unless you say otherwise.** Changing one later is cheap in the docs and cheap in code if it is done before the screen is built.

## Settled by default

### Messages

| # | Question | Decision |
|---|---|---|
| 1 | Swipe directions | Swipe right accepts. Swipe left rejects, with a short Undo bar |
| 2 | When does a message turn green | Only after the transaction is saved. Backing out leaves it Not assigned |
| 3 | What does tapping the notification do | Opens the Messages page |
| 4 | Red circle behaviour | Appears when there are new messages. Clears when the Messages page is opened. Row highlights clear when the user leaves the page |
| 5 | Message order | Newest first |
| 6 | Credit SMS | Ignored in v1. No message is created |
| 7 | Can a rejected message be restored | It can still be accepted later, by swipe or from the detail page. No separate restore action |
| 8 | Does the detail page have Accept and Reject buttons | Yes |
| 9 | How long do accepted and rejected messages stay | Forever. The filter chips manage the list. Archiving is in the backlog |
| 10 | A spend message whose amount cannot be read | It is still saved with its raw text and blank fields, so nothing is lost |
| 11 | An accepted message's transaction is deleted | The message returns to Not assigned |

### Budget and Home

| # | Question | Decision |
|---|---|---|
| 12 | New month budgets | Copied from the previous month as a starting point |
| 13 | Alert frequency | Each alert fires once per category per month |
| 14 | A ₹0-budget category that gets spending | Negative remaining, labelled "Not budgeted", no percentage, one over-budget alert. Rules in [05-budget-rules.md](05-budget-rules.md) |
| 15 | Home card order | The fixed order set on the Categories page |
| 16 | Monthly budget page Save button | Removed. Each amount is saved when its sheet is saved |
| 17 | Where transactions are edited or deleted | On a new Category detail page, opened by tapping a card on Home |
| 18 | First-launch setup | Starter categories are created with ₹0 budgets, then the Monthly budget page opens so amounts can be set |

### Trends and general

| # | Question | Decision |
|---|---|---|
| 19 | Previous month tab contents | Budget used per month over 6 months, plus this month so far against last month by category |
| 20 | Trends range setting | Settings offers 3, 6, or 12 months, defaulting to 6. It is the last item built, and the first to cut if time is short |
| 21 | Many categories in the donut | All categories are shown. Grouping small slices into "Others" is in the backlog |
| 22 | Currency | Indian rupee (₹) |
| 23 | Distribution | Installed directly on the phone over USB, not through the Play Store. Phase 1 tests this |
| 24 | Restore behaviour | Import replaces everything after a summary and confirmation. Merging is in the backlog |

### Technical

| # | Question | Decision |
|---|---|---|
| 25 | Dependency injection | Hilt |
| 26 | Navigation | Navigation 3 if it is stable when the project starts. Otherwise Navigation Compose |
| 27 | Application ID | `com.budgetmanager.app`. Chosen generic, without a personal name. Change it before the project is created, because it cannot be changed afterwards without making a new app |
| 28 | Code repository | A private Git repository, in a folder outside OneDrive. Sample SMS never goes in a public repository |
| 29 | Android's automatic cloud backup | Off (`allowBackup="false"`). It would copy SMS-derived data to a Google account. Your own export file (M9) is the backup |

## Still open (none block starting)

| Item | Needed by | Who |
|---|---|---|
| Phase 1 test results ([11-phase-1-results.md](11-phase-1-results.md)) | Before Phase 2 starts | You |
| 30 to 50 real bank SMS with personal details removed ([14-implementation-plan.md](14-implementation-plan.md) explains how and gives a template) | Milestone M2, the SMS parser. Milestones M0 and M1 can start without them | You |
| ~~Confirm the application ID in row 27~~ Done: `com.budgetmanager.app` | Before milestone M0 | You |
| Whether Navigation 3 is stable | Milestone M0 | Me |
| Whether Room 3.0 is stable (we start on Room 2.x either way) | Milestone M0 | Me |

## Pages

Navigation and page contents are in [08-pages-and-navigation.md](08-pages-and-navigation.md). The plan for building everything is in [14-implementation-plan.md](14-implementation-plan.md).
