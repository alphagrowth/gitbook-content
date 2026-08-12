# Prediction Market Philosophy — Dose of Alpha Ep. 8

*Speakers: Bryan (host) and Eric (guest/partner). Both are investors in and contributors to an AI-based prediction market platform.*

## TL;DR

- **Core debate:** Prediction markets vs. perpetual futures ("perps") — which primitive is the right tool for which use case.
  - **Prediction markets = options** (fixed price targets, expiration dates); they get "pigeonholed" and go dead once the target is hit.
  - **Perps = "better than options"** — 24/7, no expiration, continuous price discovery, constant action (squeezes, shorts, funding). Preferred for **continuous price discovery**.
  - **Prediction markets win for singular/event-driven outcomes** (e.g., political elections) where a perp makes no sense.
- **Thesis on being "the house":** The speakers are building/risk-curating the **first AI single-player prediction market** — a generalized passive liquidity provider (LP) so users can show up with an opinion and bet even where no market/liquidity exists.
- **Data-as-strategy:** Deliberately operating at a **loss** to retail (via $50K–$100K trading incentives) is a way to harvest data on **toxic flow / attack vectors**, then train models to become a smarter, sustainable house. Analogy: card-counting casinos, Uber-style loss-leader, "smart beta."
- **Philosophy:** "The greatest sign of intelligence is how far in the future you can predict an outcome" (attributed to Tatiana Colligan). AI prediction accuracy = a proxy for AGI. Also: **data wants to be free**, insider trading is inevitable, and price is the ultimate oracle of information.

## Key Topics & Arguments

### Prediction Markets vs. Perps
- **Prediction markets are functionally options:**
  - Have expiration + discrete price targets.
  - Problem: get "pigeonholed." Example — a market betting an asset goes **$3 → $5** dies if it rockets to **$11 in 4 days**; nobody trades, market closes out.
  - Liquidity "sectioning"/siphoning issues; must constantly split up new markets.
- **Perps are "the ultimate" / better than options:**
  - 24/7, no expiration, "just prints," always-on tech.
  - Continuous action: more shorting, squeezes, constant something-to-do.
  - Fundamentally = an efficient, UX-friendly money market + DEX; positions are literally **borrow/loop strategies**.
  - Critique: perps are **expensive vs. money-market loops** — "gaping holes of interest rate arbitrage."
- **Why options exist at all (historical/regulatory, not market-optimal):**
  - Legacy tech couldn't run nights/weekends; there's a "gap" markets can't cover.
  - **Tax reasons** — expiration/duration lets markets close to create **taxable events**; mark-to-market timing is about regulatory compliance, not capital/technical efficiency.
  - "If you build it from scratch, it's always perps."
- **Volatility & funding-rate mechanics:**
  - Perps require volatility **or** interest (open interest).
  - High open interest ↔ low volatility (e.g., T-bills).
  - **Chain of causation:** demand to borrow one asset vs. another (e.g., forex carry) → leverage → high utilization in a money market → funding rate in perps → more open interest.
  - If you get **OI on both sides**, you don't need volatility; **less volatility actually enables higher leverage**.
- **"Janky" expiration products / full-circle observation:**
  - Options rollover strategies, borrowing against an asset to run the options strategy, **options overlay strategies**.
  - Same ugliness reappears in prediction markets and in **Pendle** at its expirations.
  - Anything with a start/stop expiration gets ugly → spawns janky patch products → **limit as these approach zero = just perps** (no expiration).

### Being "The House" (AI Prediction Market Design)
- **Product:** first **AI single-player prediction market**; the house is the generalized passive LP.
- **Cold-start problem solved:** unlike **Polymarket** (create a market, seed liquidity, *hope* someone gambles), here you can **show up with an opinion and bet immediately** because the house provides first liquidity on a market that never existed.
- **House economics:** house must be **plus-EV**, offer equitable but unique bets, and not go broke.
- **Risk landscape (far beyond DeFi money-market risk):**
  - Old risk = smart-contract risk; new risk = **the AI is the oracle AND the market resolution.**
  - Attack vectors: **AI coordination, prompt injection, oracle manipulation.**
  - Meta-competition: choosing which (monthly-improving) AI models play/resolve = "a whole nother meta level of competition of oracles."
  - Cited comparison: **Chaos Labs leaving Aave**, citing RWA redemption/liquidation differences in **Aave V4** — the speakers' risk is "many more levels" than that.
- **Defensive tooling:** own simulations/red-teaming, expected-loss categories, expected-attack types, **machine learning + loss-prevention agents ("LP force")** to pick/choose which bets to accept and at what levels.

### Data / Toxic Flow / Card Counting (Eric's Story)
- **Card-counting background:** Eric actively beat the house; joined advantage-player **Discords (~2015–2016)** comparing casino house rules and player EV.
- **The "fishing net" casino story (early 2000s):**
  - A casino offered the best rules: **$5 minimum, re-split aces, double-down after split, surrender, ~85% deck penetration**, low table maximums.
  - Advantage players flocked in and won (thousands each, not hundreds of thousands) for **2–3 months**; casino ate the losses.
  - Then **banned everyone in one swoop**, created and **sold a "black book"** of card-counter identities to major casinos → players permanently banned everywhere.
- **Lesson = "smart beta":** a calculated loss that (a) made the house smarter and (b) monetized the **data** (charged other casinos), turning a nobody casino into a reputable one.
- **Application to prediction markets:**
  - Intentionally take losses/attract "card counters" via **$50K–$100K trading incentives** to concentrate toxic flow in one place, observe attacks, feed ML.
  - Goal: distinguish **good flow vs. toxic/mercenary capital**; only risk budgets they're willing to lose.
  - **Wallet-tagging idea:** track mercenary capital (e.g., wallets from the **Stable** and **Plasma** launches) to label toxic vs. good flow.
- **Market-maker context (ETHDenver, DAS NY):**
  - MMs are adapting these new primitives, struggling to tell real volume from insider/toxic flow.
  - Analogy: **Sushi's** liquidity-incentive structure as a "Venus flytrap" for mercenary LPs.
  - **Uniswap anecdote (~2 years prior):** their biggest challenge was capturing **retail flow vs. toxic flow** — getting retail to use Uniswap as first line of sight vs. CEXs/other DEXs → chose the **"app store" route** (direct-to-user).

### AI, Intelligence & the Financialization of Prediction
- **Thesis:** intelligence = how far into the future you can accurately predict/simulate outcomes across many realities → the more accurate & far-out, the closer to **AGI**.
- **"My AI is smarter than your AI":** if your AI is smarter, you should win every bet; if the house loses, it learns and closes the gap. Requires a *sustainable* house — you need the house to beat enough others to fund your payouts (a balanced game).
- **New niche primitive:** beyond price speculation / store of value / interest-rate arbitrage / rate discovery — prediction markets add a **"computational future projection"** layer: AI financialized to its maximum.

### Philosophy: Data, Truth & Insider Trading
- **Data wants to be free** — to float, coagulate, aggregate, distill; releasing more data is the entropy/chaos-theory-favored path and "the progress of humanity."
- **Insider trading is inevitable:** the point of banning it is to stop insiders profiting from valuable info — but valuable info becomes a **commodity**; it always happens, question is only *public or not*.
- **Wisdom-of-crowds:** at scale, the gambling framework produces societal information — a libertarian-ethos question of whether info should be free / insider trading stoppable globally ("infinite games to regulate," whack-a-mole).
- **Price as ultimate oracle:** invokes **Milton Friedman** — price is the fastest indicator of information, how all society/business functions; regulation reduces efficiency and destroys the free market.
- **Tension:** free information could eliminate market makers (informed players constantly profit at LPs' expense) → scary but beautiful to be the house **if you can monetize the data**.
- **"Two of three" maxim:** you can pursue only two of **truth, happiness, or money**; more data = more truth; restricting data holds back truth.
- **Religious framing:** a Christian view that "all secrets will be made known" (references **Ashley Madison** leak, **Epstein files**) — secrets are secret only for so long.

## Entity Extraction

- **People:**
  - Bryan (host)
  - Eric (guest/co-investor; ex card counter)
  - Tatiana Colligan (Eric's wife — origin of the "intelligence = far-future prediction" quote)
  - Milton Friedman (economist, cited on price/information)
- **Companies / Protocols / Platforms:**
  - Polymarket (prediction market — cold-start/liquidity contrast)
  - Uniswap (DEX — retail vs. toxic flow anecdote; "app store" route)
  - Sushi / SushiSwap (LP incentive "Venus flytrap" analogy)
  - Pendle (yield protocol — expiration jankiness example)
  - Aave / Aave V4 (RWA redemptions & liquidations)
  - Chaos Labs (risk curation firm that left Aave)
  - Uber (loss-leader business model analogy)
  - Sliced Investing → Stratifi (options-overlay strategy firm Eric worked at; acquired/renamed)
  - Ashley Madison (data-leak reference)
- **Tokens / Blockchains / Launches:**
  - Stable (launch — mercenary-capital wallet-tracking example)
  - Plasma (launch — mercenary-capital wallet-tracking example)
  - T-bills (low-volatility / high-OI asset example)
- **Financial Instruments / Frameworks / Concepts:**
  - Prediction markets; Perpetual futures (perps); Options; Futures; NFTs
  - Options overlay / rollover strategies
  - Money markets, funding rate, open interest, utilization, leverage, interest-rate arbitrage, rate discovery
  - Spot oracle; Toxic flow; Mercenary capital; Wisdom of crowds; Smart beta; EV (expected value)
  - Cold-start problem; Single-player prediction market
  - AGI; Prompt injection; AI coordination; Loss-prevention agents ("LP force")
- **Events / Venues / Communities:**
  - ETHDenver (conference)
  - DAS New York / "desk New York conference" (Digital Asset Summit)
  - Advantage-player Discords (~2015–2016)
- **Casino/card-counting terms:** deck penetration (~85%), re-split aces, double-down after split, surrender, table minimum/maximum, the "black book."

## Chronological Flow

1. **Cold open / hook:** intelligence = far-future prediction; teaser of building the first AI (single-player) prediction market that solves the cold-start problem by being "the house."
2. **Framing:** the "philosophical battle" — prediction markets vs. perps; how MMs handle toxic flow; the future of trading information.
3. **Disclosure & setup:** they invested in an AI prediction market; idea of a futures market via prediction market on a nascent low-liquidity asset (NFT-like); Eric argued **perps would be better**.
4. **Prediction markets = options argument:** expiration + price targets → pigeonholing; the $3→$5→$11 dead-market example; perps give constant action.
5. **Perps deep dive:** perps as "better than options"; volatility vs. open-interest/funding mechanics; T-bills/forex carry causation chain; less volatility → higher leverage.
6. **Why options exist:** nights/weekends legacy tech + **tax/regulatory** reasons (taxable events at expiration), not market-optimality.
7. **Full-circle jankiness:** rollover/overlay strategies (Sliced Investing → Stratifi), Pendle expirations → "limit approaches zero = just perps."
8. **Perp scope caveat:** perps only fit continuous price discovery; **event-driven (elections)** belongs to prediction markets; perps = money market + DEX loops (but expensive → interest-rate arb gap).
9. **Card-counting story:** advantage-player Discords → early-2000s "fishing net" casino → mass ban + monetized "black book" = **smart beta / calculated loss for data**.
10. **Application to the house:** operate at a loss to harvest toxic-flow data; ML + loss-prevention agents; wallet-tagging mercenary capital (Stable/Plasma); Sushi flytrap; Uniswap retail-vs-toxic-flow anecdote.
11. **Incentive plan:** $50K–$100K trading incentives to invite "card counters," learn attack vectors, only risk budgets they can lose.
12. **Risk/attack surface:** AI as oracle + resolution; prompt injection, AI coordination; model-selection meta-game; Chaos Labs/Aave V4 comparison.
13. **Intelligence philosophy:** Tatiana Colligan quote → AI future-prediction accuracy as AGI proxy → "my AI vs. your AI" sustainability of a balanced house.
14. **New primitive:** "computational future projection" beyond rate discovery.
15. **Data & insider-trading philosophy:** data wants to be free; insider trading inevitable (public vs. not); wisdom of crowds; regulatory whack-a-mole.
16. **Friedman / price-as-oracle:** free info threatens MMs but is beautiful if data is monetizable; two-of-three (truth/happiness/money); Christian "all secrets revealed" (Ashley Madison, Epstein).
17. **Close.**

## Key Takeaways / Conclusions

- **Both primitives persist:** perps (the "ultimate," continuous-discovery tool) and prediction markets (the "super option," event-driven tool) coexist rather than one replacing the other.
- **Options are a legacy/regulatory artifact** (nights-weekends + tax/taxable-event mechanics); a from-scratch design defaults to perps.
- **Funding-rate insight:** deep two-sided open interest can substitute for volatility, and low volatility permits higher leverage.
- **The house's edge is data, not any single bet:** deliberately losing to retail (funded incentives) to map toxic flow / attack vectors is a "smart beta" strategy mirroring the fishing-net casino and Uber.
- **AI-native risk is categorically new:** the AI is simultaneously oracle and resolver, exposing prompt injection, coordination, and model-selection attack surfaces exceeding traditional DeFi (Chaos Labs/Aave V4).
- **Sustainability requires balance:** the house must win enough to keep funding winners so a "house to beat" continues to exist.
- **Guiding philosophy:** intelligence = accurate far-future prediction (AGI proxy); data/price trend inexorably toward freedom; insider trading is unavoidable and only becomes a monetizable commodity — the winning move is to capture and monetize the resulting data.
