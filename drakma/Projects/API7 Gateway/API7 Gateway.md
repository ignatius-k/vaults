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
- **Billing:** [[People#Drakma|Sherry]] logged an AWS case about missing API7 Cloud charges (30 Oct); subscription active since 22 Jul. API7 ([[People#API7|Zhi Yuan Ju]], 29 Oct) asked whether drakma.admin.api7.cloud is still used and to clear any outstanding amount.

## ✅ Tasks
**2FA upgrade – answer API7's checks (from 11 Nov email)**
- [/] Do any upstreams rely on `X-Forwarded-Proto/Host/Port` or `Forwarded` from the load balancer? (3.10.9 rewrites/clears them for untrusted sources) #api7
	- 12 Nov: no upstream currently depends on them. Still to write up: how staging is handled (separate gateway group?), memory, and what it means for the Drakma team and future users.
- [ ] In staging on 3.10.9 with both custom plugins: run Stanbic merchant inquiry, merchant settlement and transaction inquiry end to end #api7
- [ ] Check scripts/pipelines calling `/api/custom_plugins` or `/api/plugins/{name}/usage`, and anything using perl/apt/curl/resty inside the gateway container #api7
- [ ] Add ~400 MiB memory to each data-plane container (or review shared-memory settings) #api7
- [ ] Get internal approval, then agree the maintenance window and rollback rules with API7 #api7

**Other**
- [ ] Onboard Africa's Talking API in the gateway (PROD) and test #api7 (not done yet, 13 Nov)
- [x] Onboard URA in the gateway #api7 ✅ 2026-11-13 – follow-up with URA in [[URA Tax Payments]]
- [ ] Handle **inbound traffic to QRPe** through the gateway: onboard and test the QRPe API with the credentials from [[People#Hitachi (HDPS)|Tishara]], then use the same set-up in production #api7 #qrpe
- [x] Confirm with [[People#Drakma|Sherry]]/[[People#Drakma|Veeru]] the status of API7 billing and the commercial proposal #api7

**From older notes – please confirm if still open**
- [x] MTP integration documentation shared #api7
- [ ] ⏸️ Airtel integration: callback + documentation from HDPS #api7 – **paused** (13 Nov)
- [ ] Research advanced API routing #api7

## ⏳ Waiting on
- [ ] ⏳ Waiting on @Hitachi: review of the documentation for routing inbound QRPe traffic through the gateway

## 🧠 Key facts & decisions
- **2FA over SSO for now** – keep username/password and add 2FA first; consider SSO and an IP allowlist later (call with API7, 5 Nov).
- 2FA needs **3.9.16+** or **3.10.3+**.
- During the upgrade window: no route or plugin edits while the control plane upgrades. Roll back the data plane first if 5xx rises.
- Gateways run in **our VPC**, linked to API7's cloud control plane. Usage billed like SaaS (daily usage, monthly).
- Default ports: 9080 (HTTP), 9443 (HTTPS). Integrations host: `integrations.drakma.com:9543`.

## What I learned (2026-11-12)
Topic: API7 3.10.9 and forwarded headers.
- A client can fake `X-Forwarded-Proto` and similar headers, which gives upstream services a wrong picture of the request. ✔️
- The NLB: my answer was that a **TLS listener** can write these headers, so it would need to be a trusted source. ⚠️ Re-check: an AWS NLB works at layer 4 and does **not** add `X-Forwarded-*` headers even with a TLS listener (client IP comes through as the source IP or via proxy protocol). Re-ask ~16 Nov.
- Q3 (an upstream behaviour that could break) not answered yet – re-ask ~16 Nov.

## 👥 People
API7: [[People#API7|Yuan Bao]] (support), [[People#API7|Zhi Yuan Ju]] (Head of Global) · Drakma: Sherry (infra), [[People#Drakma|Veeru]], [[People#Drakma|Ranjan]]

## 🔗 Notes & meetings
- [[Architecture]] · [[Introduction]] · [[Security overview for partners]]
- Meetings: [[2026-08-06 API7 onboarding]]
