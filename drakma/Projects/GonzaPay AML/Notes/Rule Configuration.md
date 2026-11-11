Currently, rules are defined by
- the transactions they affect ie the transaction types, or all
- then also the volume of transactions they affect

I think its safe to have configurations for identifying the transactions on which the rule its going to apply, ie by trnasaction type, source type ie where source is wallet, phone number etc, or even the destination type

the definition of rule I think can be obtained from how a rule is to be used

- for transaction, we identify whether this rule is affecting the transaction, ie the transaction type, source type, destination type etc, amount range

- if its affecting the transaction, we identify whether the rule requires a single transaction or multiple transaction
-for multiple transaction, these are kinda rolling window, ie it requires the past hour, or past day, or past 6 hours, or past ...., [duration should be configurable on the rule] transactions,  of the key figure [this could be the source or recipient] linked in the transaction

- now, after identifying the transactions its affecting, ie if single transaction then that's the list of one transaction its affecting, if multiple transaction in the window that is the list its affecting

- we define the conditions its checking for the [transactions its affecting] to be considered as breaking the rule, or captured by the rule

- am wondering how conditions could be done
	- one way user uses defined attributes and provides range or values that rule captures, a not configurable, a defined object where user just provides the vlaues, say with the affected transaction at the backend we create an object with attrbutes like unique recipients, unique sources, total amount, average amount, ...., with computed values, then reference these attribute value s against the ranges
	- another way, user build the conditions themselves using some defined attributes, and aggregate known in the back

then if the affected transactions pass the condition, an alert is created 
linked to the transactions that triggered it


there is some confusion in the 
say we have rules say like 20 rules, then transaction defined by (source_type, destination_type, amount) comes we need to evaluate this transaction across these rules and check

to reduce the number of rules that need to be executed/checked for every transaction, we use the targeting filter
for example, a rule might be applying to only "AIRTEL TOUP, MTN TOPUP", and also apply to only transactions with amount [1000000, 2000000]
here you see that we 

and another rule applies to only transactions where source_type is wallet, and destination_type ois wallet

so all this are being used to reduce the number of rules that are going to be evaluated/checked on this transaction

also the trageting filter comes before the scope unless you have reason for the current order


after knowing whether the transaction is targeted by the rule
the rule esp. if its transaction based, it defines the transactions or transaction needed to check whether the current/triggering transaction 

so the rule defines itself whether its single-transaction ie its evaluated on only that triggering transaction, or multi-transaction ie the rule is evaluated against multiple transactions so here we query for transactions say those linked to the source or destination, then these transactions are the one used to run an evaluation of the rule

so, for scope we need to know whether the rule is single-transaction
or multi-transaction, if multi-transaction you have to specify transaction from who in the triggering transaction which could be the source or destination, but now transactions in which range ie last hour, last 6 hours, last 24 hours, the custom should not be defined in seconds maybe minutes, for usability, when defining custom the user selects the [hour, day] and they provide number


some rules 
