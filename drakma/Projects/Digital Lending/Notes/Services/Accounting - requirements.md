---
mode: learn
review: ok
review_note: "Requirements reference."
---
1. The master accounts are to be created per product variant, not per product
2. Every posting in the loan accounting is a transaction, and every transaction has a reference to handle double postings, or for idempotency - hence in transactions, a reference has to be stored
3. The transactions include disbursement; which covers the loan disbursement, and top up since it is the same, charge which covers the charges posted on loan account, accrual which covers the interest & penalty accruals
4. The postings need a change
	- Currently, 

There are three types of accounts 
1. Principal
2. Charge - For any charge
3. Interest - For interests, and penalties

Each variant and each loan account keeps three ledger accounts. No cash, bank or income accounts are added. The product accounts hold the product's side of every posting. They are no longer titled "Receivable"; they are named Product Principal, Product Charge and Product Interest.

Negative is a debit and positive is a credit, for every transaction type.

- A negative loan account balance is the amount the customer owes, and zero means fully repaid.
  - A positive loan account balance means the customer is in credit (overpaid).
  - A positive variant account balance is the product's total outstanding across its loans.


3. Posting rules

┌────────────────────────────────────┬─────────────────────────────────┬────────────────┐
│            Transaction             │          Loan account           │    Product     │
│                                    │                                 │    account     │
├────────────────────────────────────┼─────────────────────────────────┼────────────────┤
│ Disbursement: principal            │ Principal −                     │ Principal +    │
├────────────────────────────────────┼─────────────────────────────────┼────────────────┤
│ Disbursement: Added charge         │ Fee −                           │ Fee +          │
├────────────────────────────────────┼─────────────────────────────────┼────────────────┤
│ Disbursement: Deducted charge      │ Fee −, then Fee + (settled from │ Fee +, then    │
│                                    │  the payout)                    │ Fee −          │
├────────────────────────────────────┼─────────────────────────────────┼────────────────┤
│ Top-up                             │ Principal −                     │ Principal +    │
├────────────────────────────────────┼─────────────────────────────────┼────────────────┤
│ Interest accrual                   │ Interest −                      │ Interest +     │
├────────────────────────────────────┼─────────────────────────────────┼────────────────┤
│ Collection: fee, then interest,    │ + on each                       │ − on each      │
│ then principal                     │                                 │


Remember, if the product sets up a charge and the charge is pre-deducted,
ie on disbursement even the top-ups

5. Income reporting
Fee and interest income for a period is the sum of the positive (credit) entries on Product Fee and Product Interest. Collection entries on those accounts are not income.


6. The service also has to expose the endpoints, for loan account - Responsible for providing a consolidated view for loan account
7. This is to be applied on the variant
8. Also for faster queries, suggest a snapshot of ledger accounts to reduce the querying

ok, so we go with daily balances end of day with grace period and recheck, 
to handle postings happening later, each posting ie transaction provides its process date, which is also included & recorded in the transaction, but the entries posted from transaction are processed, there process date or added date is the date they are processed in the accounting, to reduce need for back processing hence no need for business date on entries






