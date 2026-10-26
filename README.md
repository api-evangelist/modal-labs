# Modal (modal-labs)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
