---
mode: learn
review: update
review_note: "Says 'only successful transactions' – the system now includes failed ones. Update that line."
---
The required output format of transaction should include
- transaction date - **REQUIRED**
- transaction reference - **REQUIRED, UNIQUE**
- source ideally the customer's wallet - **REQUIRED**
- destination i.e the recipient wallet - **REQUIRED**
- transaction type - **REQUIRED**
- amount - **REQUIRED**
- intermediary

For optimized querying based on time, I suggest this should be a time indexed table, hence **Time-series DB**, with index as transaction date, and composite key as  transaction date + transaction reference

Only successful transactions are to be considered

**Agent Transactions**
Table name: ==rpt_bi_trxn_agent_det==
*Transactions*:
- Topup from Agent - 93
- Withdrawal Accept - agent (Voucher Redemption) - 391
==NOTE==: , agent not wallet, agent ID from the bank

Successful: trx_stat = 1 and setl_status = 1

**Bill Payment transactions**
Table name: ==rpt_bi_trxn_bill_pay_det==
*Transactions*:
- Bill Payment - 06

Successful: trx_stat = 1 and setl_stat = 1

==Note== : Here, the recipient doesn't have a wallet ID, 
Suggestions: To be handled as internal entities, type "BILLER" - "BillerID - BillerName" in the system

**Bank Transactions**
Table name: ==rpt_bi_trxn_bnk_det==
*Transactions*:
- Topup from account - 90, the ==source== is not wallet, though the account is the recipient's account
- Wallet to bank fund transfer - 601, the ==recipient== is not wallet, but the customer's account

Successful: trx_stat = 1 and setl_stat = 1

**Wallet Transactions**
Table name: ==rpt_bi_trxn_wlt_det==
*Transactions*:
- Topup from Airtel - 91
- Topup from MTN - 92
- Wallet to wallet fund transfer - 600
- Wallet to mobile fund transfer - 602
- Wallet to wma fund transfer - 603 (ok)

Successful: trx_stat = 1 and setl_stat = 1

==Note==:
- the source is not wallet but customer's number for top-ups
- Wallet to mobile fund transfer, the recipient is customer's mobile number




