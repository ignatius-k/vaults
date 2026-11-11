---
date: 2026-09-17
project: Digital Lending
type: meeting
mode: do
review: ok
review_note: "History – kept as written."
---
# CRDB – Eligibility pre-scoring – 2026-09-17

> Old note, kept as written. Decisions and actions from it are in the [[Digital Lending]] hub.

- product code generation - 
- variant code generation

eligibility stored with product details

- eligible products computed on the fly, or computed pre - baseline using **300_000** customers as the base
	- pre-computed
		- when a variant is changed, or added -- the whole customer base has to be evaluated based on this new change
			- if the whole base is already scored, then a variant is added or changed, all the customer base ie **300_000** needs to be re-evaluated/re-filtered against this new change, as the eligibility updated
				- what does re-evaluation look like
					- we(loan_processor) send the new variant information, to any service having customer information ie customer_serivce, scoring_engine, and it sends back all the customer ids that are eligible for this new variant , then the loan_processor updates the eligibility and removes the eligibility for customers, not in the sent listing
		- if there are 4 products with 2 variants each, assume average each customer is eligible for 3 variants, then the size of the eligibility table grows to **300_000 * 3**, since customers are referenced by code, to keep performance in check, things need to be considered
			- customer_code has to be indexed, and numeric
			- variant_code has to be indexed, and numeric

- 