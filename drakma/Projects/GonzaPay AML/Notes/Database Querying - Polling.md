- [[#What other mechanisms exist?]]
- [[#What concerns exist and how to handle them?]]
- [[#Things to note]]

## What other mechanisms exist?

- Polling (Pull) - **POSSIBLE**

- Event-driven (External system notifies us) - **IMPOSSIBLE**, the current ingestion of data in the replica does not favor it. The tables are first truncated resulting into wrong notifications

- Change Data Capture - **POSSIBLE**, however it creates unnecessary overhead, with little benefits

For the initial version, **POLLING** is to be used, why ??
- simple, and quick development
- lowered latency requirements

## What concerns exist  and how to handle them?

| #   | Concern                                                                                                                           | Solution                                                                                                                                                                                                |
| --- | --------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | how are we reading the DB for the first time<br>(The underlying issue is what do we do when there is too much data to be fetched) | - The polling strategy should be smart, first query the number of records available on external for processing, then plan on how to poll ie the max records to be fetched, and period between the polls |
| 2   | how to maintain resiliency in polling?<br>- reboots<br>- connection issues                                                        | - Idem-potency using the transaction reference ids<br>- then, using starting point as the checkpoint date, N minus delta, d                                                                             |
| 3   | how do we know or track the new data<br>(Checkpoint strategy)                                                                     | Use the date when the transaction was processed                                                                                                                                                         |

## Things to note
- Adaptive polling
- Optimized polling interval
- Persist the checkpoint information
- Using connection pool
- Index the columns
- Conditional polling, Using lightweight metadata checks first before querying