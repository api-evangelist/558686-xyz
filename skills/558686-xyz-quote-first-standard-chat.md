---
generated: '2026-09-19'
method: generated
name: Quote-first GPT-5.6 Luna Standard chat completion
description: Get one OpenAI-compatible chat completion from GPT55 for $0.00293 USDC on Base by fetching the live x402 quote, checking it against a spend cap, paying with a buyer-owned wallet, and retrying the identical request.
api: openapi/558686-xyz-gpt55-model-gateway-openapi.json
operations: [v1Models, v1ChatCompletionsStandard]
source: >-
  Grounded in https://gpt55.558686.xyz/buyer-guide ("Integration flow", "Copy-paste x402
  JavaScript quickstart"), https://gpt55.558686.xyz/x402/guides/ai-agent-x402-api, the live 402
  quote observed 2026-09-20, and operationIds verified in the OpenAPI.
---

# Quote-first GPT-5.6 Luna Standard chat completion

One paid request, one OpenAI-shaped answer. There is no account and no API key; the payment is
the credential (`authentication/558686-xyz-authentication.yml`).

## Before you start
- You need a buyer-owned wallet holding USDC on Base (`eip155:8453`). Never send its private key to the
  service; the provider's own policy says the service never asks for one.
- Set a spend cap. The published Standard price is **$0.00293 = 2930 atomic USDC**; reject any quote above it.
- Rate limit: 120 requests per 60 s per client, signalled by `ratelimit-*` headers on every response
  (`rate-limits/558686-xyz-rate-limits.yml`).

## Steps
1. **(Optional) List models** — `v1Models` (`GET /v1/models`). Anonymous, free. Confirms the host is up and
   returns seven model ids with per-model x402 endpoints and prices.
2. **Fetch the quote** — `v1ChatCompletionsStandard` (`POST /v1/chat/completions/standard`) with a JSON body
   `{"messages":[{"role":"user","content":"..."}],"max_tokens":128}` and **no** payment header. Expect **HTTP 402**
   with a `PAYMENT-REQUIRED` header and a body whose `accepts[]` carries `scheme: exact`, `network: eip155:8453`,
   `amount: "2930"`, `asset: 0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913`, `payTo: 0x1f0130669ca6fd02e025a984cc038f139df19a2f`,
   `maxTimeoutSeconds: 300`. This step executes nothing and costs nothing.
3. **Verify the quote** — check `amount <= 2930`, `network == eip155:8453`, the USDC contract and `payTo` above.
   If anything differs, stop: the provider says the live quote, not any document, is authoritative, and a
   changed payTo is exactly what a spend cap exists to catch.
4. **Pay and retry** — sign the exact payment with your wallet (`@x402/fetch` + `@x402/evm` + `viem`, or the
   provider's `first-payment-client.mjs` with `PAY_REAL_X402=1`) and resend **the same request** with the
   `X-PAYMENT` header within 300 s. The provider requires the retry to be the identical request
   (`sameRequestRetryRequired: true`).
5. **Read the result** — HTTP 200 with an OpenAI `chat.completion` object (`choices[0].message.content`,
   `usage`) and settlement headers `PAYMENT-RESPONSE`, `x-x402-receipt-id`, `x-x402-receipt-url`. Keep the
   receipt: it is the only proof of the exchange.

## Limits and errors
- Input is capped at **24,000 characters** on this route; `max_tokens` 1..128000.
- `400 {"error":{"type":"invalid_request_error"}}` = malformed JSON; `402` = quote (normal); `404` = wrong path
  or method. See `errors/558686-xyz-problem-types.yml`.
- There is **no idempotency key and no refund**: a double-fired paid call is two payments
  (`conventions/558686-xyz-conventions.yml`). Do not retry a 200.

## Notes
- The compatibility route `v1ChatCompletions` (`POST /v1/chat/completions`) behaves identically when `model`
  is omitted; other `model` values are priced per their own route (`plans/558686-xyz-plans-pricing.yml`).
- Rehearse with the sandbox path first if the wallet is new (`sandbox/558686-xyz-sandbox.yml`).
