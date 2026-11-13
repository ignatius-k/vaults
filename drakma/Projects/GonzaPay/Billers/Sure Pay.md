---
project: GonzaPay
cr: CR-013 Biller-Sure Pay
status: development starting
mode: do
review: ok
review_note: "Current – development starts 12 Nov."
---
# Sure Pay (CR-013)

School-fees payments through GonzaPay. Part of [[GonzaPay]].

## 📍 Status (13 Nov 2026)
- **Core APIs fully tested** (12–13 Nov). Next: gateway onboarding, the OAuth/signing plugin, and the API documentation for Hitachi.
- **Sprint-2 development started 12 Nov.** UAT 4–8 Jan 2027, go-live 12 Jan 2027.
- First call with the Sure Pay team held **Mon 9 Nov** → [[2026-11-09 Sure Pay call]].
- **Credentials received** from [[People#Centenary Bank (CRDB)|Keneth Sululu]] by email on 10 Nov ("FW: Biller-Sure Pay CREDENTIALS"). Keep them in the password manager, not here.
- [[People#Drakma|Veeru]] (10 Nov) shared a document with [[People#Hitachi (HDPS)|Praneeth]] on the CR to "make this much simpler" – discuss.

## ✅ Tasks
- [x] Test the core APIs: validate reference and make payment #gonzapay ✅ 2026-11-13
	- account 1613900001 returned a negative outstanding balance
- [ ] Onboard the Sure Pay API on the gateway #gonzapay
- [ ] Build the gateway plugin for Sure Pay: OAuth token + signature generation (see Decision) #gonzapay #api7
- [ ] Write the API documentation and share it with Hitachi #gonzapay

## ⏳ Waiting on
-

## 📋 Dependencies (Kithmini, 1 Oct)
1. Updated API spec
2. UI/UX with logos
3. API connectivity
4. Test data
5. Reporting, incl. EMDRS (same views)
6. Settlement accounts
7. Fee structure
8. Limits
9. Package information

## 🧠 Key facts
- No **pending** status.
- **Partial payments** always allowed.
- **Minimum fees** not strictly enforced.
- ✅ Access token and signature are handled **by the gateway** (decided 12 Nov).

## Decision (2026-11-12)
**The gateway handles the Sure Pay OAuth call and the signature generation** (not Hitachi's backend).
Why / open points: design it for scale and for auth-service outages – how the token is cached and refreshed across gateway nodes, and what happens when Sure Pay's auth service is slow or down. → today's Think (13 Nov).
Follow-up: plugin task added above.

## 👥 People
[[People#Centenary Bank (CRDB)|Keneth Sululu]], [[People#Centenary Bank (CRDB)|Micheal Kalyango]] (Centenary) · [[People#Sure Pay|Elvis Onyango]] (Sure Pay) · Stella Nakamya (Centenary, on leave; cover: Elvis Kirya)
