---
status: active
---
# API7 Gateway

## 🎯 Goal
Run all partner integrations (GPay, QRPe, URA, Airtel, MTP, SMS providers) safely through the API7 gateway.

## 📍 Status
- 2FA for the API7 dashboard needs a control-plane upgrade (and then a data-plane upgrade).

## ✅ Tasks
**Dashboard security (2FA)**
- [/] Send API7 the confirmation email with when the upgrade should be done #api7

**Africa's Talking (SMS)**
- [ ] Onboard Africa's Talking API in the gateway (PROD) #api7
- [ ] Test the integration #api7

**From older notes: please confirm if still open**
- [ ] URA changes incorporated #api7
- [ ] MTP integration and documentation shared #api7
- [ ] Airtel integration: callback + documentation from HDPS #api7
- [ ] Research advanced API routing #api7

## ⏳ Waiting on
- [ ] ⏳ Waiting on @API7: upgrade date for the control plane

## 🧠 Key facts & decisions
- 2FA with credential login chosen over SSO, because it's simpler.
- Gateways are hosted in our VPC and linked to API7's control plane.
- Default ports kept: 9080 (HTTP) and 9443 (HTTPS).
- URA: expose the endpoints as-is; Hitachi handles signature generation and OAuth2.

## 🔗 Notes & meetings
- [[Architecture]] · [[Introduction]] · [[Member bank traffic]]
- Meetings: see `Meetings/`
