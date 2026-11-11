---
status: active
partners: Stanbic, Pearl Bank (PBUG), Centenary, Hitachi (HDPS)
mode: do
review: review
review_note: "Confirm the 'from older notes' tasks (DB clean-up, mutual TLS, BigQuery)."
---
# QRPe

## 🎯 Goal
Take QRPe live with **Stanbic**, with all bank and Hitachi traffic going through the API7 gateway, and finish off-us testing with Pearl Bank and Centenary.

## 📍 Status (12 Nov 2026)
- ⚠️ **Stanbic year-end change freeze starts 25 Nov.** Stanbic put **SIT with the other banks on hold** until Drakma's APIs are stable (Imeldah, 4 Nov).
- **Off-us SIT session 1 (Fri 13 Nov) was cancelled.** Stanbic reported intermittent bank network issues on their side (11 Nov).
- **Partner portal and QRPe analytics are live in production.** For Stanbic we only need to enable them from the backend. Veeru sent the implementation plan to Stanbic on 11 Nov.
- **Bulk upload (on-us):** Hitachi generated the Stanbic QR codes (9 Nov); Stanbic is testing.
- **Inactive merchant:** API now returns status `INACTIVE` as documented; Julius retested and confirmed (4 Nov).
- **Merchant enquiry timeout:** merchant onboarding failing because TPS times out at token generation (Veeru → David, 10 Nov).
- **Gateway routing for Stanbic:** Hitachi shared the UAT client credentials (10 Nov – keep them in the password manager). UAT proxy server IP from Sherry: `15.0.2.232` (11 Nov).
- **SMS (Africa's Talking):** SMS through the gateway is done in UAT; MTN messages confirmed working (4 Nov).

## ✅ Tasks
**This week**
- [ ] Share the routing document with the Hitachi team on the "Routing Stanbic Inbound Traffic Through API Gateway" thread (Kithmini, 9 Nov) #qrpe
- [ ] Reply to Stanbic on "Testing the Partner Bank portal" (Imeldah tagged me, 11 Nov) #qrpe
- [ ] Keep the APIs stable so Stanbic can restart SIT before the 25 Nov freeze #qrpe

**Stanbic go-live**
- [ ] Share Stanbic go-live details with Veeru #qrpe
- [ ] Make sure Stanbic gets the QR codes #qrpe
- [ ] Onboard Stanbic's API in the production gateway once shared, then share credentials with Hitachi #qrpe
- [ ] Share the message-signing certificate with the Stanbic team #qrpe
- [ ] Get dummy merchants from Stanbic to test merchant settlement #qrpe
- [ ] VPN documentation and network matrix, with Sherry and Veeru #qrpe

**Gateway onboarding (SIT)**
- [ ] Onboard the QRPe API in the gateway #qrpe
- [ ] Test the API with the shared credentials #qrpe
- [ ] Once tested, tell the banks to map **qaintqrpe.drakma.com** to the new gateway IP #qrpe

**Merchant authentication**
- [ ] Tell Veeru about Ranjan's proposal and its advantages #qrpe
- [ ] Provide mockups for the proposal #qrpe

**From older notes – please confirm if still open**
- [ ] Clean up the QRPe tables in the GonzaPay database #qrpe
- [ ] Mutual TLS between member banks and QRPe; log all member-bank requests #qrpe
- [ ] Hitachi: grant administration, set up BigQuery and consume events #qrpe

## ⏳ Waiting on
- [ ] ⏳ Waiting on @Hitachi: review of the QRPe documentation
- [/] ⏳ Waiting on @Stanbic: production access to the **Flexipay Drakma Merchant Settlement** API + credentials (partly done)
- [ ] ⏳ Waiting on @Stanbic: new SIT date after the API stability check

## 🧠 Key facts & decisions
- **No load balancer in SIT:** banks reach the gateway directly, so they must change the DNS for qaintqrpe.drakma.com. In **production** an **NLB** sits in front of the gateway.
- **Gateway placement (Sherry, 26 Oct):** gateway EC2 instance goes between the proxy server, the EKS microservices and the external bank – inbound from the load balancer to the proxy, outbound from EKS pods to the bank.
- **Signing:** Centenary & PBU use HMAC-SHA256 with a security key; Stanbic uses an RSA-signed SHA256 of the payload plus an OAuth2 access token. See [[API7 Integration]].
- **Data needed from Stanbic:** client ID, client secret, auth production URL, API production URL, message-signing certificate.
- **Merchant authentication options:** (1) OTP/code given to the teller by the main merchant; (2) password + approval by the main merchant. Ranjan's proposal validates requests before they reach the merchant.

## 👥 People
Stanbic: Imeldah Nalubowa, Julius Nasasira, Victor Ssebugwawo · Hitachi: Anuruddha Bandara, Tishara Kodithuwakku · Pearl Bank: Phillip Makwasi, Caroline Abenaitwe · Drakma: Veeru, Kithmini, Sherry

## 🔗 Notes & meetings
- [[Go-live]] · [[API7 Integration]]
- Meetings: [[2026-07-29 QRPe plan review]] · [[2026-08-03 QRPe]] · [[2026-09-04 Stanbic questions]]
