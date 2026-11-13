Thank you for sharing the plugin list and redacted configurations for both gateway groups. We’ve completed an initial review of Gateway for the upgrade from 3.10.1 to 3.10.9.

In the meantime, could your team check the following?

- **Forwarded headers.** Do any upstream services rely on `X-Forwarded-Proto`, `X-Forwarded-Host`, `X-Forwarded-Port`, or `Forwarded` from your load balancer, particularly if it terminates TLS? Currently, no
    
- **Stanbic workflows.** In a staging environment running 3.10.9 with both of your custom plugins loaded, please run representative requests for merchant inquiry, merchant settlement, and transaction inquiry. Confirm that each workflow completes successfully. These checks will show whether the gateway can still obtain the upstream access token and sign requests as expected. Our engineering team will review the results and confirm plugin compatibility.
    
- **Automation and container tooling.** If any scripts or pipelines call `/api/custom_plugins` or `/api/plugins/{name}/usage`, they’ll need to use the corresponding gateway-group APIs and have `gateway:GetCustomPlugin` permission where applicable. Please also check any scripts or custom images that rely on tools such as `perl`, `apt`, `curl`, or `resty` inside the gateway container. Move affected tasks to the host or a separate container, and use `/usr/bin/apisix` when invoking `apisix` through `docker exec`.
    
- **Gateway memory.** We recommend adding about 400 MiB to each Data Plane container’s memory request and limit, or reviewing whether shared-memory allocations for unused features can be restored to their previous values. If you use Kubernetes, please also check available node memory and eviction thresholds. [API7 Gateway release notes](https://docs.api7.ai/api7-gateway/release-notes)
    

During the maintenance window, API7 will upgrade the Cloud Control Plane first. Once we’ve checked gateway connectivity and compatibility, your team can upgrade the Data Plane instances with our support. A compatibility report may be blank for an instance still running 3.10.1 during the rollout. Please pause configuration writes while the Control Plane is upgrading and avoid creating or editing routes or custom plugins throughout the window. As the Data Plane instances are upgraded, we’ll check HTTPS connectivity to each upstream and monitor gateway memory and error rates. [Data Plane Rolling Upgrade guide](https://docs.api7.ai/api7-gateway/upgrade-guides/rolling-upgrade)

Before we set a date, we’ll agree on when to roll back, including a version-related increase in `5xx` responses or a failure in Control Plane migration, Dashboard sign-in, or configuration delivery. If both sides have been upgraded, we’ll restore the Data Plane first and confirm its instances are reporting heartbeats before restoring the Control Plane. If DP Manager is temporarily unavailable during the Control Plane rollback, we’ll wait for it to come back before reconnecting the gateways.

Please let us know whether your upstreams rely on the forwarded headers and whether any automation uses the older custom plugin APIs. We can use your findings and the staging results to finalize the upgrade plan and agree on a maintenance window once you have internal approval.