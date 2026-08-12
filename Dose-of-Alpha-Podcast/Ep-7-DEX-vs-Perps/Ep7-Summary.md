# DEX vs Perps — Dose of Alpha Ep. 7

## TL;DR
- **Core debate:** Do new assets still need the traditional DeFi pipeline (**DEX → money market → CDP → perps**), or can high-liquidity assets skip straight to perpetuals?
- **Catalyst:** At the **Digital Asset Summit (DAS)** in NYC, the **S&P 500 digital team** launched S&P 500 index exposure **directly on Hyperliquid**, skipping DEXs, tokenization, and lending markets — doing **~$250M volume in one Monday**, an estimated **~$2.5M/day** fee capture for the market spinner-upper.
- **Key tension:** **Scalability vs. security.** Perps/synthetic liquidity scale and print money "until you don't" (craps analogy — "makes money until you seven out").
- **Perps risks:** Auto-deleveraging (ADL), retroactive settlement reversal (**Jelly attack**), spot-liquidity manipulation on long-tail assets, and prop-AMM quote-vs-execution exploits.
- **Verdict:** Assets with **deep existing spot liquidity + legitimate off-chain price discovery** (S&P 500, BTC, ETH) can go straight to perps. **Long-tail / illiquid assets still need spot** to establish price and safe liquidation resolution. Yield-bearing RWAs (T-bill-backed) won't generate perp volume.
- **Macro thesis:** On-chain **global rate discovery / rate arbitrage** is emerging; perps are the first leg. Institutional entry is **predatory, non-composable** ("a new playground to get richer"), not validation of crypto-native bags.

## Key Topics & Arguments

### 1. The S&P 500 → Hyperliquid "skip"
- Speaker (Eric) spoke to a member of the **actual S&P 500 digital team** (not a third-party tokenizer) at **DAS NYC**.
- They **skipped**: DEXs, tokenization, lending markets (**no Aave / Morpho integration**).
- Went **straight to Hyperliquid** as first stop.
- Estimated fee take: **~75 bps to 150 bps (1.5%)** for the party supplying spot / spinning up the market → ~$2.5M on a $250M day.
- **Break from DeFi norm:** Traditional path = build DEX liquidity → qualify for money market → CDPs → then perps. S&P 500 inverted it.

### 2. Steelman perps / Strawman DEX+lending (assigned framing)
- **Why pay for DEX liquidity at all?**
  - Depends on **asset profile**: yield-bearing/market-fund assets may not need it; **volatile** assets people want to hedge/speculate on do.
  - Perps give access to the **"most degenerate crowd of gamblers"** (attention/volume on Hyperliquid).
  - **New primitive for TradFi:** they already have spot + borrow/lend; what they *lack* is **100x long/short**, 24/7.
- **Rebuttal (spot matters):**
  - DEXs provide **price discovery / a base**; selling volatility with no underlying = "trading margin without an official position" = dangerous.
  - Need a **base to reconcile leverage, liquidations, redemptions**.
  - Without it → margin liquidates to nothing → app eats **bad debt**, OR app does **(retroactive) auto-deleverage**.
  - **S&P 500 is the exception** — price discovery already exists on TradFi rails (E-Trade, etc.); DEX is how crypto-native assets *replicate* that built-in liquidity.

### 3. Perps mechanics & risks
- **Hyperliquid design:** balances **open interest** on both sides; flips **funding rate** to rebalance (example: **~22% paid to 1x long BTC** during heavy short pressure ~2 weeks prior). Also runs a **spot DEX**.
- **Leverage caps:** Hyperliquid ~**40x BTC / 25x ETH**; competitors offer **~100x BTC/ETH**.
- **Synthetic liquidity:** exchange doesn't hold all the dollars behind open interest; profits from borrowing that synthetic supply (M1/M2/M3 analogy). "All the profits without any of the supply costs."
- **Pre-market:** Hyperliquid lists perps **before spot exists** (examples: **Monad, EigenLayer ("iGen"), Wormhole**).
- **The Jelly attack:**
  - High-FDV/low-float meme token **JELLY**; Hyperliquid had a small validator set (~4–5; now ~40).
  - Attacker used **spot manipulation (incl. on Solana)** as base liquidity, drove a perp position (~$4–5M).
  - **~4–5 validators colluded** to declare it an exploit, **froze the winner, unwound the position, denied payout** → first proof the "decentralized" game can be **rigged** (regulatory-dodging, not truly decentralized).
  - Historical parallel: **"Humpy the whale"** — per **Kroll FTX audit**, took ~$1B out of **FTX/Alameda** via the **BitMax** token (now **AscendEX**); pumped 13¢ → $3, "pistoned" leverage up/down eating exchange revenue.
- **ADL (Auto-Deleveraging):**
  - Happened again on **"10/10"**: too many won on shorts, highest-leverage shorts (10x/25x on BTC/ETH) got auto-deleveraged **in real time** (transparent, not retroactive like Jelly).
  - You can **lose unlimited but only win a capped amount** — likened to casino **max aggregate table payouts** (table wins $60k each but split a $50k cap).
- **Casino analogy (card counting):** offer a beatable game, then ban the winner — but Hyperliquid went further by **clawing back winnings** in Jelly.

### 4. Prop AMMs & new exploit vectors
- **AMM history (TLDR):** Uniswap full-range → farmed fake governance tokens for liquidity → **concentrated liquidity (Uni V3)** → **loss-versus-rebalancing (LVR)** losses → add lending yield (M1→M2, funds in money markets pulled back to settle trades; e.g., **"Bunny"**).
- **Prop AMM = synthetic / just-in-time (JIT) liquidity**, connects to money markets (like **"oil swap"/1inch-style"**), quotes to **aggregators**.
- **Exploit:** win the aggregator route with a tight quote, then **fail to honor it** — execute **~10–12 bps worse** ("sorry, slippage") in the gap between quote acceptance and execution. New MEV/OEV variant ("$1 sandwich becomes $1.10").

### 5. Synthetic liquidity & systemic (too-big-to-fail) risk
- Synthetic/printed liquidity = highest efficiency (fees with no cost basis); enables **10–20% carry returns** "farming uneducated depositors… until it blows up (e.g., Stream)."
- **Terra Luna** (20% APR, don't ask where it came from) as the cautionary hurdle-rate spiral.
- **Ethena** case: brought to **Compound**, rejected as **too synthetic / not close to M0**; grew to **$1B → $5B** = potential Terra-style contagion. Now floats near **T-bill** yields when funding is weak; more attractive as funding/utilization rises.
- **Tether "truthers":** if **Tether** fails, **≥50%** of total market cap goes down → forces players to be **Tether-aligned or Ethena-aligned**.

### 6. Institutional entry: predatory, not composable
- TradFi *is* coming — but S&P 500 launch is **not composable**, not "n+1 for the ecosystem"; **Hyperliquid captures all the money.**
- They **explicitly refused Uniswap** (own centralized trading infra).
- **No 2021-style validation halo** (arbitrary tokens not pumping 500% on the news) → less hope for bailing out old bags (DeFi summer / NFT summer).
- Framing: "You were right about the tech; **we'll build our own games to get richer at your expense.**"
- **Upside:** global, low-barrier access — **~$10 minimum** on Hyperliquid vs. TradFi gates (**$25k** for options at E-Trade/Schwab; **~$250k** accredited-investor threshold). 25,000 agents with $1 each vs. one party gatekept at $25k. Derivative demand should **resolve down to the underlying** (PAXG-style) → possibly **$100M–$1B** flowing back into the S&P/US economy.

### 7. When perps vs. spot vs. lending (pros/cons)
- **Skip to perps IF:** asset already has **massive volume + deep liquidity + real price discovery** (S&P 500, BTC, ETH).
- **Must start at spot IF:** long-tail/illiquid — need price discovery **and** a safe liquidation resolution point (else vulnerable to Jelly/Humpy-style base-liquidity manipulation: show liquidity to size the perp, then pull it → bad debt).
- **RWAs / T-bill-backed / yield-bearing stables:** "should only go up," **won't trade perp volume** (volatility only appears when something's badly wrong); better suited to **loans against the position** / carry trades (Bitcoin carry). Possible niche: **insurance-type / depeg contracts**.
- Loops available across **perps ↔ spot ↔ lending/CDPs**; watch **M2/M0 ratio (~4.2x now)** — higher leverage → higher pop risk.

### 8. Taxes & regulation
- **Perps = "perpetual options"**, no expiration / no forced mark-to-market → ambiguous vs. US dated options (which mark to market). Could push gains into **long-term brackets** or defer indefinitely ("until inherited in a trust").
- This ambiguity **blocked perps in the US**; **Coinbase** now getting a version via new legislation.
- Argument: expiration dates were only ever an artifact of **no 24/7 markets + limited accounting** — **perpetuals are more logical** absent legacy regulation.

### 9. Volume data & the market landscape
- **2024:** DEX and perp volume roughly **equal**.
- **2025:** perp volume ~**2x** DEX; on track for perps to **~triple** DEX volume; DEX still growing **~30–40%/yr**.
- Proliferation: "10 new perps launched," **every chain has its own** — **Lighter, Aster, Avantis, Nirvana(?)** — competing via funding incentives.
- **Business opportunity flagged:** aggregated **granular open-interest / funding-rate data across all perp venues** doesn't exist affordably (TradFi equivalents ~**$500k/yr licenses**) — valuable AI-training input.

### 10. Macro thesis: on-chain rate discovery
- Perps are the **first leg** of **global on-chain rate discovery & rate arbitrage**.
- Parallel to **offshore entities** (companies incorporate offshore for tax/rate arbitrage; example: **Nike renting its logo from a Panamanian foundation** to run at a loss).
- As borders dissolve online, rate discovery equalizes across regions (e.g., **~25% APR loans to profitable LATAM businesses** whose local alternative is ~30% APR in a worse currency).
- Next frontier flagged: **currency perpetuals / FX arbitrage** (mentioned on a venue "ODM(?)").

## Entity Extraction

### People
- **Eric** (co-host / guest)
- **Host** (unnamed; casino/card-counting background)
- **"Humpy the whale"** (whale actor, FTX/BitMax exploiter)

### Companies / Institutions / Exchanges
- **S&P 500 (digital team)**, **FTX**, **Alameda (Research)**, **Kroll** (FTX audit), **Coinbase**, **E-Trade**, **Charles Schwab**, **Compound (Labs)**, **New York Stock Exchange**, **Nike**, **Panamanian foundation** (tax structure), **AscendEX** (formerly BitMax)

### Protocols / Platforms / Apps
- **Hyperliquid**, **Aave**, **Morpho**, **Uniswap** (V2/V3), **1inch** ("oil swap"-style aggregator), **Ethena**, **Tether**, **Terra / Luna**, **Stream**, **Bunny**, **Lighter**, **Aster**, **Avantis**, **Nirvana(?)**, **"ODM"(?)** (currency perps venue)

### Tokens / Assets
- **JELLY**, **BitMax token**, **BTC/Bitcoin**, **ETH/Ether/Ethereum**, **PAXG** (PAX Gold, referenced), **S&P 500 index (perp)**, **crude/light oil (perp)**, **T-bills / RWAs / yield-bearing stables**, **DAI** ("DED"(?) decentralized stable reference)

### Blockchains
- **Solana**, **Ethereum**, **Monad**, **EigenLayer** ("iGen"), **Wormhole**

### Concepts / Frameworks / Primitives
- **Perpetuals (perps)**, **DEX / spot**, **money markets / lending**, **CDPs**, **AMM / concentrated liquidity / prop AMM / JIT liquidity**, **LVR (loss-versus-rebalancing)**, **MEV / OEV**, **funding rate**, **open interest**, **ADL (auto-deleveraging)**, **synthetic liquidity**, **M0/M1/M2/M3 money supply**, **carry trade / delta-neutral / basis**, **rate discovery / rate arbitrage**, **Oracle**, **validator set**, **mark-to-market**, **"dead tree contracts" (T+2 redemption)**

### Events
- **Digital Asset Summit (DAS), New York** (Friday the 27th), **Jelly attack**, **"10/10" ADL event**, **2008 financial crash**, **Iranian attack / oil spike weekend**

## Chronological Flow
1. **Cold open / hook:** S&P 500 skipped DEX + tokenization + lending, went straight to Hyperliquid; "scaling makes money until you seven out"; TradFi builds its own games to get richer.
2. **DAS recap:** Speaker met the real S&P 500 digital team; $250M Monday volume; ~75–150 bps fee → ~$2.5M/day; no Aave/Morpho.
3. **Framing set:** host steelmans perps, strawmans DEX+lending; debate why pay for DEX liquidity.
4. **Spot's necessity:** price discovery, base for liquidations/redemptions; bad debt vs. ADL without it.
5. **Jelly attack** explained → validator collusion, frozen winnings, "rigged game."
6. **Humpy / BitMax / FTX** historical parallel (Kroll report).
7. **Card-counting/casino analogy;** ADL again at "10/10"; casino max-aggregate-payout parallel.
8. **Hyperliquid mechanics:** funding-rate balancing, 22% 1x-long example, leverage caps, pre-market (Monad/EigenLayer/Wormhole).
9. **DEX/AMM history:** Uniswap → governance-token farming → concentrated liquidity → LVR → lending-integrated (Bunny) → **prop AMMs** and quote/execution exploits.
10. **Synthetic liquidity → systemic risk:** carry returns, Terra Luna, Ethena/Compound rejection & contagion scale, Tether too-big-to-fail.
11. **Institutional entry critique:** non-composable, Uniswap refused, no validation halo, predatory but democratizing ($10 min vs. $25k/$250k gates), resolves to underlying.
12. **Decision rule:** perps for deep-liquidity assets; spot-first for long-tail; RWAs/T-bills won't trade perps.
13. **Taxes/regulation:** perpetual options ambiguity, US block, Coinbase legislation, expiration dates as legacy artifact.
14. **Volume data:** 2024 parity → 2025 perps ~2x, tracking ~3x DEX; perp proliferation (Lighter/Aster/Avantis/Nirvana); flagged data-aggregation business opportunity.
15. **Macro close:** on-chain global rate discovery/arbitrage, offshore/Nike/LATAM analogies, currency perps as next frontier; sign-off.

## Key Takeaways / Conclusions
- **Not all assets need the DeFi pipeline anymore.** Deep-liquidity, externally-price-discovered assets (S&P 500, BTC, ETH) can launch **perp-first**; everything else still needs **spot** to bootstrap price and safe liquidations.
- **Perps > DEX in volume and growth** and accelerating (2x → ~3x DEX in 2025); every chain is launching one.
- **"Decentralized" is conditional.** Jelly (retroactive) and 10/10 (real-time) ADL prove venues will **cap wins / claw back / reverse** to protect solvency — the house can change the rules.
- **Synthetic liquidity is maximally profitable and maximally fragile** — the recurring failure mode (Terra, Stream, Ethena-scale contagion, Tether concentration).
- **Institutional adoption is extractive, not validating** — new profit playground, non-composable, no automatic bag pump; but it does **democratize access** globally at a **~$10 minimum**.
- **Prop AMMs introduce new exploit surfaces** (quote-vs-execution / JIT MEV/OEV).
- **Regulatory/tax treatment of perpetual options is unresolved** and shaping US access (Coinbase legislation path).
- **The bigger meta-thesis:** perps are the leading edge of **on-chain global rate discovery and rate arbitrage** (extending to FX/currency perps), with an open **data-aggregation business opportunity** around cross-venue open interest and funding rates.
- *(Uncertain transcriptions flagged with "(?)": Nirvana, ODM, "DED", "iGen"=EigenLayer.)*
