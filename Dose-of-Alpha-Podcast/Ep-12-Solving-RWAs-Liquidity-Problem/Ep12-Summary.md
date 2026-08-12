# Solving RWA's Liquidity Problem — Dose of Alpha Ep. 12

**Guest:** **Mike** — RedStone (oracle / onchain risk infrastructure)
**Hosts:** **Brian** and **Eric** (Alpha Growth — risk curator; former Compound BD)

## TL;DR

- **RedStone has expanded from a pure price oracle into the "RedStone Stack"** — a one-stop procurement layer (feeds + OEV + risk ratings + settlement) so institutions don't repeat months-long vendor due diligence for each component.
- **Core new product: RedStone Settle** — enables **T0 (same-day/instant) settlement of RWA liquidations** even when the underlying RWA's real-world redemption window is 4+ days. Launch liquidity partner: **Symbiotic**.
- **Settle's mechanism is a reverse auction on discount**: solvers bid the **percentage of par** they will pay to take over the liquidated RWA position; **highest bid wins** (e.g., 95 / 96.5 / **97** → 97 wins). The winner eats the redemption delay risk; the discount is their fee.
- **The problem it solves** (illustrated by Brian's Compound anecdote): a gold-token issuer wanted **$100M of borrow capacity** while having only **~$5M of onchain liquidity** — attestations and paper contracts don't protect suppliers of ETH/stablecoins.
- **Credora was acquired in September 2025** to bring **independent risk ratings** to DeFi — importing TradFi's decades-old norm that *yield and risk are two sides of the same coin*.
- **OEV (Oracle Extractable Value)** recaptures liquidation MEV via an **off-chain auction bundled atomically with the price update**, returning value to the protocol/curator instead of leaking to MEV bots.
- **Bull/bear ranking (deliberately contrarian): RWA #1 (most bullish) → DeFi Mullet #2 (medium) → AI #3 (killed)** — Mike will not offload financial decisions to models that still hallucinate.
- **Thesis catchphrase:** eventually there is no "onchain finance" vs. "offchain finance" — **just finance**, with the chain as infrastructure. "Remove the D from DeFi."

## Key Topics & Arguments

### What RedStone Is Today
- **Still an oracle** — price feeds remain as critical to DeFi/Web3 as ever.
- Claimed track record: **no mispricing event, no downtime since going live**.
- **The change:** price feeds alone are "not going to cut it" in 2026 once **tokenized funds and institutions** arrive — they need far more than secure feeds.
- **The RedStone Stack** — multiple products that interoperate to solve one problem end-to-end:
  - **Price feeds** (core oracle)
  - **OEV** (liquidation value recapture)
  - **HyperTree feeds** (transcribed "hip tree")
  - **RedStone Bolt** — highest-performance / fastest oracle in the market
  - **Risk / liquidation products for RWAs**
  - **Credora** (independent risk ratings, acquired)
  - **RedStone Settle** (instant RWA liquidation settlement)
- **Target customers:** risk curators, tokenization platforms, chains.
- **Strategic rationale — procurement compression:** institutions must run a **full vendor onboarding for every new supplier**, often **months of procurement**. A single platform covering multiple stack layers collapses that overhead.

### What Institutions Actually Want (Mike's four-part answer)
- **1. Risk assessment** — crypto optimized for **yield** since before DeFi Summer and largely ignored risk; **in TradFi yield and risk are two sides of the same coin**. Institutions are trained to think in risk terms and demand to see it. *(This is the stated reason for the Credora acquisition.)*
- **2. Ease of use** — crypto has always had a **high technical entry barrier**, even just to invest. Institutional allocators are **financial** experts, not technical ones; they should not have to reason about slippage, which chain, which wallet.
- **3. Compliance / regulatory profile** — a level above crypto-native norms; drives the procurement problem above.
- **4. Speed** — a **primary reason institutions come onchain at all**: TradFi cannot match onchain **settlement time** or **global remittance**. RedStone Settle is positioned as the missing piece here.

### OEV (Oracle Extractable Value) — Mechanics
- **The underlying problem:** when a lending position is liquidated, collateral is swapped for principal. Historically **MEV bots** perform this and pocket the **liquidation bonus / slippage**.
- **This value leaks out** — neither the user nor the protocol captures it; it is simply lost.
- **OEV moves the problem into the oracle:**
  - The oracle **knows a price is about to change before anyone else**.
  - On seeing an update that would trigger a liquidation, RedStone runs an **off-chain auction**.
  - Liquidators **bid in the auction instead of bidding gas / front-running each other** — near-identical UX for them.
  - Bids are **stack-ranked**, then the **price update + auction result are submitted in a single atomic transaction**.
  - Result: **zero-delay liquidation in the same block as the oracle update**, with the value returned to the protocol/curator.

### The Philosophical Debate: Should Protocols Profit From Liquidations?
- **Brian's objection:** if a protocol earns from liquidations, does it become incentivized to **encourage risk**? Is a protocol a business or not?
- **Mike's position (unchanged over ~18 months):** **No — protocols should not be *making money* out of this.** Liquidations happen regardless; **MEV is value that was leaking to nobody useful**. Recapturing it takes **nothing away from the user** — their situation is identical.
- **Long-run goal: drive MEV to zero.**
- **Empirical resolution:** curators and protocols partnered with RedStone have, **in most if not all cases, reinvested recaptured value back into the markets/protocol**, ultimately benefiting users. The concern has been settled by observed behavior.

### The Curator Margin Problem
- **Brian's "ugly truth" about DeFi:** it is **too efficient** — the spread from lender to borrower is so thin there is **not enough margin to guarantee good work around the edges**.
- **Consequence:** curators earn far less than TradFi counterparts; many **are not doing real risk provision** — curation largely **justifies their AUM** and lets them raise separately.
- **Stress test cited:** the **October 10th event** — cascading failures followed by curator shrugs ("my bad").
- **Mike's counterpoint:** this is **not crypto-exclusive** — the same happens in TradFi; the difference is TradFi has had **independent risk assessment for decades**. The problem is **not malice** — the curators he works with do their homework — it's that events like October 10th happen.
- **Solution framing:** **transparency and information are "step zero"**; each investor then decides per their own risk profile (higher risk usually = higher APY).

### What TradFi Wants That Crypto Doesn't Offer (Eric/Brian)
- TradFi borrowers want **insurance** and **loans against stock or other holdings**.
- They expect a **grace period**: "if we go under LTV, **call me, give me 3 days to top up**" — not instant liquidation.
- **Crypto liquidates in the same block.**
- RedStone's stack lets Alpha Growth **package and sell this as insurance**:
  - **(1)** Raise risk tolerance / LTVs because liquidations are now less detrimental.
  - **(2)** Offer a **~90%-style guarantee** — "in your worst case, it's really not a bad case" — a trust primitive not previously available.

### The RWA Liquidity Problem (Compound Gold-Token Case Study)
- While running BD at **Compound**, Brian was approached by **one of the two largest gold tokens**, eager to list.
- **Analysis result: liquidity was paper thin.**
  - Ask: **$100M of borrow capacity.**
  - Reality: **~$5M of onchain liquidity.**
  - Issuer's defense: "we guarantee it, we have the BIPs, the attestations, the paper contracts."
  - Compound's answer: **cannot do it** — if the issuer goes bust, suppliers of dollars and ETH bear the loss.
- **Redemption timing (the crux):** issuer said worst-case redemption to cash was **4 days** (bank-holiday + weekend); throughput roughly **$100M / 24h, up to $200M / 72h**.
- **Mike:** 4 days is actually **mild** — many RWAs have **longer windows, or no defined number of days at all** (redeemable only at specific times), which is unacceptable given crypto's expectation of **precision and speed**.

### RedStone Settle — The Solution
- **Name rationale:** allows positions to be **settled at T0 on an RWA liquidation event even when the RWA's redemption time is much longer**.
- **Origin story:** idea formed in conversation with friends from Argentina at **DevCon last year** → taken to RedStone's technical team → "across the road" to **Symbiotic** for liquidity → shipped ~**6 months later**.
- **Auction design (differs from OEV/"Atom"):**
  - OEV-style auctions: bidders compete for a **higher liquidation bonus / ticket**.
  - **Settle:** solvers **bid a discount** — the **price they'll pay as % of the position**.
  - Worked example: **Brian bids 95, Eric bids 96.5, Mike bids 97 → Mike wins** (closest to 100%).
- **Settlement flow:**
  - Position is **immediately settled at T0 against launch partner Symbiotic** (Symbiotic Ethereum initially; infrastructure supports **any asset on a whitelist basis**).
  - The winning **settler then waits out the real redemption window** (e.g., the famous 4 days), **absorbing that duration risk**, and redeems 100%.
  - **The discount is the settler's fee.**
- **Benefits:** prevents **bad debt**, delivers **immediate liquidity on RWA positions**, and solves for **both asset issuers and curators**.
- **Zero code changes for issuers** — it's **baked into the RedStone feeds**.

### Winners & Losers
- **Mike declines to pick explicit winners/losers**, but:
  - **Biggest winners: reputable RWA asset issuers** — Settle removes their **adoption friction, utilization friction, and liquidity friction** at zero integration cost.
  - **Investors win** — instant liquidity on assets where it is normally impossible.
  - **Curators win** — **materially reduced bad-debt risk**.
  - **"The winner is really the industry"** — another building block toward a **trustless** end state; no single product gets there alone.
  - **Implicit losers: RWAs that are effectively a "fraud" on liquidity** — those with no real depth get filtered out. **Even this is good for the industry**, since it **selects for reputable, secure, stable RWAs** capable of powering onchain finance.
- **Brian's addendum — nominal vs. relative:** the unlock grows the whole industry, so even "losers" may **win nominally**. Specifically he expects **DEX market share to decline**, but in an **exponentially growing market** that still means **nominal growth, just slower**.
- **Concrete pipeline signal:** the hosts had a call **that same day** with a **very large traditional lender** looking to tokenize positions to grow scale by decentralizing them.
- **Alpha Growth's follow-through:** preparing to launch **industry-leading high LTVs** that are simultaneously **the safest markets that exist**, enabled by Settle.

### Time Premium, Duration, and Speed
- **Brian's "no explicit loser" reframe: it's a market of different time premiums.**
  - Some participants want **instant liquidity at T0** (and pay the discount).
  - Others can **manage risk out to T7**, clear debt then, and **capture the time premium / rate premium as yield**.
  - It is a market segmented by **risk level and duration appetite**.
- **TradFi duration extremes cited:** funds where you can exit **once a year**, within a **30-day window**, with notice required **45–60 days before** the exit period.
- **On oracle latency (Eric's question — do we need 50ms or 20ms as chains get faster and AI accelerates exploits?):**
  - **RedStone Bolt is the fastest oracle in the market** (~10–20ms class).
  - **Mike explicitly does not recommend maximum speed everywhere** — if **block time is longer than 10ms**, a 10ms feed is **unutilized**.
  - **Design philosophy: give options and fill gaps**, rather than **imposing one direction on DeFi** ("everyone needs a 10ms oracle").
  - The portfolio reflects this: **Bolt** (ultra-fast), **HyperTree** (very fast feeds), a **pull model** (consumers pull data directly), **different push cadences per chain**, and now **Settle**.
- **Brian's closing synthesis:** the primitives are **yield, time, and risk** — the industry's job is to **tease them apart**. In crypto, one or two devs at a protocol did **risk curation and duration management simultaneously**; that's **too much for a human brain** and must be **decomposed into specialized systems** to be professional, sustainable, and maintainable at scale.

## Entity Extraction

### People
- **Mike** — guest, RedStone
- **Brian** — host (Alpha Growth; formerly ran BD at Compound)
- **Eric** — host (Alpha Growth)
- Unnamed **friends in Argentina** (DevCon conversation that sparked Settle)

### Companies / Organizations
- **RedStone** (transcribed variously as "Resdom," "Reston," "Ryson," "Resdon")
- **Credora** (independent risk ratings; **acquired by RedStone, September 2025**; transcribed once as "Predora")
- **Symbiotic** — Settle's **launch liquidity partner**
- **Alpha Growth** — hosts' firm; risk curator; RedStone partner
- **Compound** — Brian's former employer (gold-token listing story)
- **Spark** — subject of a Credora × Spark risk case study posted that day
- Unnamed **large gold-token issuer** (one of the two largest)
- Unnamed **very large traditional lender** (tokenization prospect)

### Products / Protocols / Frameworks
- **RedStone Stack** (umbrella product suite)
- **RedStone Settle** — T0 RWA liquidation settlement via discount auction
- **RedStone Bolt** — fastest oracle in market (~10–20ms)
- **HyperTree feeds** ("hip tree") — high-performance feeds
- **OEV — Oracle Extractable Value** (RedStone's liquidation-recapture product)
- **"Atom"** — prior RedStone auction product referenced as the OEV-style comparison
- **MEV** — Maximal/Miner Extractable Value
- **Price feeds** — push model, pull model, per-chain push cadence
- **DeFi Mullet** (narrative)
- **RWA — Real-World Assets** (narrative)
- **AI** (narrative — ranked last)

### Blockchains / Networks
- **Ethereum** (Symbiotic Ethereum)
- General references to **faster / real-time blockchains**

### Assets / Instruments
- **Gold tokens** (RWA case study)
- **Tokenized funds**
- **ETH**, **stablecoins / dollars** (supply side of lending markets)

### Concepts / Metrics
- **T0 / T7 settlement**, redemption window (4 days; $100M/24h, $200M/72h), **LTV**, **liquidation bonus**, **bad debt**, **slippage**, **APY**, **AUM**, **atomic transaction**, **off-chain auction**, **stack-ranked bids**, **whitelist basis**, **zero code changes**, **time premium / rate premium / duration appetite**, **risk curation**, **independent risk ratings**, **procurement / vendor onboarding**, **DEX market share**, **hallucination (AI)**, **block time**, **10–20ms update times**, **400ms block times**

### Events / Dates
- **October 10th** — cascading liquidation event used as the curator stress test
- **September 2025** — Credora acquisition
- **DevCon (last year)** — Settle's origin conversation
- **~1 year prior** — earlier podcast appearance where OEV was first discussed
- **2026** — the horizon for "feeds alone won't cut it"

### Distribution / Contact Channels
- **redstone.finance** (official website; redesign pending)
- **Twitter / X** (latest news; Credora × Spark case study)
- **Telegram** — Mike's handle is his name
- Podcast distribution: **Twitter, YouTube, Spotify**

## Chronological Flow

1. **Cold open (teaser montage):** "What do institutions truly want?" → risk assessment → the Credora acquisition rationale; DeFi is "too efficient" to leave margin for good work; Mike's contrarian **RWA-most-bullish** call; the **$100M ask vs. $5M liquidity** anecdote.
2. **Intro:** Mike welcomed; long-running relationship between RedStone and Alpha Growth established.
3. **"What is RedStone today?"** — still an oracle with a spotless record, but feeds alone are insufficient for 2026 institutional demand → the **RedStone Stack** (OEV → HyperTree → Bolt → RWA risk/liquidation) as a **one-stop shop** eliminating multi-vendor procurement.
4. **What institutions want:** (1) risk assessment, (2) ease of use for finance-native/non-technical allocators, (3) compliance and procurement relief, (4) speed — teeing up **Settle**.
5. **Host framing:** audience is technical, but jargon gets unpacked; request to explain **MEV → OEV**.
6. **OEV explained:** liquidation = collateral-for-principal swap; MEV bots pocket the bonus; value leaks. RedStone moves it into the oracle via a pre-update off-chain auction, stack-ranks bids, and submits **price update + auction result atomically** → zero-delay, same-block liquidation with value returned to the protocol.
7. **Philosophical debate:** does OEV incentivize protocols to court liquidations? Mike: **no — protocols shouldn't profit; the goal is MEV → 0**; user impact is nil; observed behavior shows curators reinvest the recapture. Debate considered settled by history.
8. **Curator economics critique (Brian):** DeFi's efficiency leaves no margin; many curators don't do real risk work, using curation to justify AUM; **October 10th** exposed this.
9. **Mike's rebuttal:** not malice, not crypto-exclusive; TradFi has had independent risk assessment for decades — hence **Credora, acquired September 2025**; **transparency is step zero**, investors choose per risk profile.
10. **TradFi's actual asks (Eric):** insurance, loans against stock, and a **3-day grace period** instead of same-block liquidation → RedStone's stack lets Alpha Growth sell that as **insurance** with **higher risk tolerance + guarantee levels**.
11. **The "F/Marry/Kill" curveball:** rank **AI, DeFi Mullet, RWA**.
    - **RWA = most bullish** ("not even a question — it's just happening"); the debate moved on from block times to tokenization/institutions/RWAs; **"the future of finance"**; catchphrase — one day there's no on/offchain finance, **just finance**.
    - **DeFi Mullet = medium** — likes the fintech-frontend / decentralized-backend crossover; **early, not bad — early is early**; smart people are betting heavily on it, but the narrative isn't as strong as RWA today.
    - **AI = kill (for now)** — not ready to **offload important financial decisions to models**; **hallucination is still real**; impressed by AI's rate of improvement but it's **the least real of the three today** for crypto/DeFi impact.
12. **Compound gold-token case study (Brian):** $100M borrow ask vs. $5M onchain liquidity; attestations don't protect suppliers; the **4-day worst-case redemption window** and $100M/24h–$200M/72h throughput define the problem.
13. **Mike escalates the problem:** 4 days is **mild** — many RWAs have longer or entirely undefined redemption windows, incompatible with crypto's precision-and-speed norms.
14. **RedStone Settle revealed:** T0 settlement on RWA liquidation regardless of redemption time; origin at **DevCon** with Argentine friends → technical team → **Symbiotic** for liquidity → live ~6 months later.
15. **Settle mechanics:** off-chain auction where **solvers bid a discount** (95 / 96.5 / **97 wins**); position settles instantly against **Symbiotic**; winner absorbs the redemption wait; discount = fee; whitelist-based asset support; outcome = **no bad debt + instant RWA liquidity** for issuers and curators alike.
16. **Winners and losers:** reputable issuers, investors, curators, and "the industry" win; low-liquidity RWA "frauds" get filtered out — itself a positive selection effect. Brian: DEX market share falls but nominal volumes still grow in an exponential market; the whole industry rises.
17. **Commercial signal:** same-day call with a large traditional lender exploring tokenization; Alpha Growth preparing **industry-leading LTVs on the safest markets**.
18. **Time-premium reframe (Brian):** no explicit losers — just **different duration appetites**; T0 buyers pay a discount, T7 holders earn the time/rate premium; TradFi's once-a-year exit windows illustrate the extreme.
19. **Oracle-speed Q&A (Eric):** Bolt is fastest in market, but **maximum speed isn't universally correct** — a 10ms feed is wasted under longer block times. Philosophy: **fill gaps, offer options, don't impose a direction**; portfolio spans Bolt, HyperTree, pull model, per-chain push cadences, and Settle. Goal: **remove the "D" from DeFi** — onchain finance powering both TradFi and DeFi.
20. **Closing synthesis (Brian):** yield, time, and risk must be **decomposed** from the one-or-two-dev protocol model into specialized, professional, scalable systems.
21. **Contact/outro:** **redstone.finance** (redesign incoming), **Twitter** (Credora × Spark case study posted that day), **Telegram** (name handle); podcast on Twitter/YouTube/Spotify.

## Key Takeaways / Conclusions

- **The binding constraint on RWAs is not tokenization — it's liquidation liquidity.** Attestations, BIPs, and paper contracts do not let a lending market safely extend $100M of credit against $5M of onchain depth. **Settlement timing, not asset quality, is the gating factor.**
- **RedStone Settle converts a duration problem into a priced risk.** Rather than forcing RWAs to become instantly redeemable, it **auctions off the waiting period** to solvers who bid a discount and absorb the redemption window — a transfer of duration risk from the protocol to a specialist.
- **The auction inverts OEV's direction.** OEV bidders compete for a larger liquidation bonus; Settle bidders compete to take the **smallest discount** — the same auction machinery aimed at protecting rather than extracting.
- **Recaptured MEV is not new revenue, it's stopped leakage.** Mike's consistent position: protocols shouldn't be *profiting* from liquidations, and the correct long-run target for MEV is **zero**; the observed reinvestment of OEV proceeds by curators defused the incentive objection.
- **DeFi's efficiency is a structural weakness at the risk layer.** Thin lender-to-borrower spreads leave no budget for genuine risk work, so curation often exists to justify AUM. **Independent ratings (Credora) are the TradFi import that fixes this** — transparency first, investor choice second.
- **Institutional adoption is a procurement problem as much as a technical one.** Bundling feeds, OEV, risk ratings, and settlement into one vendor removes months of duplicated onboarding — a commercial moat disguised as a product suite.
- **Speed is a menu, not a mandate.** Sub-20ms oracles matter only where block times can consume them; RedStone's stated philosophy is to **fill gaps and offer options** rather than push the whole market to one latency.
- **The market segments by time premium, not by winners and losers.** T0 liquidity buyers pay a discount; T7 risk-holders earn the premium — the unlock creates a duration market where none existed.
- **The endgame thesis is dissolution of the category:** no "onchain" vs. "offchain" finance, no "D" in DeFi — **just finance**, with the chain as the infrastructure layer and trust progressively engineered out, one building block at a time.
