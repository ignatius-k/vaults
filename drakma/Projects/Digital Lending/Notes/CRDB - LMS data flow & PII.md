---
mode: think
review: review
review_note: "Check it matches the answers Drakma sent to Centenary's risk team on 22 Oct."
---
- Why is it needed
	- to illustrate the process/interactions, that occur between the Bank's systems, the Data Process Unit
	- also to illustrate how the data being requested is stored and when its used, and where it is sent specifically the PII

	- in this setup, PII includes; NIN, Phone number, Account number, and when is this PII needed
	
- what are the key process flow to illustrate this
	- the first scoring, ie first time the customer's eligibility is computed 
	- the customer accessing the platform to apply for the first time
	- the state of the data being and how it is introduced in these systems

- assumptions
	- the bank sends unecrypted PII information to the DPU since it is in the same environment
	- the bank send encrypted PII information


bank engineering and us(the lms developer)

- initial scoring (Process 1);
	- eligibility of customer is computed

- customer's first encounter with the system to view their eligibility (Process 2)
	
- rescoring (Process 3)
	- customer is now known, and system needs an updated or recent transaction statement of the customer
	- 