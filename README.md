# Modal

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

Modal is a serverless cloud for AI, data, and general compute. Developers define infrastructure as code in Python (with JavaScript and Go SDKs) and run functions, GPUs, sandboxes, web endpoints, cron jobs, and volumes on demand. The primary developer interface is the Modal SDK and CLI communicating with a gRPC backend, not a conventional first-party REST API. User-deployed Modal Functions can be exposed as HTTPS web endpoints (@modal.fastapi_endpoint / asgi_app / wsgi_app / web_server) on *.modal.run, and Sandboxes can expose ports via network tunnels.

**Areas:** Serverless · Compute · GPU · AI Infrastructure · Sandbox · Infrastructure as Code

## Modal on APIs.io

Everything profiled for Modal is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/modal-labs/](https://apis.io/providers/modal-labs/)** — or go straight to one of the APIs or properties below.

### APIs (22)

- [Modal Functions and Remote Invocation](https://apis.io/apis/modal-labs/modal-labs-functions-api/) — Decorate Python functions with @app.function to run them remotely on Modal's cloud. Invoke deployed functions synchronously (.remote), asynchronously…
- [Modal Volumes](https://apis.io/apis/modal-labs/modal-labs-volumes-api/) — Distributed, high-performance file system volumes for sharing state across functions and containers, managed via modal.Volume in the SDK and the `modal…
- [Modal Dicts and Queues](https://apis.io/apis/modal-labs/modal-labs-dicts-queues-api/) — Distributed key-value store (modal.Dict) and distributed queue (modal.Queue) for passing state and messages between functions and containers. Accessed…
- [Modal Secrets](https://apis.io/apis/modal-labs/modal-labs-secrets-api/) — Securely inject environment variables and credentials into functions and sandboxes via modal.Secret, managed in the dashboard, CLI, or SDK (Secret.from_name…
- [Modal Cron and Scheduled Functions](https://apis.io/apis/modal-labs/modal-labs-scheduled-api/) — Run functions on a recurring schedule using modal.Period or modal.Cron passed to @app.function(schedule=...). Schedules are declared in code and managed…
- [Modal Images and GPU](https://apis.io/apis/modal-labs/modal-labs-images-gpu-api/) — Define container images programmatically with modal.Image (from_registry, debian_slim, pip_install, run_commands) and attach GPUs by passing gpu= (T4, L4,…
- [Modal CLI](https://apis.io/apis/modal-labs/modal-labs-cli/) — The `modal` command-line interface for deploying apps, running functions, tailing logs, managing volumes/secrets/dicts, and launching shells. Wraps the same…
- [Modal Web Endpoints (Representative) API](https://apis.io/apis/modal-labs/modal-labs-modal-web-endpoints-representative-api/) — The Modal Web Endpoints (Representative) API from Modal — 2 operation(s) for modal web endpoints (representative).
- [Modal Functions API](https://apis.io/apis/modal-labs/modal-functions-api/) — Defines, deploys, and invokes serverless Python Functions on Modal with per-function GPU/CPU/memory configuration, autoscaling, and sub-second cold starts.
- [Modal Apps API](https://apis.io/apis/modal-labs/modal-apps-api/) — Logical grouping of functions, classes, and resources deployed and versioned together as an App.
- [Modal Sandboxes API](https://apis.io/apis/modal-labs/modal-sandboxes-api/) — Spins up isolated, GPU-capable sandbox containers for running untrusted code (LLM agents, tool use, code-interpreter workflows) with file-system and network…
- [Modal Images API](https://apis.io/apis/modal-labs/modal-images-api/) — Builds, caches, and rehydrates container images with pip / conda / apt / uv layers and supports custom Dockerfiles for function and sandbox runtimes.
- [Modal Volumes API](https://apis.io/apis/modal-labs/modal-volumes-api/) — Distributed read/write Volumes for persistent storage of model weights, datasets, and caches across function invocations.
- [Modal Network File Systems API](https://apis.io/apis/modal-labs/modal-network-file-systems-api/) — Network File Systems for shared, mountable file storage across multiple functions and sandboxes.
- [Modal Secrets API](https://apis.io/apis/modal-labs/modal-secrets-api/) — Stores environment-variable secrets and API keys, mountable into functions and sandboxes at runtime.
- [Modal Web Endpoints API](https://apis.io/apis/modal-labs/modal-web-endpoints-api/) — Publishes HTTP, WebSocket, and ASGI/WSGI web endpoints (FastAPI, Flask, Streamlit) backed by serverless Modal containers with custom domains and TLS.
- [Modal Cron API](https://apis.io/apis/modal-labs/modal-cron-api/) — Schedules functions to run on cron expressions with retries, time-zone awareness, and job history.
- [Modal Queues API](https://apis.io/apis/modal-labs/modal-queues-api/) — Distributed FIFO queues for asynchronous workloads, work-stealing, and producer/consumer patterns across functions.
- [Modal Dicts API](https://apis.io/apis/modal-labs/modal-dicts-api/) — Distributed dictionaries (key-value stores) for sharing state between functions and across container restarts.
- [Modal Tunnels API](https://apis.io/apis/modal-labs/modal-tunnels-api/) — Forwards local ports into Modal containers (and vice versa) for development, debugging, and hybrid networking.
- [Modal Environments API](https://apis.io/apis/modal-labs/modal-environments-api/) — Multi-environment isolation (dev / staging / prod) within a workspace, each with its own apps, secrets, and quotas.
- [Modal Token / Workspace API](https://apis.io/apis/modal-labs/modal-token-api/) — Manages workspaces, tokens, members, and authentication for the Modal control plane.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Modal Labs Agentic Access](https://apis.io/agentic-access/modal-labs/modal-labs-agentic-access/)

#### Collections (2)

Postman and Open Collection request collections.

- [Modal Web Endpoints (Representative)](https://apis.io/collections/modal-labs/open-modal-labs/)
- [Modal Web Endpoints (Representative) Modal Web Endpoints (Representative) Modal Web Endpoints (Representative) Modal Web Endpoints (Representative) API](https://apis.io/collections/modal-labs/open-modal-labs-modal-web-endpoints-representative-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Modal Labs Modal Web Endpoints Representative Api Overlay](https://apis.io/overlays/modal-labs/modal-labs-modal-web-endpoints-representative-api-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Modal Labs Authentication](https://apis.io/security/modal-labs/modal-labs-authentication/)
- [Modal Labs Domain Security](https://apis.io/security/modal-labs/modal-labs-domain-security/)
- [Modal Labs Trust Center](https://apis.io/security/modal-labs/modal-labs-trust-center/)
- [Modal Labs Vulnerability Disclosure](https://apis.io/security/modal-labs/modal-labs-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Modal Labs Plans Pricing](https://apis.io/plans/modal-labs/modal-labs-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Modal Labs Rate Limits](https://apis.io/rate-limits/modal-labs/modal-labs-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Modal Labs Finops](https://apis.io/finops/modal-labs/modal-labs-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://modal.com/)
- [Documentation](https://modal.com/docs)
- [Getting started](https://modal.com/docs/examples/hello_world)
- [API reference](https://modal.com/docs/sdk/py/latest)
- [Pricing](https://modal.com/pricing)
- [Sign up](https://modal.com/signup)
- [Support](https://modal.com/slack)
- [Changelog](https://modal.com/docs/sdk/py/releases)
- [Blog](https://modal.com/blog/atom.xml)
- [Trust centre](https://trust.modal.com/)
- [Terms of service](https://modal.com/legal/terms)
- [Privacy policy](https://modal.com/legal/privacy-policy)
- [GitHub](https://github.com/modal-labs)
- [Status](https://status.modal.com/)

## API Evangelist rating

**Kin Score 56.2** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 64.3 |
| Contract quality | 43.5 |
| Contract governance | 18.2 |
| Operational transparency | 52.6 |
| Developer ergonomics | 81.0 |
| Access clarity | 60.5 |

**Agent readiness 33.0** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | served (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | — |
| Agent Skills | yes |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 30.4** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/modal-labs/](https://apis.io/providers/modal-labs/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Modal: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/modal-labs/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
