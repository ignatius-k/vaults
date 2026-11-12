---
project: GonzaPay
cr: CR-004 Biller-Motor Third Party
status: in progress
mode: do
review: review
review_note: "Confirm the 3 ❓ items: 400-response fields, IDD review, solution document review."
---
# Motor Third Party – MTP (CR-004)

Motor third-party insurance payments through GonzaPay, via **ServiceCops** (the MTP system). Part of [[GonzaPay]].

## 📍 Status (12 Nov 2026)
- APIs onboarded on the gateway and given to the backend team (UAT credentials sent to [[People#Hitachi (HDPS)|Praneeth]], 21 Oct; base URL on `integrations.drakma.com:9543`).
- **UI/UX document waiting for bank approval** – [[People#Drakma|Veeru]] asked [[People#Centenary Bank (CRDB)|Keneth]], [[People#Centenary Bank (CRDB)|Beth]] and [[People#Centenary Bank (CRDB)|Micheal]] to approve (11 Nov).
- UAT 10–14 Dec, go-live 20 Dec (moved 10 days because of a 15-day delay getting API information).
- [[People#Centenary Bank (CRDB)|Micheal]] (11 Nov): the schedule is still as in his 20 Oct email.
- ❓ Dates disagree (11 Nov mails): ServiceCops expects UAT from **23 Nov** with sign-off 30 Nov; Micheal said UAT starts **30 Nov** once the app is ready; DCP says UAT **10 Dec**. Which is right?

## ✅ Tasks
- [ ] Reply to [[People#Drakma|Kithmini]]: which fields come back on a **400** response (asked 26 Oct) ❓ already answered? #gonzapay
- [ ] Review the MTP internal design document (IDD) uploaded by [[People#Drakma|Kithmini]] (29 Oct) ❓ done? #gonzapay
- [ ] Review the GonzaPay MTP solution document (Kithmini, 28 Oct) ❓ done? #gonzapay

## ⏳ Waiting on
- [ ] ⏳ Waiting on @Centenary ([[People#Centenary Bank (CRDB)|Keneth]], [[People#Centenary Bank (CRDB)|Beth]], Micheal): approval of the MTP UI/UX document

## 🧠 Key facts & decisions
- **We can't use the sticker and vehicle-policy endpoints.** ServiceCops limits policy details to insurers and their agents. Our scope: collect the money, **notify payment**, deposit to UIA's account at Centenary. The MTP system sends the details to the customer's phone, and they use those to get the sticker. (Micheal, 27 Oct)
- `validate-vrn` returns `returnCode 100` / `successful: false` when the vehicle already has an active policy.
- `process payment` must be called to tell MTP about a payment; if it fails, retry with the same request. `initiate_payment` is in scope but not needed.
- UAT settlement account for MTP: given by Keneth on 16 Oct (see the CR comments).

## 👥 People
Micheal Kalyango, Keneth Sululu, Beth Nabukenya (Centenary) · [[People#ServiceCops|Maxwell Opio]], M. Muhereza (ServiceCops) · [[People#Hitachi (HDPS)|Praneeth]], [[People#Hitachi (HDPS)|Anuruddha]], [[People#Hitachi (HDPS)|Umaya Delpachithra]] (Hitachi)

## 🔗 Links
- [[MTP integration notes]]
- DCP: GonzaPay → CR-004
