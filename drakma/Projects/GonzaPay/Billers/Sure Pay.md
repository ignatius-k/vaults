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

## 📍 Status (12 Nov 2026)
- **Sprint-2 development starts 12 Nov.** UAT 4–8 Jan 2027, go-live 12 Jan 2027.
- First call with the Sure Pay team held **Mon 9 Nov** → [[2026-11-09 Sure Pay call]].
- **Credentials received** from [[People#Centenary Bank (CRDB)|Keneth Sululu]] by email on 10 Nov ("FW: Biller-Sure Pay CREDENTIALS"). Keep them in the password manager, not here.
- [[People#Drakma|Veeru]] (10 Nov) shared a document with [[People#Hitachi (HDPS)|Praneeth]] on the CR to "make this much simpler" – discuss.

## ✅ Tasks
- [ ] Test the core APIs: validate reference and make payment #gonzapay
- [ ] Onboard the Sure Pay API on the gateway #gonzapay
- [ ] Draft the API documentation (after testing) #gonzapay

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
- ❓ Is the access-token request handled on our side?

## 👥 People
[[People#Centenary Bank (CRDB)|Keneth Sululu]], [[People#Centenary Bank (CRDB)|Micheal Kalyango]] (Centenary) · [[People#Sure Pay|Elvis Onyango]] (Sure Pay) · Stella Nakamya (Centenary, on leave; cover: Elvis Kirya)
