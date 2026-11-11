---
mode: do
review: ok
review_note: "Dashboard, kept up to date by Claude."
---
# 🏠 Home

> Claude keeps this note up to date (every morning, at the midday check and at the end of the day). You only read it.
> Last updated: 2026-11-12 00:30 (vault rewrite)

## Today
→ [[2026-11-11 Wed]] (Thursday's plan arrives at 6:44)

## ⚠️ Deadlines coming up
- **12 Nov** – Sure Pay development starts ([[Sure Pay]])
- **25 Nov** – Stanbic year-end change freeze ([[QRPe]])
- **30 Nov** – UAT: URA, GonzaPay onboarding/USSD/app CRs ([[GonzaPay]])
- **8 Dec** – URA go-live · **10 Dec** – MTP UAT · **20 Dec** – MTP go-live

## ⚙️ Tasks to do
*Most urgent first. Full lists live in each project note.*
- [ ] Test Sure Pay core APIs: validate reference, make payment → [[Sure Pay]] · dev starts 12 Nov
- [ ] Answer API7's 4 upgrade checks (headers, Stanbic staging test, scripts, memory) → [[API7 Gateway]]
- [ ] Share the routing document with Hitachi → [[QRPe]] · asked 9 Nov
- [ ] Reply to Stanbic on partner portal testing → [[QRPe]] · asked 11 Nov
- [ ] Review the notification service document → [[Digital Lending]] · asked 9 Nov
- [ ] Read Sai's handover document → [[GonzaPay]]
- [ ] Onboard Sure Pay API on the gateway → [[Sure Pay]]
- [ ] Be ready for URA UAT → [[URA Tax Payments]] · 30 Nov
- [ ] Fix AML-007 dormant account rule → [[GonzaPay AML]]
- [ ] CloudFront certificates (aml, uedclsupport) – with Sherry → [[Ops & Admin]]

## 🧠 Decisions waiting
- **AML rule conditions:** Option A (fixed attributes) or B (user-built)? → [[Rule Configuration]]
- **Sure Pay access token:** handled by us or by Hitachi? → [[Sure Pay]] (development starts 12 Nov)
- **URA branch code:** `CNB1` or the code used in the 29 Oct test? → [[URA Tax Payments]] (UAT 30 Nov)
- **API7 2FA upgrade:** internal approval and maintenance window → [[API7 Gateway]]
- **AML data layout:** record what was actually chosen → [[AML Fraud detection data layout & storage]]

## 📚 Learning queue
- **API7 3.10.9 upgrade:** forwarded headers, rolling data-plane upgrade, custom-plugin API changes → needed for API7's 4 checks ([[API7 Gateway]])
- **API7 key concepts:** gateway groups, services, routes, upstreams, consumers → finish [[Architecture]]
- **Service discovery:** answer the open questions (registry, client vs server-side load balancing) → [[service discovery]]

## ⏳ Waiting on others
- Hitachi: review of QRPe documentation
- Stanbic: production API access + credentials; new SIT date
- Centenary: MTP UI/UX approval; confirmation the micro-lending risk items are closed
- Sherry: CloudFront certificates

## 📊 Projects
| Project | Status | Next step |
|---|---|---|
| [[GonzaPay]] | 🟡 slow (billers delayed by partner info) | Sure Pay dev starts 12 Nov |
| [[QRPe]] | 🔴 blocked (Stanbic SIT on hold) | Stabilise APIs before 25 Nov freeze |
| [[API7 Gateway]] | 🟡 waiting on our checks | Answer API7's 4 checks |
| [[Digital Lending]] | ❓ to confirm | Notification service review |
| [[GonzaPay AML]] | 🟢 live | Fix AML-007 |
| [[Ops & Admin]] | 🟡 waiting on Sherry | CloudFront certificates |

## 🔗 Quick links
[[📥 Inbox]] · [[People]] · [[How tasks work]] · [[🧹 Vault review]] · Archive: `Archive/Old weekly notes`
