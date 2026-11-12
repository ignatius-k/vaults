---
project: GonzaPay
cr: CR-003 Biller-URA Tax Payments
status: in progress
mode: do
review: review
review_note: "Confirm which branch code is right (CNB1 vs the code used on 29 Oct)."
---
# URA Tax Payments (CR-003)

Paying URA taxes through GonzaPay. Part of [[GonzaPay]].

## 📍 Status (12 Nov 2026)
- **UAT 30 Nov – 4 Dec, go-live 8 Dec.**
- Payment notification works in UAT after the troubleshooting call with URA (29 Oct): it succeeded once tested with the bank branch codes URA shared.
- URA service credentials for the gateway were given to Hitachi ([[People#Hitachi (HDPS)|Hiranya]], 23 Oct).

## ✅ Tasks
- [ ] Confirm which branch code to use in UAT and production (`CNB1` per [[People#Centenary Bank (CRDB)|Micheal]], 28 Oct, vs the code used in the 29 Oct test) #gonzapay
- [ ] Be ready for UAT on 30 Nov #gonzapay

## ⏳ Waiting on
-

## 🧠 Key facts & decisions
- Gateway exposes URA's endpoints **as-is**; Hitachi handles signature generation and OAuth2.
- The URA service runs on instance `15.0.1.49` (not `15.0.1.178`).
- [[People#Hitachi (HDPS)|Anuruddha]] (28 Oct): verification passed with `bankBranchCode`, but payment failed until the branch-code fix.

## 👥 People
[[People#URA|David Kaisu]], B. Ndyomugabe (URA) · [[People#Centenary Bank (CRDB)|Micheal Kalyango]], [[People#Centenary Bank (CRDB)|David Keneth Mwesigwa]] (Centenary) · [[People#Hitachi (HDPS)|Hiranya Wijesiri]], [[People#Hitachi (HDPS)|Praneeth]], [[People#Hitachi (HDPS)|Anuruddha]] (Hitachi)

## 🔗 Links
- DCP: GonzaPay → CR-003
