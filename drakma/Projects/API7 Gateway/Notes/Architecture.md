Gateway Group -> Gateway Instance

**Gateway instances** in the same **Gateway Group** get the same changes/configurations

Other entities to know
- Gateway group
- Service
- Route

==Note==:
- Services are defined in gateway group
- Then routes are defined in a service
- But, also upstream nodes are added to a service

In terms of set up
- Gateway group 
- Gateway instance/node

==Note==:
- Gateway instances are configured in a gateway group
- Also, if a gateway instance is registered in a particular group, it cant be registered in another

In terms of access
- Gateway group
- Consumer

==Note==:
- ~~Consumers are defined per gateway group~~ Consumers can defined across gateway groups


I stopped on key concepts; https://docs.api7.ai/api7-gateway/key-concepts/overview

