# Product Overview

## Vision

A small, private budgeting app that answers one question quickly: **how much is left in each category this month?** It should take very little effort to keep up to date, because bank SMS are picked up automatically and only need a quick review.

## Who it is for

One user (the owner), on their own Android phone, with accounts at several different banks.

## Principles

- **Low effort:** logging a transaction should take a few taps, and SMS should do most of the work.
- **Honest numbers:** overspending shows as a negative number rather than being hidden or capped.
- **User in control:** the app suggests a category from keywords, but nothing is filed without the user accepting it.
- **Private:** all data stays on the phone.
- **Simple first:** anything that adds complexity without being essential goes to the backlog.

## Decision log

| Topic | Decision | Status |
|---|---|---|
| Platform | Native Android app (needed to read SMS and show notifications) | Decided |
| Users | Single user | Decided |
| Data storage | On the phone only, with manual export and import as a backup | Decided |
| Budget period | Calendar month (1st to last day) | Decided |
| Month rollover | None. Each month resets and starts from its own budget | Decided |
| Overspending | Allowed. Remaining amount can go below zero (for example -2000) | Decided |
| Categories | Each has a name and an icon, and the icon can be an emoji | Decided |
| Adding transactions | Entered manually, or created from a bank SMS after the user reviews it | Decided |
| SMS categorisation | Keyword-based suggestion that the user can change or confirm | Decided |
| SMS review | Done on a dedicated Messages page, not through notification buttons | Decided |
| Notification | A simple "new spends detected" notification. Action buttons are in the backlog | Decided |
| Budget alerts | Notify at 80% of a category budget and when it is overspent | Decided |
| Home screen focus | Remaining budget per category, plus month-over-month trends | Decided |
| Currency | Indian rupee (₹) | Assumed |
| Distribution | Installed directly on the owner's phone, not through the Play Store | Assumed |
| New month budget | Starts as a copy of the previous month's budgets, which can be edited | Assumed |
