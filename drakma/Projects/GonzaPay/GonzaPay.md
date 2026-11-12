---
status: active
client: Centenary Bank (CRDB)
dcp: PRJ-0006 GonzaPay (CRDB, CTS & Drakma)
mode: do
review: review
review_note: "Confirm the ❓ tasks (customer info app, UEDCL messages)."
---
# GonzaPay

## 🎯 Goal
Deliver GonzaPay change requests for Centenary Bank (CRDB). My part: **biller integrations through the API gateway** (URA, Motor Third Party, Sure Pay) and **GonzaPay support**.

## 📍 Status (12 Nov 2026)
- **Sprint-2 development starts 12 Nov.** Sure Pay and Motor Third Party are in Sprint-2.
- **[[Sai Karthik]] handed over** his GonzaPay and QRPe technical work to me and [[Ranjan Epili|Ranjan]] on 27 Oct (handover document in that email: "Work Handover Document – GonzaPay and QRPe").
- Billers: [[URA Tax Payments]] · [[Motor Third Party]] · [[Sure Pay]]

## 📅 Key dates (from DCP)
| CR | What | UAT | Go-live | Status |
|---|---|---|---|---|
| CR-003 | [[URA Tax Payments]] | 30 Nov | 8 Dec | In progress |
| CR-004 | [[Motor Third Party]] | 10 Dec | 20 Dec (moved +10 days) | In progress |
| CR-013 | [[Sure Pay]] | 4 Jan 2027 | 12 Jan 2027 | Dev starts 12 Nov |
| CR-001 | Customer onboarding (KYC) | 30 Nov | 10 Dec | In progress |
| CR-002 | Accounting architecture change | 30 Nov | 10 Dec | In progress |
| CR-006 | USSD flow enhancement | 30 Nov | 8 Dec | In progress |
| CR-011 | GonzaPay app enhancements | 30 Nov | 10 Dec | In progress |

## ✅ Tasks
Biller tasks are in each biller note. Cross-cutting:
- [ ] Read Sai's handover document and list anything I now own #gonzapay
- [ ] Customer information app: request the required authorization from the bank team for the shared user ❓ still open? #gonzapay
- [ ] UEDCL support: clearer response messages, especially errors ❓ still open? #gonzapay

## ⏳ Waiting on
- See each biller note.

## 🧠 Key facts & decisions
- **Biller money flow** (all billers, same as UEDCL, NWSC, SchoolPay), per [[Veeru Yelluru|Veeru]] 8 Oct:
  1. Dr customer wallet → 2. Cr CRDB OVA → 3. Ask the bank to settle the biller → 4. Dr eWallet suspense → 5. Cr biller's collection account.
- **Support logs:** upload GonzaPay support log files to the WorkDrive folder "Log Files" (shared by Veeru, 15 Oct).

## 👥 People
- **Centenary:** [[Keneth Sululu]] (product development), [[Micheal Kalyango]] (Centenary Tech, product & BD)
- **Hitachi (HDPS):** [[Praneeth Damian]], [[Anuruddha Bandara]]
- **Drakma:** Veeru (PM), [[Kithmini Chamathka Wanasundara|Kithmini]] (BA/PM)
- More in [[People]].

## 🔗 Notes & meetings
- Billers: [[URA Tax Payments]] · [[Motor Third Party]] · [[Sure Pay]]
- [[TPS merchant inquiry (Centenary)]] · [[MTP integration notes]]
- Meetings: [[2026-11-09 Sure Pay call]]
- DCP: https://dcp.drakma.com → GonzaPay
