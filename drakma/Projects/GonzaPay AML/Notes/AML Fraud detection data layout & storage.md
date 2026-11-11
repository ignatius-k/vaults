---
mode: think
review: review
review_note: "Early research (July) with no final decision. Record what was chosen, or move to Archive."
---
Getting the right data layout for the system
- [[#How is data usually stored (industry-recommended)?]]
- [[#What data storage/ layout is to be used?]]
- [[#Which concerns are to be considered with this layout?]]
## How is data usually stored (industry-recommended)?

Into consideration,
- Time-series aggregates
- Rules
- Network analysis
- Feature/store - customer risk assessment

By industry, the used data stores include:
- Redis (In-memory database) - For quick features, and feedback to block transactions
- RDMS(PostgreSQL) - For customer information, transactions,
- NoSQL - The AML & Fraud rules
- Graph database - Network analysis, patterns that user wouldn't know or look for???
## What data storage/ layout is to be used?

- PostgreSQL - To handle the customer information, transactions, simple pattern detection rules
- Redis - For quick data

## Which concerns are to be considered with this layout?

- not scalable when graph data use-cases are required
- PostgreSQL is being used for many data cases, ie NoSQL, Graph, ..


