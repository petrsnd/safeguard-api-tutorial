# SPP 2 -- Using Swagger UI to call the Safeguard API

Given the information from the [introductory tutorial](../spp1-introduction),
you are now ready to learn to call the Safeguard API using the built-in Swagger
UI. Swagger is based on the
[OpenAPI specification](https://swagger.io/docs/specification/about/) which
provides a way to document an entire API like the Safeguard API in a single
file. SPP code that serves the Safeguard API is instrumented in such a way that
it generates an OpenAPI file during build. This OpenAPI file may be downloaded
from any of the Safeguard API services: core, appliance, notification, event,
and a2a.

|Service|Description|
|-|-|
|core|Most product functionality is found here. All cluster-wide operations: access request workflow, asset management, policy management, etc.|
|appliance|Appliance-specific operations, such as setting IP address, maintenance, backups, support bundles, appliance management|
|notification|Anonymous, unauthenticated operations. This service is available even when the appliance isn't fully online|
|event|Specialized endpoint for connecting to SignalR for real-time events|
|a2a|Application integration specific operations. Fetching passwords, making access requests on behalf of users, etc.|

Each service has its own OpenAPI file. However, the OpenAPI file for the event
service is not really useful as that endpoint just provides for SignalR
connectivity.

Swagger UI is generated along with the Swagger OpenAPI file to visualize and
interact with the Safeguard API in place without having to implement a client.

## Exercises

[Hands-on Lab](swagger-hol.md)

1. Find the Swagger OpenAPI file
2. Find Swagger UI
3. Calling the notification service -- anonymous GET
4. Authenticate to Safeguard using Swagger UI
5. Calling the core service to create a user
6. Calling the core service to set the user password
7. Using query parameters
8. Maintenance operations available on the appliance service