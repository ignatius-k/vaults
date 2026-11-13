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

## 📍 Status (13 Nov 2026)
- **Stanbic on-us production go-live: tentatively today, 13 Nov.** [[People#Drakma|Veeru]]'s implementation plan lists what we must hand over (see Stanbic go-live tasks). Kithmini asked Stanbic (13 Nov) to share their items so we can move to production.
- **MOU finalised** and out for signatures (Veeru → Hitachi, 12 Nov). Hitachi to update the QR template with all bank logos.
- **Partner portal (UAT):** users re-created to match Stanbic's new user matrix ([[People#Drakma|Sai]], 13 Nov). Testing call with Stanbic **today 15:00–15:30**.
- **VPN Stanbic ↔ Drakma is down** since last week; [[People#Drakma|Sherry]] asked [[People#Stanbic|Victor]] to check (12 Nov).
- Stanbic asked for Drakma's rollback steps; Veeru replied it's config only and can be rolled back (12 Nov).
- ⚠️ **Stanbic year-end change freeze starts 25 Nov.** Stanbic put **SIT with the other banks on hold** until Drakma's APIs are stable ([[People#Stanbic|Imeldah]], 4 Nov).
- **Off-us SIT session 1 (Fri 13 Nov) was cancelled.** Stanbic reported intermittent bank network issues on their side (11 Nov).
- **Partner portal and QRPe analytics are live in production.** For Stanbic we only need to enable them from the backend. [[People#Drakma|Veeru]] sent the implementation plan to Stanbic on 11 Nov.
- **Bulk upload (on-us):** Hitachi generated the Stanbic QR codes (9 Nov); Stanbic is testing.
- **Inactive merchant:** API now returns status `INACTIVE` as documented; [[People#Stanbic|Julius]] retested and confirmed (4 Nov).
- **Merchant enquiry timeout:** merchant onboarding failing because TPS times out at token generation ([[People#Drakma|Veeru]] → David, 10 Nov).
- **Gateway routing for Stanbic:** Hitachi shared the UAT client credentials (10 Nov – keep them in the password manager). UAT proxy server IP from [[People#Drakma|Sherry]]: `15.0.2.232` (11 Nov).
- **SMS (Africa's Talking):** SMS through the gateway is done in UAT; MTN messages confirmed working (4 Nov).

## ✅ Tasks
**This week**
- [x] Share the routing document with the Hitachi team on the "Routing Stanbic Inbound Traffic Through API Gateway" thread ([[People#Drakma|Kithmini]], 9 Nov) #qrpe ✅ 2026-11-09 (sent to [[People#Hitachi (HDPS)|Anuruddha]] 9 Nov; Hitachi reviewing)
- [x] Reply to Stanbic on "Testing the Partner Bank portal" ([[People#Stanbic|Imeldah]] tagged me, 11 Nov) #qrpe ✅ 2026-11-12
- [ ] Keep the APIs stable so Stanbic can restart SIT before the 25 Nov freeze #qrpe

**Stanbic go-live**
- [x] Share Stanbic go-live details with Veeru #qrpe ✅ 2026-11-13
- [ ] Make sure Stanbic gets the QR codes #qrpe
- [ ] Onboard Stanbic's API in the production gateway once shared, then share credentials with Hitachi #qrpe
- [ ] Get Stanbic's member-bank API details and onboard it on the gateway (per Veeru's implementation plan) #qrpe 📅 2026-11-13
- [ ] Test the Stanbic APIs, especially **merchant inquiry** – ask Stanbic for a test merchant code #qrpe
- [ ] Get the credentials banks need to call QRPe from [[People#Hitachi (HDPS)|Tishara]] and share them with Stanbic #qrpe
- [ ] Share the **mutual-TLS certificate** we use when calling Stanbic's server #qrpe
- [ ] Share the message-signing certificate with the Stanbic team #qrpe
- [ ] Follow up with [[People#Drakma|Sherry]] that the Stanbic ↔ Drakma VPN is up (down as of 12 Nov) #qrpe
- [ ] Get dummy merchants from Stanbic to test merchant settlement #qrpe
- [ ] VPN documentation and network matrix, with [[People#Drakma|Sherry]] and Veeru #qrpe

**Gateway onboarding (SIT)**
- [ ] Onboard the QRPe API in the gateway #qrpe
- [ ] Test the API with the shared credentials #qrpe
- [ ] Once tested, tell the banks to map **qaintqrpe.drakma.com** to the new gateway IP #qrpe

**Merchant authentication**
- [ ] Tell Veeru about [[People#Drakma|Ranjan]]'s proposal and its advantages #qrpe
- [ ] Provide mockups for the proposal #qrpe

**From older notes – please confirm if still open**
- [ ] Clean up the QRPe tables in the GonzaPay database #qrpe
- [ ] Mutual TLS between member banks and QRPe; log all member-bank requests #qrpe
- [ ] Hitachi: grant administration, set up BigQuery and consume events #qrpe

## ⏳ Waiting on
- [ ] ⏳ Waiting on @Hitachi: review of the QRPe documentation
- [ ] ⏳ Waiting on @Hitachi ([[People#Hitachi (HDPS)|Pasidu]], [[People#Hitachi (HDPS)|Manjula]]): review of the Stanbic routing document (asked by [[People#Hitachi (HDPS)|Anuruddha]], 10 Nov)
- [/] ⏳ Waiting on @Stanbic: production access to the **Flexipay Drakma Merchant Settlement** API + credentials (partly done)
- [ ] ⏳ Waiting on @Stanbic: new SIT date after the API stability check
- [ ] ⏳ Waiting on @Stanbic ([[People#Stanbic|Victor]]): check why the VPN tunnel is down (Sherry, 12 Nov)
- [ ] ⏳ Waiting on @Stanbic: their production items for go-live (Kithmini chased 13 Nov)

## 🧠 Key facts & decisions
- **No load balancer in SIT:** banks reach the gateway directly, so they must change the DNS for qaintqrpe.drakma.com. In **production** an **NLB** sits in front of the gateway.
- **Gateway placement (Sherry, 26 Oct):** gateway EC2 instance goes between the proxy server, the EKS microservices and the external bank – inbound from the load balancer to the proxy, outbound from EKS pods to the bank.
- **Signing:** Centenary & PBU use HMAC-SHA256 with a security key; Stanbic uses an RSA-signed SHA256 of the payload plus an OAuth2 access token. See [[API7 Integration]].
- **Data needed from Stanbic:** client ID, client secret, auth production URL, API production URL, message-signing certificate.
- **Merchant authentication options:** (1) OTP/code given to the teller by the main merchant; (2) password + approval by the main merchant. [[People#Drakma|Ranjan]]'s proposal validates requests before they reach the merchant.

## 👥 People
Stanbic: Imeldah Nalubowa, [[People#Stanbic|Julius Nasasira]], [[People#Stanbic|Victor Ssebugwawo]] · Hitachi: Anuruddha Bandara, [[People#Hitachi (HDPS)|Tishara Kodithuwakku]] · Pearl Bank: [[People#Pearl Bank|Phillip Makwasi]], [[People#Pearl Bank|Caroline Abenaitwe]] · Drakma: Veeru, [[People#Drakma|Kithmini]], Sherry

## 🔗 Notes & meetings
- [[Go-live]] · [[API7 Integration]]
- Meetings: [[2026-07-29 QRPe plan review]] · [[2026-08-03 QRPe]] · [[2026-09-04 Stanbic questions]]
