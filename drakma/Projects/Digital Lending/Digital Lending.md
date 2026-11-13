---
status: active
dcp: PRJ-0001 Digital Lending Solution
clients: Centenary Bank (CRDB), Pearl Bank
mode: do
review: review
review_note: "Confirm the 'from older notes' tasks and the ❓ architecture review."
---
# Digital Lending (LMS v2)

## 🎯 Goal
Build **LMS v2** – a loan management system split into services – and deliver digital lending for **Centenary (CRDB)** and **Pearl Bank**, fed by the **Credit Scoring Engine (CSE)** and **Data Processor (DPU)**.

## 📍 Status (13 Nov 2026)
- **Customer service (CR-002) went live in production** (DCP, 12 Nov).
- [[People#Drakma|Kithmini]] put dates on the CRs in DCP and tagged me (12 Nov) – see the table.
- New: **LMS V2.0 Weekly Development Review**, Fridays 15:00–16:00 until 18 Dec.
- **Done:** Product service, Customer service.
- **To do:** Loan Processor, Loan Accounting, Payments Processor, Operations service, Loan Servicing, Scoring Engine, Notification service.
- **LMS v2.0 timelines** per module were shared by [[People#Drakma|Kithmini]] to [[People#Drakma|Veeru]] on 9 Nov ("LMS V2.0 - Project Timelines").
- All 10 service CRs are approved; dates now set for CR-003, 005, 006, 007.
- **Centenary micro-lending:** Drakma answered the CRDB Risk and Data Protection queries on 22 Oct. On 11 Nov Centenary asked [[People#Centenary Bank (CRDB)|Keneth]] to confirm whether that closes all risk items.
- **Pearl Bank:** fix to encrypt the phone number in `dwh_digi_loans` deployed to UAT (10 Nov); KYC data fetch and DB function update in progress with [[People#Drakma|Sai]] (11 Nov). MSME digital lending: Pearl running UVTs with scored customers (19 Oct).

## 📅 Service CRs (DCP, PRJ-0001)
| CR | Service | Owner | Dates (DCP) |
| --- | --- | --- | --- |
| CR-001 | Notification service | [[People#Drakma\|Ranjan]] | |
| CR-002 | Customer service | [[People#Drakma\|Kithmini]] | 🚀 live 12 Nov |
| CR-003 | Product service | Kithmini (me tagged) | Dev + SIT 10–13 Nov |
| CR-004 | Credit Scoring Engine | Kithmini | |
| CR-005 | Operations service | **me** (+ Sai) | UI/UX 10 Nov – 4 Dec |
| CR-006 | Loan Processor | **me** | Dev + SIT 16–20 Nov |
| CR-007 | Loan Accounting | **me** | Dev + SIT 23–26 Nov |
| CR-008 | Loan Servicing        | **me**          |            |
| CR-009 | Payments Processor    | **me**          |            |
| CR-010 | Data Processor        | Kithmini        |            |

## ✅ Tasks
- [ ] Review the updated **notification service** document and confirm ([[People#Drakma|Sai]], 9 Nov) #lending
- [ ] Product service changes #lending
- [ ] Integrate the product service with the loan processor #lending
- [ ] Confirm the CR dates Kithmini set in DCP (CR-003, 005, 006, 007 – 12 Nov) #lending 📅 2026-11-13
- [ ] Loan Processor (CR-006) – Dev + SIT #lending 📅 2026-11-20
- [ ] Loan Accounting (CR-007) – Dev + SIT #lending 📅 2026-11-26
- [ ] Review [[People#Drakma|Ranjan]]'s customer journey service architecture flow (21 Oct) ❓ done? #lending
- [x] Review the Loan Service SRS (Ranjan) – "I think it's ok" ✅ 2026-11-09

**From older notes – please confirm if still open**
- [ ] Service-to-service authentication and authorization (X-User-Token, X-Request-ID) #lending
- [ ] Docker Swarm for service discovery #lending
- [ ] Loan accounting set-up: create the ledger accounts; product accounting config (master vs product accounts); default per-product account config #lending
- [ ] CRDB: CSE ↔ DPU integration, CSE ↔ LMS integration #lending
- [ ] CRDB: when is the operative account number shared with LMS? #lending

## ⏳ Waiting on
- [ ] ⏳ Waiting on @Centenary ([[People#Centenary Bank (CRDB)|Keneth Sululu]]): confirmation that Drakma's 22 Oct submission closes the risk items

## 🧠 Key facts & decisions
- **Login:** the operations service issues and signs JWTs (at least userId, username, roleId). Other services check them with the public key.
- **Permissions:** each service defines its own; the operations service builds roles from them. Role lookups are cached.
- **Tracing:** every request carries an `X-Request-ID` that's kept as it passes between services.
- **CSE shares only eligibility:** category, financial eligibility, credit score.
- **PII:** customer NIN, phone and account number are shared and encrypted at rest.
- **Pre-scoring** doesn't use the KYC, loans or transactions data APIs.
- **Loan Processor (26 Oct):** responds to the customer as soon as the payments processor confirms, then posts to loan servicing asynchronously; it generates the loan account number itself.
- **CRDB accounting (21 Jul):** write-offs in batch; classification PA → NPA → Write-off; charges/fees built into interest rates; reporting via portal and the bank's intelligence platform.

## 👥 People
Ranjan (lead), Kithmini (BA), Sai Karthik (notification service) · Centenary: Keneth Sululu, [[People#Centenary Bank (CRDB)|David Keneth Mwesigwa]] · Pearl Bank: [[People#Pearl Bank|Micheal Bukenya]], Oketcho Hillary, [[People#Pearl Bank|Martha Akora]], [[People#Pearl Bank|Adons Aryong]]

## 🔗 Notes & meetings
- Scope: [[LMS Project Scope; tasks and subtasks]] · [[service discovery]]
- Eligibility: [[Product eligibility & customer classification]] · [[Eligibility workflow (top notes)]]
- Services: `Notes/Services/` (Accounting, Customer, Loan Processor, Payments Processor, Product)
- CRDB: [[CRDB - LMS data flow & PII]]
- Meetings: see `Meetings/` (CRDB client meetings start with "CRDB –")
- Documents: "Loan Management System - SAD" (Zoho WorkDrive)
