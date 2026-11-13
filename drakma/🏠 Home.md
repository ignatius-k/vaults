---
mode: do
review: ok
review_note: "Dashboard, kept up to date by Claude."
---
# 🏠 Home

> Claude keeps this note up to date (every morning, at the midday check and at the end of the day). You only read it.
> Last updated: 2026-11-13 18:30 (wrap-up + weekly review)

## Today
→ Weekend. This week's review: [[2026-W46]] · next daily note Mon 16 Nov

## ⚠️ Deadlines coming up
- **Overdue** – Stanbic on-us go-live (was tentative 13 Nov) ([[QRPe]]) · ❓ Product service (CR-003 SIT ended 13 Nov, your note says not finished) ([[Digital Lending]])
- **16–20 Nov** – CR-006 Loan Processor Dev + SIT ([[Digital Lending]])
- **17–19 Nov, 14:00–15:30** – QRPe off-us SIT Sessions I–III (Stanbic, Pearl, Centenary) ([[QRPe]])
- **23–26 Nov** – CR-007 Loan Accounting Dev + SIT ([[Digital Lending]])
- **25 Nov** – Stanbic year-end change freeze ([[QRPe]])
- **30 Nov** – UAT: URA, GonzaPay onboarding/USSD/app CRs ([[GonzaPay]])
- **8 Dec** – URA go-live · **10 Dec** – MTP UAT · **20 Dec** – MTP go-live

## ⚙️ Tasks to do
*Most urgent first. Full lists live in each project note.*
- [ ] Stanbic go-live: mTLS + message-signing certificates, bank credentials from Tishara, test merchant inquiry → [[QRPe]] · slipped from 13 Nov
- [ ] Tell Yuan Bao when the 3.10.9 staging test runs; finish scripts + memory checks → [[API7 Gateway]] · he asked 13 Nov
- [ ] ❓ Product service – what still needs adding? → [[Digital Lending]] · your 13 Nov inbox note
- [ ] Loan Processor (CR-006) → [[Digital Lending]] · 16–20 Nov
- [ ] Sure Pay: gateway onboarding + OAuth/signing plugin → [[Sure Pay]]
- [ ] Follow up David Kaisu on the empty `reason` field → [[URA Tax Payments]]
- [ ] Follow up the Stanbic ↔ Drakma VPN with Sherry → [[QRPe]] · down since last week
- [ ] Review the notification service document → [[Digital Lending]] · asked 9 Nov
- [ ] AML: design the new wallet-opening rule → [[GonzaPay AML]]
- [ ] Africa's Talking in the production gateway → [[API7 Gateway]]
- [ ] ❓ Confirm MTP UAT date (23 Nov, 30 Nov or 10 Dec?) → [[Motor Third Party]]

## 🧠 Decisions waiting
- **Sure Pay token caching in the gateway:** per node or shared? → [[Sure Pay]] · blocks the plugin build (open since 13 Nov)
- **AML rule conditions:** Option A (fixed attributes) or B (user-built)? → [[Rule Configuration]]
- **URA branch code:** `CNB1` or the code used in the 29 Oct test? → [[URA Tax Payments]] (UAT 30 Nov)
- **API7 2FA upgrade:** internal approval and maintenance window → [[API7 Gateway]]
- **AML data layout:** record what was actually chosen → [[AML Fraud detection data layout & storage]]

## 📚 Learning queue
- **AWS NLB and HTTP headers** (re-ask Q2 + unanswered Q3 from 12 Nov quiz, Mon/Tue) → [[API7 Gateway]]
- **API7 3.10.9 upgrade:** rolling data-plane upgrade, custom-plugin API changes → needed for API7's checks ([[API7 Gateway]])
- **OAuth2 token caching in a gateway plugin** → needed for the Sure Pay plugin ([[Sure Pay]])
- **API7 key concepts:** gateway groups, services, routes, upstreams, consumers → finish [[Architecture]]
- **Service discovery:** answer the open questions (registry, client vs server-side load balancing) → [[service discovery]]

## ⏳ Waiting on others
- Stanbic: production items for go-live; VPN tunnel check ([[People#Stanbic|Victor]]); new SIT date
- Hitachi: review of the QRPe documentation, the Stanbic routing document and the inbound-QRPe gateway set-up
- Centenary: MTP UI/UX approval; confirmation the micro-lending risk items are closed
- URA ([[People#URA|David Kaisu]]): explanation of the empty `reason` field

## 📊 Projects
| Project | Status | Next step |
|---|---|---|
| [[GonzaPay]] | 🟡 slow (billers delayed by partner info) | Sure Pay tested; build the gateway plugin |
| [[QRPe]] | 🟡 on-us go-live in progress, off-us SIT on hold | Hand over certificates and credentials to Stanbic |
| [[API7 Gateway]] | 🟡 waiting on our checks | Headers answered; staging test date, scripts, memory |
| [[Digital Lending]] | 🟢 dates set, CR-002 live | Loan Processor 16–20 Nov |
| [[GonzaPay AML]] | 🟢 live | Wallet-opening rule, AML-007 |
| [[Ops & Admin]] | 🟢 certificates done | – |

## 🔗 Quick links
[[2026-W46]] · [[📥 Inbox]] · [[People]] · [[How tasks work]] · [[🧹 Vault review]] · Archive: `Archive/Old weekly notes`
