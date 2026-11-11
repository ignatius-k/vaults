---
mode: learn
review: ok
review_note: "Reference: how each bank signs requests."
---

1) QR Service - **AS SERVER** - Member banks(Clients) requesting QRPe(Server)
		Just forward the request as-is from the client

		[member bank] -> [API Gateway] -> [QRPe]

	- Required
		- QR Service UAT API
		- member banks are **consumers**


2) QR Service - **AS CLIENT** - QRPe(Client) requesting Member Banks

		[QRPe] -> [API Gateway] -> [member bank]

	1) Centenary & PBU -- **Standard**
		- Headers
			- Signature  - HMAC-SHA256(==security_key==, SHA256(==password== + payload))
			- Security key - ==security_key==
	
	2) Stanbic
		- Headers
			- Signature - ENCRYPT(SHA256(payload), ==private_key==)
			- Authorization - ==access_token==
				- OAuth2 - ==client_id==, ==client_secret==
				
		- Required
			- Demo Application - calling member bank APIs
			- On board

QRPe - As a Client
- What is expected from Hitachi
	- same payload
	- url ie for each client  - https://.../[bank_name]/

- What is expected by servers?
	- different auth
	- different headers
	- different credentials

		- Case Scenario: Stanbic
			- auth: OAuth2

Suggested Actions 
1) Use server-less functions for both cases
	1) OAuth2
		- server-less function; lockable lua-resty-lock something, and token refresh
	2) Signatures
		- serverless function - ==Note==: Is delegating "hashing + encrypting" to an external worth it?? 

Steps:
1) First, workout OAuth2 
2) Then, work out signature
3) Then, measure performance and identify areas of improvement and try improving it
