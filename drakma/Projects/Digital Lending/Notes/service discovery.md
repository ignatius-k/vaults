---
mode: learn
review: review
review_note: "A list of open questions (Eureka, registry, load balancing). Answer them, or delete if Docker Swarm/Eureka is no longer the plan."
---
use- how does facilitate load balancing, is this by client or service registry
- for server-side, the router - is this level-4
- is the querying of the registry done on every request, which I believe is not optimal, if not on every request, is the client constantly querying the registry
- however much, we are removing the static configuration, but still there is some static config on client side, right?? like name of service

eureka
- which kind of configurations does it have
- which database is used, or can I select a particular database
- what information is required to register service on here,
- how does it know that this is second instance of the service


how does service registry or if its client registering itself, know its ip and port?



**Container Orchestration**
- Docker swarm mode vs K8s
- allows to keep the **same** old beloved `docker-compose.yml` (to some extent) for both _running_ Docker containers locally, as well as _deploying_ stacks, where does it change???
- 