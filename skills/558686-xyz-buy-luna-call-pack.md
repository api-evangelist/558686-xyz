---
generated: '2026-09-19'
method: generated
name: Buy a 100-call prepaid Luna pack and spend it
description: Reduce per-call x402 payment steps for repeated GPT-5.6 Luna work by quoting and buying the 100-call prepaid pack ($1.60, 80% of per-call) from GET /v1/paid/call-packs/gpt-5.6-luna-100, then calling POST /v1/chat/completions/gpt-5.6-luna against the pack.
api: openapi/558686-xyz-gpt55-model-gateway-openapi.json
operations: [v1PaidCallPacksGpt56Luna100, v1ChatCompletionsGpt56Luna]
source: >-
  Grounded in https://gpt55.558686.xyz/x402/first-external-revenue-offer.json (the pack's paid
  URL, price, callCount, discount and expectedPaidResult schema), https://gpt55.558686.xyz/buyer-guide
  ("Prepaid Call Credits"), the x-gpt55-product block on the operation in the OpenAPI, and the
  operationIds verified in the OpenAPI.
---

# Buy a 100-call prepaid Luna pack and spend it

For repeated GPT-5.6 Luna calls the provider's repeat-use path is a prepaid pack: one x402 payment
buys 100 call credits so each subsequent call skips the on-chain payment handshake. The pack is the
provider's stated "next purchase" after a first Standard result.

## Steps
1. **Quote the pack** — `v1PaidCallPacksGpt56Luna100` (`GET /v1/paid/call-packs/gpt-5.6-luna-100`), optionally with
   `?quote_only=true` (the spec's own dry-run hint; an unpaid request returns the 402 regardless). Expect **402**
   with `amount "1600000"` (=$1.60 USDC), `network eip155:8453`, `payTo 0x1f01…9a2f`. Published discount: 0.8 of the
   per-call total (100 x $0.019999).
2. **Verify** amount, network, asset and payTo against your policy; the provider says to "fetch the live 402 quote
   immediately before paying".
3. **Pay** — retry the identical GET with `X-PAYMENT` within 300 s. Expected 200 body (provider schema):
   `{ok: true, productId: "model-call-pack", pack: {id: "gpt-5.6-luna-100-call-pack", token: "pk_live_…", model: "gpt-5.6-luna", callCount: 100, remainingCalls: 100, price: "$1.60"}}`.
   **Store the pack token as a secret** — it is the bearer of 100 prepaid calls.
4. **Spend it** — `v1ChatCompletionsGpt56Luna` (`POST /v1/chat/completions/gpt-5.6-luna`) with the OpenAI body
   `{"model":"gpt-5.6-luna","messages":[...],"max_tokens":256}`. How the pack token is presented on the call is
   **not described in the OpenAPI or the buyer guide**; the paid pack response and `x402NextPurchase` fields are
   the provider's stated place to find it, so read them rather than assuming a header name.
5. **Track** `remainingCalls` from the pack response; there is no documented balance endpoint in the contract.

## Rules and caveats
- **No refund or cancellation window is published for packs** (`conventions/558686-xyz-conventions.yml`,
  reversibility: none). Treat $1.60 as spent the moment the 200 arrives.
- Other sizes (500 / 2000 / 10000 calls; and packs for gpt-5.5, gpt-5.3-codex, Terra, Soul) are priced in
  `plans/558686-xyz-plans-pricing.yml`; only the five 100-call routes are in the OpenAPI.
- Do NOT use the "Key Pack" links in the agent card or README: they point at `x402-key.558686.xyz`, which
  answers 410 Gone (`lifecycle/558686-xyz-lifecycle.yml`).
- Errors and rate limits as in `errors/558686-xyz-problem-types.yml` and `rate-limits/558686-xyz-rate-limits.yml`.
