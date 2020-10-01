---
title: "Building Blocks"
linkTitle: "Building Blocks"
weight: 30
description: "HTTP or gRPC APIs that can be called from user code and uses one or more Dapr components."
---

A [building block](./architecture/building_blocks.md) is as an HTTP or gRPC API that can be called from user code and uses one or more Dapr components. Dapr consists of a set of building blocks, with extensibility to add new building blocks.

The diagram below shows how building blocks expose a public API that is called from your code, using components to implement the building blocks' capability.

<img src="../images/concepts-building-blocks.png" width=250>
  
The following are the building blocks provided by Dapr:

<img src="../images/building_blocks.png" width=800>

| Building Block | Endpoint | Description |
|----------------|----------|-------------|
| [**Service-to-Service Invocation**](./service-invocation/README.md) | `/v1.0/invoke` | Service invocation enables applications to communicate with each other through well-known endpoints in the form of http or gRPC messages. Dapr provides an endpoint that acts as a combination of a reverse proxy with built-in service discovery, while leveraging built-in distributed tracing and error handling.
| [**State Management**](./state-management/README.md) | `/v1.0/state` | Application state is anything an application wants to preserve beyond a single session. Dapr provides a key/value-based state API with pluggable state stores for persistence.
| [**Publish and Subscribe**](./publish-subscribe-messaging/README.md) | `/v1.0/publish` `/v1.0/subscribe`|  Pub/Sub is a loosely coupled messaging pattern where senders (or publishers) publishes messages to a topic, to which subscribers subscribe. Dapr supports the pub/sub pattern between applications.
| [**Resource Bindings**](./bindings/README.md)| `/v1.0/bindings` | A binding provides a bi-directional connection to an external cloud/on-premise service or system. Dapr allows you to invoke the external service through the  Dapr binding API, and it allows your application to be triggered by events sent by the connected service.
| [**Actors**](./actors/README.md) | `/v1.0/actors` |  An actor is an isolated, independent unit of compute and state with single-threaded execution. Dapr provides an actor implementation based on the Virtual Actor pattern which provides a single-threaded programming model and where actors are garbage collected when not in use. See * [Actor Overview](./actors#understanding-actors)
| [**Observability**](./observability/README.md) | `N/A` |  Dapr system components and runtime emit metrics, logs, and traces to debug, operate and monitor Dapr system services, components and user applications.
| [**Secrets**](./secrets/README.md) | `/v1.0/secrets` | Dapr offers a secrets building block API and integrates with secret stores such as Azure Key Vault and Kubernetes to store the secrets. Service code can call the secrets API to retrieve secrets out of the Dapr supported secret stores.