# Modal (modal-labs)

Modal is a serverless cloud for AI, data, and general compute. Developers define infrastructure as code in Python (with JavaScript and Go SDKs) and run functions, GPUs, sandboxes, web endpoints, cron jobs, and volumes on demand.

**Important - SDK/gRPC, not a REST API:** Modal's primary developer interface is the Modal SDK and the `modal` CLI communicating with a gRPC backend. Modal does **not** publish a conventional first-party public REST API for defining or invoking infrastructure. The one genuine HTTPS surface is **user-deployed web endpoints** (`@modal.fastapi_endpoint` / `asgi_app` / `wsgi_app` / `web_server`) served on `*.modal.run`, plus optional Sandbox network tunnels - and even those have request/response shapes defined by the developer's own code, not a Modal-owned contract. The surfaces below are catalogued as developer capabilities; SDK-only ones intentionally omit an OpenAPI reference, and the OpenAPI provided is a clearly-labeled **representative** of a typical user web endpoint. See `review.yml` for the full assessment.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/modal-labs/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/modal-labs/refs/heads/main/apis.yml)

## Tags

- Serverless
- Compute
- GPU
- AI Infrastructure
- Sandboxes
- Infrastructure as Code

## Timestamps

- **Created:** 2026-07-01
- **Modified:** 2026-07-01

## APIs

### Modal Functions and Remote Invocation

Decorate Python functions with `@app.function` to run them remotely on Modal's cloud. Invoke deployed functions synchronously (`.remote`), asynchronously (`.spawn`), in parallel (`.map`), or look them up from another app via `Function.from_name`. SDK/gRPC-only - there is no first-party REST endpoint.

- **Human URL:** [https://modal.com/docs/guide/apps](https://modal.com/docs/guide/apps)

#### Tags

- Functions
- Remote Execution
- Serverless
- SDK

#### Properties

- [Documentation](https://modal.com/docs/guide/apps)
- [API Reference](https://modal.com/docs/reference/modal.Function)

### Modal Web Endpoints

The genuine HTTPS surface. Functions decorated with `@modal.fastapi_endpoint`, `@modal.asgi_app`, `@modal.wsgi_app`, or `@modal.web_server` are auto-deployed as HTTPS endpoints on `*.modal.run`. The URL host is fixed by Modal but the request/response schema is defined by the developer's own code, so the accompanying OpenAPI is representative.

- **Human URL:** [https://modal.com/docs/guide/webhooks](https://modal.com/docs/guide/webhooks)
- **Base URL:** `https://<workspace>--<app>-<function>.modal.run`

#### Tags

- Web Endpoints
- HTTP
- FastAPI
- ASGI
- Webhooks

#### Properties

- [Documentation](https://modal.com/docs/guide/webhooks)
- [API Reference](https://modal.com/docs/reference/modal.fastapi_endpoint)
- [OpenAPI](openapi/modal-labs-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html) (representative)
- [Postman Collection](collections/modal-labs.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/modal-labs.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Modal Sandboxes

Secure containers for executing untrusted user or agent-generated code, created via `Sandbox.create()` in the Python, JavaScript, and Go SDKs. Supports `exec()`, filesystem access, Volumes, Secrets, and network tunnels that can expose a container port over HTTPS. Lifecycle control is SDK/gRPC-only.

- **Human URL:** [https://modal.com/docs/guide/sandbox](https://modal.com/docs/guide/sandbox)

#### Tags

- Sandboxes
- Code Execution
- Containers
- Agents

#### Properties

- [Documentation](https://modal.com/docs/guide/sandbox)
- [API Reference](https://modal.com/docs/reference/modal.Sandbox)
- [OpenAPI](openapi/modal-labs-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html) (representative)

### Modal Volumes

Distributed, high-performance file system volumes for sharing state across functions and containers, managed via `modal.Volume` in the SDK and the `modal volume` CLI. SDK/CLI-only with no public REST endpoint.

- **Human URL:** [https://modal.com/docs/guide/volumes](https://modal.com/docs/guide/volumes)

#### Tags

- Volumes
- Storage
- Persistence
- SDK

#### Properties

- [Documentation](https://modal.com/docs/guide/volumes)
- [API Reference](https://modal.com/docs/reference/modal.Volume)

### Modal Dicts and Queues

Distributed key-value store (`modal.Dict`) and distributed queue (`modal.Queue`) for passing state and messages between functions and containers. Accessed exclusively through the SDK; no public REST interface.

- **Human URL:** [https://modal.com/docs/guide/dicts-and-queues](https://modal.com/docs/guide/dicts-and-queues)

#### Tags

- Dicts
- Queues
- Key Value
- Messaging
- SDK

#### Properties

- [Documentation](https://modal.com/docs/guide/dicts-and-queues)
- [API Reference](https://modal.com/docs/reference/modal.Dict)

### Modal Secrets

Securely inject environment variables and credentials into functions and sandboxes via `modal.Secret`, managed in the dashboard, CLI, or SDK (`Secret.from_name` / `from_dict`). SDK/CLI-only; no public REST endpoint.

- **Human URL:** [https://modal.com/docs/guide/secrets](https://modal.com/docs/guide/secrets)

#### Tags

- Secrets
- Configuration
- Credentials
- SDK

#### Properties

- [Documentation](https://modal.com/docs/guide/secrets)
- [API Reference](https://modal.com/docs/reference/modal.Secret)

### Modal Cron and Scheduled Functions

Run functions on a recurring schedule using `modal.Period` or `modal.Cron` passed to `@app.function(schedule=...)`. Schedules are declared in code and managed through deployment; there is no REST scheduling API.

- **Human URL:** [https://modal.com/docs/guide/cron](https://modal.com/docs/guide/cron)

#### Tags

- Cron
- Scheduling
- Jobs
- SDK

#### Properties

- [Documentation](https://modal.com/docs/guide/cron)
- [API Reference](https://modal.com/docs/reference/modal.Cron)

### Modal Images and GPU

Define container images programmatically with `modal.Image` (`from_registry`, `debian_slim`, `pip_install`, `run_commands`) and attach GPUs by passing `gpu=` (T4, L4, A10, L40S, A100, H100, H200, B200) to a function. Declared in code and resolved by the gRPC backend; no public REST endpoint.

- **Human URL:** [https://modal.com/docs/guide/images](https://modal.com/docs/guide/images)

#### Tags

- Images
- GPU
- Containers
- Environments
- SDK

#### Properties

- [Documentation](https://modal.com/docs/guide/images)
- [API Reference](https://modal.com/docs/reference/modal.Image)

### Modal CLI

The `modal` command-line interface for deploying apps, running functions, tailing logs, managing volumes/secrets/dicts, and launching shells. Wraps the same gRPC control plane the SDK uses.

- **Human URL:** [https://modal.com/docs/reference/cli/modal](https://modal.com/docs/reference/cli/modal)

#### Tags

- CLI
- Tooling
- Deployment

#### Properties

- [Documentation](https://modal.com/docs/reference/cli/modal)

## Common Properties

- [GitHub Organization](https://github.com/modal-labs)
- [LinkedIn](https://www.linkedin.com/company/modal-labs)
- [Website](https://modal.com/)
- [Documentation](https://modal.com/docs)
- [Plans](plans/modal-labs-plans-pricing.yml)
- [Rate Limits](rate-limits/modal-labs-rate-limits.yml)
- [Fin Ops](finops/modal-labs-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
