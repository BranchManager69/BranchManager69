# Nicholas “Nick” Sander

I go by Branch here. I founded Dexter so people can own and grow businesses run by agents. When a business wins an order it can’t afford to fill, a lender can pay its supplier before the customer pays. The business should keep the customer, the earnings and the choice of lender on the next order.

I’m building **Dexter Account** so owners can change agents and financial providers while keeping the business’s assets, obligations and history. The owner chooses future services and where available capital goes. An accepted commitment binds everyone with authority over its backing, including the owner. Dexter can earn a fee for arranging and settling the purchase while someone else earns the interest. [Dexter Account and the private beta](https://docs.dexter.cash/docs/)

I built a bridge so Solana could verify World ID enrollments against the registry on World Chain. Ten days after someone enrolled in July, Solana checked their proof against the earlier registry root and upgraded the same credit record. [World Chain bridge and mainnet proofs](https://github.com/Dexter-DAO/world-chain-bridge/blob/main/README.md)

In our local financing demo, a lender sells its right to repayment before the supplier collects. The supplier still gets paid under the original terms. The account blocks a second sale of the same claim and rejects repayment to the former lender. [Financing work with Dexter Account](https://github.com/Dexter-DAO/demos/blob/main/account-financing/README.md)

I proposed Open Tabs for purchases where approval, delivery and collection happen at different times. In a bookstore demonstration I used Dexter’s own operator key to try to redirect a reserved payment. The program refused, and the approved seller collected from the same reservation. [Individual Internet-Draft](https://datatracker.ietf.org/doc/draft-sander-open-tabs-passkey/) · [Bookstore record](https://dexter.cash/mandate?case=b0ee0521-898e-828b-9c14-265bfb59216c)

## Buying and selling through Dexter

With Dexter Connect, a buyer signs in with a passkey. Their assistant can use OpenDexter to find a service in Indexter and price the request. I tied each purchase to the buyer’s session and approved maximum. I also built the Dexter MCP tool that lets a seller publish bundled services from their account. [Dexter Connect](https://github.com/Dexter-DAO/dexter-connect) · [OpenDexter purchase code](https://github.com/Dexter-DAO/dexter-mcp/commit/0ced4d63f8aa1bc8b74f9efba68889b4728b885f) · [Seller publishing code](https://github.com/Dexter-DAO/dexter-mcp/commit/398e4661478c74d23c9e3ba42b546cbb0f245bf7)

I published Dexter’s first Solana payment server in September 2025. In zkMedusa’s published passport service, our facilitator verifies and settles the payment before the service issues a privacy credential. Through November 2, 2026, x402scan attributed **28 million transactions and $4.8 million in gross payment volume** to Dexter’s facilitator. The totals can include our own test traffic. [Original server](https://github.com/BranchManager69/dexter-x402/commit/90902d197794483f1c57b2987846b2d975fc823a) · [zkMedusa’s integration](https://github.com/zkMedusa/zkMedusa/blob/2e731f9ab69bd3e7703565dc8f4998dbbc1ae26f/app/api/passport/issue/route.ts#L114-L167) · [x402scan figures](https://www.x402scan.com/api/trpc/public.stats.overall?input=%7B%22json%22%3A%7B%22facilitatorIds%22%3A%5B%22dexter%22%5D%2C%22timeframe%22%3A0%7D%7D)

When Stripe and Tempo introduced the Machine Payments Protocol, we shipped managed Solana settlement for it the next day. [Stripe’s March 18 announcement](https://stripe.com/blog/machine-payments-protocol) · [Dexter’s March 19 release](https://dexter.cash/press/dexter-mpp-managed-settlement)

## Changes I contributed to x402

While running the facilitator I found that x402 rejected valid Solana payments when a smart wallet wrapped the transfer in its own instruction. I wrote a verifier that simulates the payment and checks the transfer inside it. An x402 maintainer merged it and enabled it on x402.org. Another developer brought it to Solana Foundation’s Pay Kit. [My change and its review](https://github.com/x402-foundation/x402/pull/1527) · [x402.org rollout](https://github.com/x402-foundation/x402/pull/2504) · [Pay Kit integration](https://github.com/solana-foundation/pay-kit/pull/255)

On Base, I found a batch settlement that exhausted its gas. A later estimate for the same call more than doubled. A node reading older chain state could explain the discrepancy. This particular operation has a bounded cost, so I gave it an explicit gas limit and added a regression test. The maintainer agreed and merged the fix. [Failure and diagnosis](https://github.com/x402-foundation/x402/issues/2374) · [Review and repair](https://github.com/x402-foundation/x402/pull/2375#issuecomment-4496413084)

During a Dexter SDK test, our client reported failure when a slow seller had already been paid. The retry sent a second payment. After a timeout the client now checks settlement before reporting what happened. [Incident and regression tests](https://github.com/Dexter-DAO/dexter-x402-sdk/blob/main/FINDINGS-pay-timeout-double-charge-2026-05-21.md)

## About me

Pump Fund named Dexter its seventh investment in March 2026. It invested $250,000 through a SAFE with a $10 million post-money valuation cap. In May I spoke at Solana Accelerate AI in Miami about how agents find services. I live in South Florida. [Pump Fund’s announcement](https://x.com/pumpspotlight/status/2035092234526203925) · [Investment terms](https://dexter.cash/press/dexter-pump-fund-investment) · [Watch the Miami talk](https://www.youtube.com/watch?v=AYUw9m3gfqs&t=269s)

[branch.bet](https://branch.bet/) · [Get in touch](mailto:branch@branch.bet)
