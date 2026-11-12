---
status: active
vendor: API7 (API7 Cloud control plane, 3.10.1)
mode: do
review: review
review_note: "Confirm the 'from older notes' tasks (MTP docs, Airtel, routing research)."
---
# API7 Gateway

## 🎯 Goal
Run all partner integrations safely through the API7 gateway: GonzaPay billers (URA, MTP, Sure Pay), QRPe banks (Stanbic, Pearl, Centenary), SMS (Africa's Talking), Airtel, MTP.

## 📍 Status (12 Nov 2026)
- **Dashboard 2FA:** needs an upgrade from **3.10.1 → 3.10.9** (control plane first, then data planes). I sent API7 the plugin list and redacted ADC exports on 6 Nov. **API7 replied 11 Nov with 4 checks** for us (below).
- **Billing:** [[Sherry Alan Fintan|Sherry]] logged an AWS case about missing API7 Cloud charges (30 Oct); subscription active since 22 Jul. API7 ([[Zhi Yuan Ju]], 29 Oct) asked whether drakma.admin.api7.cloud is still used and to clear any outstanding amount.

## ✅ Tasks
**2FA upgrade – answer API7's checks (from 11 Nov email)**
- [ ] Do any upstreams rely on `X-Forwarded-Proto/Host/Port` or `Forwarded` from the load balancer? (3.10.9 rewrites/clears them for untrusted sources) #api7
- [ ] In staging on 3.10.9 with both custom plugins: run Stanbic merchant inquiry, merchant settlement and transaction inquiry end to end #api7
- [ ] Check scripts/pipelines calling `/api/custom_plugins` or `/api/plugins/{name}/usage`, and anything using perl/apt/curl/resty inside the gateway container #api7
- [ ] Add ~400 MiB memory to each data-plane container (or review shared-memory settings) #api7
- [ ] Get internal approval, then agree the maintenance window and rollback rules with API7 #api7

**Other**
- [ ] Onboard Africa's Talking API in the gateway (PROD) and test #api7
- [ ] Confirm with Sherry/[[Veeru Yelluru|Veeru]] the status of API7 billing and the commercial proposal #api7

**From older notes – please confirm if still open**
- [ ] MTP integration documentation shared #api7
- [ ] Airtel integration: callback + documentation from HDPS #api7
- [ ] Research advanced API routing #api7

## ⏳ Waiting on
-

## 🧠 Key facts & decisions
- **2FA over SSO for now** – keep username/password and add 2FA first; consider SSO and an IP allowlist later (call with API7, 5 Nov).
- 2FA needs **3.9.16+** or **3.10.3+**.
- During the upgrade window: no route or plugin edits while the control plane upgrades. Roll back the data plane first if 5xx rises.
- Gateways run in **our VPC**, linked to API7's cloud control plane. Usage billed like SaaS (daily usage, monthly).
- Default ports: 9080 (HTTP), 9443 (HTTPS). Integrations host: `integrations.drakma.com:9543`.

## 👥 People
API7: [[Yuan Bao]] (support), Zhi Yuan Ju (Head of Global) · Drakma: Sherry (infra), Veeru, [[Ranjan Epili|Ranjan]]

## 🔗 Notes & meetings
- [[Architecture]] · [[Introduction]] · [[Security overview for partners]]
- Meetings: [[2026-08-06 API7 onboarding]]
