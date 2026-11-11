Currently, there are multiple transaction tables from which we are to listen to
My idea is, a view is created to join all this data

- [[#What approaches exist?]]
- [[#What are the issues with going with this approach?]]
- [[Defining the view & underlying table]]

## What approaches exist?

- Regular views - Simple to implement, however, there is issues with database performance especially in environments with large data, also latency as the query is executed on the fly every time the view is queried

- Materialized views - **CHOSEN**, relatively simple, database performance is not much affected, reduced latency as query is already executed. Though, requires Refresh

- Multi-table polling (application level) - Complexity in code, Introduces some issues in code scalability, centralized place for applying business logic

- DB triggers writing to unified polling table - Benefit here is, a table is used reducing performance issues introduced by views, or need for refresh. Requires query updates, in case of changes as in views

## What are the issues with going with this approach?

| #   | Issues                        | Solution                                                   |
| --- | ----------------------------- | ---------------------------------------------------------- |
| 1   | View refresh                  | Manual refresh, but automatically triggered using CRON job |
| 2   | Performance impact on refresh | Smart database querying                                    |
