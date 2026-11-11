1. Partner portal

2. UAT Tests for ONUS transactions

3. **Onboarding Stanbic API in production; API Gateway

	NOTE: In production, do we expect the gateway to handle inbound traffic ie requests from Stanbic to QRPe Service
	
	**Steps involved**
	- Deploy an API Gateway instance in production

	- Create Hitachi's Gateway access credentials, and share with them

	- Onboard Stanbic's Member Bank API on the Gateway, for Hitachi to consume, and add observability, plus alerts, ==🔵things to note==
		- **Merchant Inquiry** - Used when onboarding a merchant, however, now we are using bulk upload, which doesn't require this endpoint
		- **Merchant Settlement** - To settle merchant, however, this is for OFF-US transactions
		- **Transaction Inquiry** - To inquire about the merchant_settlement transaction, hence this is also OFF-US
	
	- Share the message signing certificate with Stanbic team
	
	- Test the onboarded API, end to end
		- **Issues**:
			-- For merchant settlement to be tested, then dummy merchants are needed from Stanbic

VPN documentation
Network matrix like Pearl Bank

