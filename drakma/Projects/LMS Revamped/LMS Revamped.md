---
status: active
---
# LMS Revamped

## 🎯 Goal
Rebuild the loan management system as separate services: product, customer, loan processor, loan accounting, payments, operations, scoring, notifications.

## 📍 Status
- Product service: done. Customer service: done.
- To do: loan processor, loan accounting, payments processor, operations service, loan servicing, scoring engine, notifications service.

## ✅ Tasks
- [ ] Product service changes #lms
- [ ] Integration between the product service and the loan processor #lms
- [ ] Loan processor #lms
- [ ] Loan accounting #lms

**From older notes: please confirm if still open**
- [ ] Service-to-service authentication and authorization (X-User-Token, X-Request-ID) #lms
- [ ] Docker Swarm for service discovery #lms

## ⏳ Waiting on
-

## 🧠 Key facts & decisions
- Back-office login: the operations service issues and signs JWTs (at least userId, username, roleId). Other services check the signature with the public key.
- Each service defines its own permissions; the operations service builds roles from them. Role lookups are cached.
- Every request carries an X-Request-ID that's kept as it passes between services, for tracing.
- The CSE shares only eligibility: category, financial eligibility and credit score.

## 🔗 Notes & meetings
- [[LMS Project Scope; tasks and subtasks]] · [[service discovery]] · [[Product eligibility & customer classification]]
- Services: see `Notes/Services/`
- Meetings: see `Meetings/`
