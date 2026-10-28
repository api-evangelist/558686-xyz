# gpt55-token-gateway

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

gpt55-token-gateway is the self-chosen service name of an unnamed operator running two OpenAI-compatible AI API gateways on the 558686.xyz domain. GPT55 Model Gateway (gpt55.558686.xyz) sells single GPT-5.6 Luna, GPT-5.5 and GPT-5.3-codex chat completions, deterministic text and wallet tools, and prepaid call packs per request over the x402 payment protocol (HTTP 402 quote, exact USDC on Base eip155:8453, payTo 0x1f01...9a2f) with no account and no API key, and publishes an OpenAPI 3.1 contract (37 operations), a remote MCP server at /mcp that answers initialize and tools/list anonymously with 218 tools, an A2A 1.0 agent card, an MCP registry server.json, an ai-plugin.json, an x402 discovery document, pricing and live-price JSON, a Postman collection, llms.txt and a Content-Signal robots.txt. A second, free, unauthenticated REST surface of 44 developer utilities is served under /api-market for API.market import. Sub2API (sub2api.558686.xyz, also api.558686.xyz) is a self-hosted deployment of the open-source Wei-Shaw/sub2api relay that resells GPT, Claude and Gemini models by Bearer API key at a 1 USD paid = 10 USD platform-quota ratio, with a 3-operation OpenAPI, an APIs.json index, Chinese-language docs and public registration currently closed. Four retired split hosts (x402-utils, x402-wallet, x402-seller, x402-key.558686.xyz) answer HTTP 410 with retirement notices pointing back to GPT55. Source repository github.com/wangletiand/gpt55-x402-gateway (MIT); the security contact ops@400860.xyz and the Sub2API recharge shop shop.400860.xyz tie the operator to the sibling 400860.xyz record.

**Areas:** x402 · Agentic Payments · MCP · A2A · AI Gateway · OpenAI-Compatible · LLM · AI Agents · USDC · Base · API Relay · Developer Tools

## gpt55-token-gateway on APIs.io

Everything profiled for gpt55-token-gateway is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/558686-xyz/](https://apis.io/providers/558686-xyz/)** — or go straight to one of the APIs or properties below.

### APIs (13)

- [GPT55 x402 Gateway MCP Server](https://apis.io/apis/558686-xyz/gpt55-mcp-server/) — Remote Model Context Protocol server at https://gpt55.558686.xyz/mcp (Streamable HTTP; a GET returns the server.json-shaped manifest and /mcp/sse streams…
- [GPT55 Model Gateway A2A Agent](https://apis.io/apis/558686-xyz/gpt55-a2a-agent/) — Agent2Agent surface: an agent card served at https://gpt55.558686.xyz/.well-known/agent-card.json (and identically at the legacy /.well-known/agent.json) -…
- [gpt55-token-gateway Base Usdc API](https://apis.io/apis/558686-xyz/558686-xyz-base-usdc-api/) — The base-usdc API from gpt55-token-gateway — 1 operation(s) for base-usdc.
- [gpt55-token-gateway Gpt55 Model Gateway API](https://apis.io/apis/558686-xyz/558686-xyz-gpt55-model-gateway-api/) — The gpt55-model-gateway API from gpt55-token-gateway — 27 operation(s) for gpt55-model-gateway.
- [gpt55-token-gateway Gpt55 Retained High Intent API](https://apis.io/apis/558686-xyz/558686-xyz-gpt55-retained-high-intent-api/) — The gpt55-retained-high-intent API from gpt55-token-gateway — 1 operation(s) for gpt55-retained-high-intent.
- [gpt55-token-gateway Gpt55 Retained Nonmodel API](https://apis.io/apis/558686-xyz/558686-xyz-gpt55-retained-nonmodel-api/) — The gpt55-retained-nonmodel API from gpt55-token-gateway — 6 operation(s) for gpt55-retained-nonmodel.
- [gpt55-token-gateway Models API](https://apis.io/apis/558686-xyz/558686-xyz-models-api/) — The Models API from gpt55-token-gateway — 1 operation(s) for models.
- [gpt55-token-gateway Responses API](https://apis.io/apis/558686-xyz/558686-xyz-responses-api/) — The Responses API from gpt55-token-gateway — 1 operation(s) for responses.
- [gpt55-token-gateway Utility Tools API](https://apis.io/apis/558686-xyz/558686-xyz-utility-tools-api/) — Deterministic text, JSON, encoding, hashing, URL parsing, and developer utilities.
- [gpt55-token-gateway Wallet Security API](https://apis.io/apis/558686-xyz/558686-xyz-wallet-security-api/) — The wallet-security API from gpt55-token-gateway — 1 operation(s) for wallet-security.
- [gpt55-token-gateway Wallet Signing Safety Pack API](https://apis.io/apis/558686-xyz/558686-xyz-wallet-signing-safety-pack-api/) — The wallet-signing-safety-pack API from gpt55-token-gateway — 1 operation(s) for wallet-signing-safety-pack.
- [gpt55-token-gateway X402 API](https://apis.io/apis/558686-xyz/558686-xyz-x402-api/) — The x402 API from gpt55-token-gateway — 1 operation(s) for x402.
- [gpt55-token-gateway Chat Completions API](https://apis.io/apis/558686-xyz/558686-xyz-chat-completions-api/) — The Chat Completions API from gpt55-token-gateway — 1 operation(s) for chat completions.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [gpt55-x402-gateway](https://apis.io/servers/558686-xyz/gpt55-x402-gateway/)

#### Examples (2)

Example requests and responses.

- [558686 Xyz Standard Chat Example](https://apis.io/examples/558686-xyz/558686-xyz-standard-chat-example/)
- [558686 Xyz Translate Canary Example](https://apis.io/examples/558686-xyz/558686-xyz-translate-canary-example/)

#### Overlays (3)

OpenAPI overlays, including conversational phrasing for each operation.

- [558686 Xyz Api Market Utility Tools Overlay](https://apis.io/overlays/558686-xyz/558686-xyz-api-market-utility-tools-overlay/)
- [558686 Xyz Gpt55 Model Gateway Overlay](https://apis.io/overlays/558686-xyz/558686-xyz-gpt55-model-gateway-overlay/)
- [558686 Xyz Sub2Api Overlay](https://apis.io/overlays/558686-xyz/558686-xyz-sub2api-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [558686 Xyz Authentication](https://apis.io/security/558686-xyz/558686-xyz-authentication/)
- [558686 Xyz Domain Security](https://apis.io/security/558686-xyz/558686-xyz-domain-security/)
- [558686 Xyz Vulnerability Disclosure](https://apis.io/security/558686-xyz/558686-xyz-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [558686 Xyz Plans Pricing](https://apis.io/plans/558686-xyz/558686-xyz-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [558686 Xyz Rate Limits](https://apis.io/rate-limits/558686-xyz/558686-xyz-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://558686.xyz/)
- [Documentation](https://gpt55.558686.xyz/x402/guides/ai-agent-x402-api)
- [Getting started](https://gpt55.558686.xyz/x402/guides/ai-agent-x402-api)
- [API reference](https://gpt55.558686.xyz/buyer-guide)
- [Pricing](https://gpt55.558686.xyz/pricing.json)
- [Blog](https://sub2api.558686.xyz/blog/)
- [Security](https://github.com/wangletiand/gpt55-x402-gateway/blob/main/SECURITY.md)
- [Privacy policy](https://gpt55.558686.xyz/privacy)
- [Status](https://gpt55.558686.xyz/x402/status)

## API Evangelist rating

**Kin Score 57.6** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 80.0 |
| Contract quality | 48.2 |
| Contract governance | 18.2 |
| Operational transparency | 60.5 |
| Developer ergonomics | 73.2 |
| Access clarity | 65.8 |

**Agent readiness 39.1** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | yes |
| Consent Identity | yes |
| Agent Card | conformant |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | mostly |

**Regulatory alignment 22.5** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/558686-xyz/](https://apis.io/providers/558686-xyz/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for gpt55-token-gateway: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/558686-xyz/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
