	- OTC
	- IP addresses
	- Integrated on the Telecos

Gateway Integration
1. Is the access token request to be handled on our side?
2. Paying school fees, how are partial payments handled
3. Status - pending, do school fees payments also have pending payments


---

### API7 Gateway: Security Overview

#### 1. Authentication: who is calling?

“Every request must prove who it is before it reaches our systems.”

- **Key Auth**: Each client gets its own API key.
- **Basic Auth**: Standard username and password over HTTPS.
- **JWT**: Signed tokens, checked for signature and expiry on every call.
- **OIDC / SAML**: Connects to the bank’s identity provider for single sign-on.
- **HMAC**: Each request is signed, so the gateway can tell if it was changed in transit.
- **Multi-Auth**: One API can accept more than one method.

#### 2. Authorization: what can they do?

“Being logged in is not enough. Each client can only reach what it is allowed to.”

- **ACL**: Allow lists and block lists per client, route or service.
- **RBAC**: Access is based on roles, so each group only gets what it needs (least privilege).

#### 3. Traffic and runtime protection

“The gateway protects our backend from abuse and attacks.”

- **Rate limiting**: Caps requests per client or per IP, which helps against brute-force and DDoS.
- **IP restriction**: Only approved IP ranges can connect.
- **WAF**: Blocks common attacks like SQL injection and cross-site scripting.

#### 4. Encryption and secrets

“Data is encrypted in transit, and secrets are not stored in plain text.”

- **TLS**: TLS 1.2 is the minimum and TLS 1.3 is supported. Old versions (1.0 and 1.1) are disabled.
- **End-to-end encryption**: HTTPS from the client to the gateway and from the gateway to the backend.
- **mTLS**: Both sides show certificates, so only trusted systems can connect.
- **Secret management**: Keys can be kept in a vault, such as HashiCorp Vault, instead of in the configuration.

#### 5. Logging and audit ✅ configured

“We can see who did what, and when.”

- All API traffic is logged.
- Admin changes to the gateway are recorded in an audit trail.

#### 6. Admin access ✅ RBAC

“Only authorized staff can change gateway settings, and each person only has the permissions their role needs.”

#### 7. Vendor certifications ✅

“Our gateway vendor, API7, is independently audited.”

- **ISO/IEC 27001:2022**
- **SOC 2 Type II**
- **HIPAA** and **GDPR**
- API7 can provide its SOC 2 report and penetration test report on request.


ACL and Access Management to resources
- How access is requested by internal and external parties
- How often is access reviewed
- How is acc

Application Level Secure Testing

Incident Response Plan & Plan evaluation

Resilience backup & Disaster Recovery

Recovery Tests - Report on recovery of data backup, process