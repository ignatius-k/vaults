---
status: active
app: https://aml.drakma.com
mode: do
review: ok
review_note: "Current."
---
# GonzaPay AML

## 🎯 Goal
An AML and fraud detection system for GonzaPay that makes adding new (even unusual) rules easy, spots suspicious patterns, and helps risk officers work alerts into cases.

## 📍 Status (12 Nov 2026)
- **Live** – alerts are emailed from info@drakma.com (e.g. FRAUD-001 "High-Velocity Failed Outbound Transaction Burst", 11 Nov).
- Next: new wallet-opening rule, smarter pattern analysis, case management.

## ✅ Tasks
**New work**
- [ ] Design and implement the new rule: new wallet → pull from bank → send straight to an external wallet #aml (carried over again 13 Nov)
- [ ] Research easy rule onboarding, including unusual rules → [[Rule Configuration]] #aml
- [ ] Research better transaction analysis: common patterns, using an LLM, better reports (in the app and by email) #aml
- [ ] Pattern reporting in the app (e.g. a transaction quickly followed by another) #aml

**Bugs and fixes** → details in [[AML Raised Issues]] and [[Key Notes]]
- [ ] Fix **AML-007 Dormant Account Activity** – it fires even when the wallet had transactions within 90 days #aml
- [ ] Standardise phone numbers at ingestion (256700111222 = 700111222 = 0700111222) #aml
- [ ] Alerts: dismiss, assign to a risk officer, open a case from an alert #aml
- [ ] Case management: dashboard, notifications, case progression #aml
- [ ] Entity page layout fixes (transaction volume chart, risk profile, recent activity, cases section) #aml

**From older notes – please confirm if still open**
- [ ] Network graph UI: make it visible, able to grow, colour-coded money flow #aml
- [ ] Read-only user role #aml

## ⏳ Waiting on
-

## 🧠 Key facts & decisions
- Cron job refreshes the materialized view (extension in `defaultdb`, scheduled on `gonzapay-prod`).
- Google Analytics data needs **BigQuery**. Delay: device → GA4 ≈ 1 hour → BigQuery (1 min unstable, 1 day stable) → AML.
- Rules target transactions by **status** too (success, failure or both), since failed transactions matter.
- Some entities have no wallet: those that push money in and those that pull money out.
- Data collection by polling (regular vs adaptive vs batch); continuous monitoring with a look-back window.

## 🔗 Notes & meetings
- Design: [[Rule Configuration]] · [[Key Notes]] · [[AML Raised Issues]]
- Data: [[Unified Data Source]] · [[Data Schema]] · [[AML Fraud detection data layout & storage]] · [[Database Querying - Polling]] · [[Defining the view & underlying table]]
