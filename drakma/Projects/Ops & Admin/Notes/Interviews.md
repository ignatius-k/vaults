- musiimenta joachim
	- demonstrated attitude to learn, listening, collaborative
	- enough experience in both frontend and backend,  to support on projects
	- 


- benjamin mayanja
	- didnt demosnteate attitude to learn, or being collaborative
	- enough experience in both frontend and backend,  to support on projects
	- didnt demostrate enough ,, to conclude whether he is well conversant with full development life cycle, ie deployments

compare with the SAD document in res

loan processor; expose an endpoint to access the score of customer; ie their eligibility which includes customer_id, score, financial_eligibility., this is to be used by certain service to send score to the loan processor, this should accept batch, the score is sent and also include breif information of the customer
ie their customer_id, date_expires maybe more information will be provided

then loan processor, stores the custoemr's eligibility, so when cleint makes a request to see their eligibility the loan processor makes request for the loan products from the product service, ie all 

maybe a t start, it queries the product information form product service, where the product variants are returned with al their information that needs to be displayed to customer

then whn client makes request for customer eligibility ie with customer id; the loan processor checks its customer_eligibilty, then if it exists it checks the product or variants the custoemr is eligible for merges and sends response



and then sends the response to the customer; 

then customer can view their eligiility,,the client is the miniapp