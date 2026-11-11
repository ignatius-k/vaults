Which data is required for this project, maybe we can divide it depending on the users or expected functionalities
- Risk officer
- AML Analyst
- Rule tuner

**Functional information**
- Customer profiles
- Risk assessment profiles; score, assessment history 
- Transaction details, types, transactions 
- Party details; like institutions, billers, etc
- watchlists & sanctions; from external
- cases
- regulatory reports
- rules

**Supporting information**
- System users ie risk officers etc
- roles
- system audit logs

### Things to note
- the concrete customer profiles, will be obtained from the replica database, GonzaPay UAT database,
- but the customer profile in the system will be the customer's assessment profile

### Issues
- Graph analytics are not included
- Data replication, ie in the source and this applicatio