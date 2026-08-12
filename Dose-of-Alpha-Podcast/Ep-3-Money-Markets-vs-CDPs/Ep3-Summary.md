# Money Markets vs. CDPs — Dose of Alpha Ep. 3

Hosts: **Eric** and **Bryan** (from **Alpha Growth**). Topic: comparing DeFi **Money Markets** vs. **Collateralized Debt Positions (CDPs)** — mechanics, risks, peg maintenance, bad debt, and use cases.

## TL;DR
- **Money markets** = bare-bones peer-to-peer lending: borrow an asset someone else holds, at a rate, fully collateralized; requires a **counterparty**; simplest, most "vanilla" entry point.
- **CDPs** = mint a synthetic dollar against your own collateral; **no counterparty needed**, but you must manage **peg maintenance** and **redemptions**.
- **CDP tradeoff:** higher origination fee + lower interest rate → cheaper for **long-hold positions** (>~1–2 months); money markets cheaper for **high-frequency** in/out.
- **CDPs invented DeFi:** Tether on Bitfinex was the first CDP-like synthetic dollar; MakerDAO (now **Sky/USDS**) was the second iteration on ETH.
- **Bad debt** is fatal in crypto — no bankruptcy backstop; it's a **zero-sum game**. A partially-exposed fractional reserve becomes fully exposed via a **run on the bank** (cf. **Terra/Luna**).
- **Generalized vs. isolated markets:** generalized (Aave/Compound) = efficient/cheaper but shared contagion risk; isolated (Morpho) = safer/purer but liquidity fragmentation, cold-start, and higher cost.
- **October 10th ("10/10")** stress event: **CDPs did NOT de-peg**, money-market carry trades ran negative with spiking rates; **decentralized oracles held, some centralized ones broke.**
- Core thesis: protocols/asset issuers should lean into **CDPs** to bury tokens and build durable, deep liquidity; carry trades work better on CDPs for long holds.

## Key Topics & Arguments

### Money Markets — fundamentals
- Definition: **"absolute bare bones of lending"** — borrow an asset a counterparty holds, at a rate they accept.
- Traditionally **fully secured** → liquidations are manageable, lenders get paid, safe & efficient.
- Variants: **isolated** vs. **generalized** markets; newer "fancy" forms via **V4 pools** and **Euler Swap (oiler swap)**.
- Best **first step for basic users** — most predictable, you know what/how much you borrow.

### CDPs — fundamentals & history
- **CDP = Collateralized Debt Position:** deposit collateral, mint debt, position nominally worth $1.
- **CDPs "invented DeFi":**
  - **Tether / USDT on Bitfinex** = first original CDP-like construct — users hedged Bitcoin exposure; Bitcoin fully collateralized → borrow USDT at a rate; Bitfinex was effectively the counterparty; later tokenized. Over time Tether shut that market and diversified into **T-bills, Bitcoin, other holdings**. = the **original synthetic dollar**.
  - **MakerDAO** = second iteration, on **ETH**; hedge exposure via **DAI**.
    - **Levered loop:** deposit ETH → mint DAI → buy more ETH → repeat (pushes ETH price up, adds exposure).
    - ETH reserves alone couldn't hedge appropriately → added **USDT/USDC** as collateral.
    - Now ~**$6–7B** across placements; rebranded to **USDS of Sky**.
- **Advantage:** no counterparty required to borrow.
- **Disadvantage:** must maintain **peg** for the printed dollar; you can mint a dollar-pegged token but must be able to liquidate/redeem it back to $1.

### Peg maintenance, redemptions & attacks
- Price of borrowing a CDP should be **cheaper than buying $1 of USDC**; if not, the peg construct is flawed → **peg ward / de-peg risk**.
- **"Run on the bank" attack:** an attacker eats up all counterparty liquidity around the peg → spikes CDP value down → destroys peg.
- **Older mechanism:** peg maintenance relied only on **liquidity pools**; liquidity is expensive to source.
- **Liquity V2-style redemptions:** allow **redemption for original collateral**, creating a liquidation mechanism if peg drops too low → far more stability.
- Real example (**Liquity / bold**, ETH-only, three versions):
  - **rETH** maintains peg worse than **wstETH** because of redemption/peg-maintenance design.
  - rETH shows a **lower average borrow rate** — redemptions prefer assets with better spot liquidity, pushing those borrow rates higher; rETH "extracts against competition" for having worse peg maintenance. "Is what it is," not clearly a feature or flaw.

### Money Market vs. CDP — when to use which
- **Money market:** basic users, high-frequency traders/liquidity providers, need to move fast, flash loans on Aave.
- **CDP:** long-term holders (>~1–2 months), **lower interest rate** at cost of **higher origination**, less slippage/execution cost converting collateral (ETH/BTC) → dollars.
- **Mortgage analogy (Bryan):** money market = 0.25% (or fixed) origination + 6% rate; CDP = higher origination (e.g., $30k vs $10k) but 4% rate → saves money over a long enough hold.
- Caveat: **most CDPs currently lack the capacity** of money markets — expected to change over time.

### Bad debt
- Modern economies survive via **bankruptcy** (subsidize, reset) — **crypto has no such backstop**; a hack/hole = money fully gone; everything built on top suffers.
- If a protocol accrues **bad debt** → fractional reserve that can't be made whole → **self-exposing**: partial exposure triggers a run that fully exposes it (**Terra/Luna** cited — could have survived short-term panic).
- Triggers: **money market** = liquidations not processing in time; **CDP** = a collateral asset falling faster than (cascading) liquidations can occur.
- **Whoever liquidates fast enough wins** in a contagion.
- Key components: **collateral risk**, **liquidations** (most important), **bailouts**.

### Generalized vs. isolated markets (scalability vs. security)
- **Generalized (Aave, Compound):** 10–15 assets; more efficient rates, easier liquidity/liquidations ("buying in bulk"), but **shared contagion** — one asset's bad debt infects all markets. Also **misprices collateral**: BTC might justify 3–5% but everything borrows USDC at ~4% at the same rate.
- **Isolated (Morpho):** one collateral, one borrowable asset — **purity** and protection from other protocols failing, but:
  - **Cold-start problem**, **liquidity crunch**, less withdrawal flexibility.
    - *Utilization example:* 90% util on a $1B market = $100M withdrawable; 90% on a $10M market makes moving a $5M size hard.
  - Requires a **curator** (expensive), matched assets, and self-sourced suppliers.
  - Rule of thumb: markets **≤$10M often don't justify existing** given fee/tooling overhead; curators want **$10M–$100M** markets.
- **Maturity path ("minor leagues → major leagues"):** asset starts isolated → grows liquidity/holders → graduates into generalized markets; scale leverage incrementally.
- CDPs face **similar risk**: they are generalized around the stable token; if any collateral capitulates and accrues bad debt it affects everything (severity depends on speed/size/liquidation capacity).

### October 10th ("10/10") stress test — findings
- **No CDP got crazily affected or de-pegged** on 10/10 → contradicts the usual claim that CDPs are less safe than money markets.
- Money-market looping/carry trades saw **spiking rates**, **negative carry**, expensive unwinding; **CDP rates barely impacted** → more stability for long-term positions.
- **Oracles:** decentralized oracles historically got wrecked (people used centralized CEX-based oracles for protection), but on 10/10 the **decentralized oracles held** and some **centralized ones broke** → possible inflection point where decentralized is genuinely safer.
- **Deep liquidity → better oracles:** thin liquidity makes **market-rate oracles** manipulatable; building liquidity from a CDP from the start means you know your achievable depth and oracle protection.
- Recurrence: 10/10-type events happen **once or twice a year** (a **~20–25% dip** happened the prior weekend) → leveraging a CDP for de-risking / token protection is becoming a **necessity**.

### Underappreciated risks
- **CDPs:** peg maintenance details; how **redemptions** occur; understanding **arbitrage**. Minting "a dollar" ≠ it actually being $1. Focus should be on **under-peg** protection (over-peg is never the problem) — CDPs tend to trade slightly under peg, which effectively *is* the origination cost.
- **Money markets:** understanding the **collateral**. **Stream Finance / 10/10** lesson: minting a synthetic dollar to fund a **basis trade** (borrow 8%, earn 10%) is fine *as arbitrage*, but was **disclosed as secured lending when it was really a line of credit** → users didn't know they were at risk. If you're chasing the highest money-market rate, that's likely why.

### Structured products & the carry trade (on CDPs)
- **Carry trade** = earn more supplying an asset than you pay borrowing another → manufacturing yield via **rate arbitrage**. Useful for otherwise-idle assets (BTC/gold can't be staked / don't self-yield).
- **Mechanism:** deposit gold/BTC → borrow dollars at 7% → lend dollars at 10% → capture the **3% spread**.
- **BTC yield:** high demand, structurally low, mostly sourced from carry trades; seeing **fixed/capped rates** against Bitcoin.
- **CDP advantage in carry:** e.g., borrow BTC at **7% on Aave** vs **5% on Liquity** — with dollars earning 10%, the extra 2% massively boosts profit over a long hold.
- Alpha Growth is building CDP structured products for BTC, staked ETH, and other assets: efficient borrow rates via safest CDP versions, managing LTV, borrow rates, and redemption protection so user collateral (e.g., BTC) stays protected while borrowed dollars out-earn borrow cost.

## Entity Extraction
- **People:** Eric (host/guest), Bryan (host), Malcolm Gladwell (referenced — piece on police "use of force" complaints / Pareto long tail).
- **Companies / Organizations:** Alpha Growth (the hosts' firm), Bitfinex, Tether, Sky (formerly MakerDAO), Stream Finance.
- **Protocols:** MakerDAO, Aave (AVE/VE), Compound, Morpho, Euler Swap ("oiler swap"), Liquity ("liquidy"/"bold").
- **Tokens / Stablecoins:** USDT (Tether), USDC, DAI, USDS (Sky), Bitcoin (BTC), Ethereum (ETH), rETH (R ETH), wstETH (wrapped staked ETH).
- **Blockchains:** Bitcoin, Ethereum (ETH / on-chain).
- **Concepts / Frameworks / Instruments:** CDP (Collateralized Debt Position), Money Market, Carry trade, Basis trade, Structured products, Oracles (decentralized, centralized/CEX-based, market-rate), Peg maintenance, Redemptions (Liquity V2-style), Isolated vs. Generalized markets, Bad debt, Run on the bank, Fractional reserve, Flash loans, V4 pools, LTV (loan-to-value), Supply caps, Utilization rate, Liquidations / cascading liquidations, Curators, Synthetic dollar, Line of credit, T-bills, Pareto principle / long tail.
- **Events:** October 10th ("10/10", "10 10") crash; Terra/Luna collapse; prior-weekend ~20–25% market dip.

## Chronological Flow
1. **(Intro banter — excluded):** card-counting side hustle, casino surveillance, Malcolm Gladwell / police use-of-force Pareto tangent.
2. **Framing:** "What is a money market and what is a CDP — which is better?" → answer: **different strokes, both have use cases.**
3. **Money markets defined** as bare-bones, fully-secured lending; note isolated vs. generalized and V4 pools / Euler Swap.
4. **CDP history:** Tether/Bitfinex as first synthetic dollar → MakerDAO on ETH → levered DAI loop → added USDC/USDT collateral → rebrand to Sky/USDS (~$6–7B).
5. **Peg mechanics & attacks:** counterparty-free but needs peg maintenance; run-on-the-bank attacks; Liquity V2 redemptions for stability.
6. **Use-case split:** money markets for basic/HFT users; CDPs for long holds (lower rate, higher origination) — mortgage refinance analogy.
7. **Bad debt:** no bankruptcy in crypto; self-exposing fractional reserves; Terra/Luna; liquidation speed decides winners.
8. **Generalized vs. isolated markets:** contagion vs. purity; collateral mispricing on Aave; cold-start/liquidity-fragmentation costs; $10M–$100M curator sweet spot; minor-vs-major-leagues maturity path; CDPs share the same generalized-contagion issue.
9. **Cohort recommendations:** protocols → CDPs to bury tokens & build liquidity; users → money markets for speed, CDPs for long carry trades.
10. **10/10 stress test:** CDPs didn't de-peg; money-market carry ran negative; decentralized oracles held vs. centralized breaking → decentralization inflection point; deep liquidity → better oracles.
11. **Hidden risks:** CDP peg/redemption/under-peg understanding; money-market collateral risk; Stream Finance basis-trade-disclosed-as-secured-lending lesson.
12. **Structured products / carry trade walkthrough** on CDPs (gold/BTC borrow-dollars-lend-higher; Aave 7% vs Liquity 5% example; Alpha Growth's BTC/stETH products).
13. **Close:** thanks / sign-off (excluded).

## Key Takeaways / Conclusions
- **CDPs are more resilient than commonly believed** — 10/10 proved they held peg while leveraged money-market carry trades blew out.
- **Match the instrument to holding period:** high-frequency/short → money market; long hold/carry → CDP (lower rate offsets higher origination).
- **Security vs. scalability is the central tradeoff** for isolated (Morpho) vs. generalized (Aave/Compound) markets — and it recurs for CDPs.
- **Bad debt is uniquely dangerous in crypto** (no bankruptcy backstop); liquidation speed and collateral quality are the decisive risk factors.
- **Disclosure matters:** synthetic-dollar-funded basis trades marketed as "secured lending" (Stream Finance) hid real risk from users — highest advertised rates usually signal it.
- **Deep, CDP-built liquidity → more robust oracles → protection from 10/10-style contagion**; protocols and asset issuers should prioritize CDPs and durable liquidity, treating a CDP allocation as a near-necessity going forward.
- **CDP infrastructure remains under-utilized** but, provided reserves are full (not fractional), is core DeFi plumbing enabling deeper trading and structured products.
