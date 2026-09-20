---
generated: '2026-09-19'
method: generated
name: Prove a wallet with the translate first-payment canary
description: Validate that a buyer-owned x402 wallet or client can quote, pay and receive a result on GPT55 using the provider's recommended lowest-cost model-backed canary, POST /v1/tools/translate at $0.00293, before spending on chat or packs.
api: openapi/558686-xyz-gpt55-model-gateway-openapi.json
operations: [v1ToolsTranslate]
source: >-
  Grounded in https://gpt55.558686.xyz/x402/translate-first-purchase(.json), the
  recommendedFirstPaymentCanary block of https://gpt55.558686.xyz/.well-known/x402, the
  repository README ("Lowest-Friction First Payment"), and the operationId verified in the OpenAPI.
---

# Prove a wallet with the translate first-payment canary

The provider's own advice: "Verify a buyer-owned x402 wallet/client with one short translation before
paying for a model call or quota pack." The canary is the cheapest **model-backed** paid route; an even
cheaper non-model settlement proof, `GET /v1/x402-ping` ($0.002), exists on the host but is not in the
OpenAPI, so it is noted here and not used as a step.

## Steps
1. **Quote** — `v1ToolsTranslate` (`POST /v1/tools/translate`) with
   `{"text":"Hello, world.","target_language":"Chinese"}` and no payment header. Expect **402** with
   `accepts[0].amount == "2930"` (=$0.00293), `network eip155:8453`, USDC asset, `payTo 0x1f01…9a2f`.
   Provider command for the same thing: `ROUTE_ID=translate-canary MAX_USDC=0.00293 node first-payment-client.mjs`.
2. **Check** the quote against your cap (`MAX_USDC=0.00293`) and the expected payTo/network. Stop on any mismatch.
3. **Pay** — resend the identical request with `X-PAYMENT` within 300 s
   (`PAY_REAL_X402=1 ROUTE_ID=translate-canary MAX_USDC=0.00293 EVM_PRIVATE_KEY=$EVM_PRIVATE_KEY node first-payment-client.mjs`,
   with the key staying in your own process).
4. **Confirm delivery** — a 200 whose body carries `text`, `model`, `usage` and `x402NextPurchase`, plus the headers
   `x-x402-receipt-id` and `x-x402-receipt-url`. The provider lists exactly these as `paidResultRequiredFields`;
   treat a 200 without a receipt header as not delivered.
5. **Graduate** — only after a clean canary move to Standard chat
   (`558686-xyz-quote-first-standard-chat.md`) or a prepaid pack (`558686-xyz-buy-luna-call-pack.md`).

## Rules
- Quote-only is the default and costs nothing; real payment is an explicit operator decision.
- No refund path exists for a paid canary; the amount is the risk budget by design
  (`conventions/558686-xyz-conventions.yml`, reversibility: none).
- Watch `ratelimit-remaining`; the window is 120 requests / 60 s (`rate-limits/558686-xyz-rate-limits.yml`).
- If you are paying from a Solana wallet: the live quotes observed advertise Base only, whatever the prose says.
