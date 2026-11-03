# Nicholas “Nick” Sander

I go by Branch. I founded Dexter so people can own and grow businesses run by agents. I built and run the payment stack. Every production decision at Dexter has been mine.

When I designed account switching in Dexter Connect, I required a fresh passkey sign-in before an app could open the new account. Dexter checks that the wallet and account session match before the app can show the owner’s data. Giving an agent permission to spend takes a separate approval from the owner. [My Dexter Connect release](https://github.com/Dexter-DAO/dexter-connect/pull/4)

An agent uses OpenDexter to find a service on Indexter, check the seller’s price and buy within the limit its owner approves. On the seller’s side, zkMedusa’s passport code uses our SDK to verify and settle USDC before issuing a credential. Dexter is its default facilitator. [OpenDexter purchase flow](https://docs.dexter.cash/docs/operator/services/) · [zkMedusa’s payment setup](https://github.com/zkMedusa/zkMedusa/blob/2e731f9ab69bd3e7703565dc8f4998dbbc1ae26f/src/lib/passport/x402.server.ts#L28-L49) · [Passport issuance](https://github.com/zkMedusa/zkMedusa/blob/2e731f9ab69bd3e7703565dc8f4998dbbc1ae26f/app/api/passport/issue/route.ts#L139-L157)

Through November 2, 2026, x402scan ranked Dexter **third by all-time transaction count**, behind Coinbase and PayAI. It attributed **28,012,371 transactions and $4.80 million in gross payment volume** to our facilitator. The totals can include our own test traffic. [x402scan ranking and volumes](https://www.x402scan.com/api/trpc/public.facilitators.list?input=%7B%22json%22%3A%7B%22timeframe%22%3A0%2C%22pagination%22%3A%7B%22page%22%3A0%2C%22page_size%22%3A10%7D%7D%7D)

## Solana smart wallets in x402

A smart wallet on Solana can pay a seller by calling the token program from inside the wallet’s own instructions. I wrote the x402 verifier that simulates the transaction and checks the token, amount and recipient of the transfer inside it. That lets different wallet programs pay through x402 without a custom parser for each one. The x402 maintainers enabled it on x402.org, and Solana Foundation’s Pay Kit exposes it to developers. [My merged contribution](https://github.com/x402-foundation/x402/pull/1527) · [x402.org rollout](https://github.com/x402-foundation/x402/pull/2504) · [Pay Kit integration](https://github.com/solana-foundation/pay-kit/pull/255)

## World Chain bridge

I extended an Ethereum light client so Solana could verify the World ID registry on World Chain. The proof program checked the outcome of a rollup dispute on Ethereum, reconstructed the winning claim from the World Chain block, and verified the registry value against that block’s state. Anyone could relay the proof. Solana checked that it continued from the checkpoint already on file. [World Chain proof code](https://github.com/Dexter-DAO/world-chain-bridge/blob/main/source/world-chain-anchor.rs)

In July, Solana used the proven registry history to verify an enrollment that Dexter’s operator had vouched for. The program upgraded the same credit record in place, preserving its address, creation time and event counter. The public archive includes two mainnet proofs you can verify offline. [Bridge, source and mainnet records](https://github.com/Dexter-DAO/world-chain-bridge/blob/main/README.md)

## Dexter Account

When a business wins an order it can’t afford to fill, a lender can pay its supplier before the customer pays. I’m building Dexter Account so the owner can change lenders or replace the agent running the business and keep its customers, assets and history. The owner chooses future services and where available capital goes. Once the business accepts a commitment, everyone with authority over its backing must honor it, including the owner. Dexter can earn a fee for arranging and settling the purchase while the lender earns the interest. [Dexter Account and the private beta](https://docs.dexter.cash/docs/)

In our local financing demo, a lender sells its right to repayment before the supplier collects. The supplier still gets paid under the original terms. The account blocks a second sale of the same claim and rejects repayment to the former lender. [Financing work with Dexter Account](https://github.com/Dexter-DAO/demos/blob/main/account-financing/README.md)

I proposed Open Tabs for purchases where approval, delivery and collection happen at different times. In a bookstore demonstration I used Dexter’s own operator key to try to redirect a reserved payment. The program refused, and the approved seller collected from the same reservation. [Individual Internet-Draft](https://datatracker.ietf.org/doc/draft-sander-open-tabs-passkey/) · [Bookstore record](https://dexter.cash/mandate?case=b0ee0521-898e-828b-9c14-265bfb59216c)

## Payment settlement

I set an explicit gas limit for x402 batch settlement on Base, where the contract makes at most one token transfer. When Stripe and Tempo introduced the Machine Payments Protocol, we shipped managed Solana settlement for it the next day. Sellers can accept USDC without running their own Solana infrastructure. [Merged Base contribution](https://github.com/x402-foundation/x402/pull/2375) · [Stripe’s announcement](https://stripe.com/blog/machine-payments-protocol) · [Dexter’s MPP release](https://dexter.cash/press/dexter-mpp-managed-settlement)

## About me

Pump Fund named Dexter its seventh investment in March 2026. It invested $250,000 through a SAFE with a $10 million post-money valuation cap. In May I spoke at Solana Accelerate AI in Miami about how agents find services. I live in South Florida. [Pump Fund’s announcement](https://x.com/pumpspotlight/status/2035092234526203925) · [Investment terms](https://dexter.cash/press/dexter-pump-fund-investment) · [Watch the Miami talk](https://www.youtube.com/watch?v=AYUw9m3gfqs&t=269s)

[branch.bet](https://branch.bet/) · [Get in touch](mailto:branch@branch.bet)
