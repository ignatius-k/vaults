---
status: active
---
# QRPe

## 🎯 Goal
Take QRPe live with Stanbic, with all bank and Hitachi traffic going through the API7 gateway.

## 📍 Status
- QRPe documentation shared with Hitachi; their review is pending.
- Stanbic production go-live in progress (see [[Go-live]]).

## ✅ Tasks
**Stanbic go-live**
- [ ] Share Stanbic go-live details with Veeru #qrpe
- [ ] Make sure Stanbic gets the QR codes #qrpe
- [ ] Email Stanbic for the production URL and credentials #qrpe
- [ ] Onboard Stanbic's API in the production gateway once shared, then share credentials with Hitachi #qrpe
- [ ] Share the message-signing certificate with the Stanbic team #qrpe
- [ ] Get dummy merchants from Stanbic to test merchant settlement #qrpe
- [ ] VPN documentation and network matrix, with Sherry and Veeru #qrpe

**Gateway onboarding (SIT)**
- [ ] Get SIT test credentials from Tishara #qrpe
- [ ] Onboard the QRPe API in the gateway #qrpe
- [ ] Test the API with the shared credentials #qrpe
- [ ] Once tested, tell the banks to map **qaintqrpe.drakma.com** to the new gateway IP #qrpe

**Merchant authentication**
- [ ] Tell Veeru about Ranjan's proposal and its advantages #qrpe
- [ ] Provide mockups for the proposal #qrpe

## ⏳ Waiting on
- [ ] ⏳ Waiting on @Hitachi: review of the QRPe documentation
- [/] ⏳ Waiting on @Stanbic: production access to the **Flexipay Drakma Merchant Settlement** API + credentials (partly done)

## 🧠 Key facts & decisions
- **No load balancer in SIT:** partner banks reach the gateway directly, so they must change the DNS for qaintqrpe.drakma.com. In production there is an **NLB** in front of the gateway.
- Hitachi may block direct access from member banks to the proxy server.
- **Data needed from Stanbic:** Client ID, Client Secret, Authentication production URL, API production URL, message-signing certificate.
- **Merchant authentication options:**
  1. OTP/code: the main merchant (or a user they allow) gives the code to the teller.
  2. Password + approval: the login request is checked with the password, then sent to the main merchant to approve.
  - Ranjan's proposal: requests are validated before they reach the merchant, and merchant and teller don't need to talk to log in.

## 🔗 Notes & meetings
- [[Go-live]] · [[API7 Integration]] · [[Onboarding QRPe APIs to the Gateway]]
- Meetings: see `Meetings/`
