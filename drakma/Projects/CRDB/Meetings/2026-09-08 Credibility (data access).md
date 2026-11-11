- Data is to be processed in **only** bank environment
- Impression; GonzaPay user different from Bank user (not existing yet in GonzaPay) -- GonzaPay user accept T&c's then we collect their info for scoring

- encrypted fields; 
	- who is responsible -- Data Processing Unit ??? [Mark not sure]
	- when are they decrypted -- Not decrypted, just customer_id used then, customer table we are storing the user-provided nin, phone_number

- ~~CRB Processing to be done by the scoring engine, and not DPU~~ not reverted, CRB processing/querying to be done within bank, cause parameters needed are only accessible by DPU in bank environment

- the flow 
