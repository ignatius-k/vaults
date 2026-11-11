---
status: active
---
# GonzaPay AML

## 🎯 Goal
An AML and fraud detection system that makes adding new (even unusual) rules easy and spots suspicious patterns.

## 📍 Status
- Next: new wallet-opening rule, and research on smarter transaction analysis.

## ✅ Tasks
- [ ] Design and implement the new rule: new wallet → pull from bank → send straight to an external wallet #aml
- [ ] Research how to make rule onboarding easy, including unusual rules #aml
- [ ] Research better transaction analysis: common patterns, using an LLM, better reports (in the app and by email) #aml
- [ ] Pattern reporting in the app (e.g. a transaction quickly followed by another one) #aml

**From older notes: please confirm if still open**
- [ ] Network graph UI: make it visible, able to grow, colour-coded money flow #aml

## ⏳ Waiting on
-

## 🧠 Key facts & decisions
- Cron job refreshes the materialized view (extension in `defaultdb`, scheduled on `gonzapay-prod`).
- Google Analytics data needs BigQuery. Delay: device → GA4 about 1 hour → BigQuery (1 min unstable, 1 day stable).

## 🔗 Notes & meetings
- [[GonzaPay AML & Fraud Detection System]] (overview) · [[AML Raised Issues]] · [[Rule Configuration]] · [[Key Notes]]
