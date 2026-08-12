# Steer & Automation — Dose of Alpha Ep. 4

**Guest:** Derek Barrera (Founder, Steer Protocol) | **Format:** Founder interview on DeFi liquidity management, automation, and on-chain financial primitives.

## TL;DR
- **Steer Protocol** is a leading on-chain **liquidity manager / ALM** (Automated Liquidity Manager): most strategies, most AMM support, most chains. Incubated via **Sushi Swap** (intro by **Joseph Delong**); Derek's prior project was **Volmex** (BTC/ETH volatility indexes).
- **Core thesis:** Uniswap **V3** introduced concentrated liquidity (capital efficiency) but requires active repositioning; ALMs automate optimal liquidity placement using historical data + volatility. **V4** added **hooks**, unlocking **rehypothecation**, permissioned pools, and expressive logic.
- **Rebalancing is the recurring attack surface** across ALMs (Bunny, Fluid, Gamma, others). Steer mitigates this via **off-chain, non-deterministic strategies** (WASM on the Steer Network) and **indirect vault deposits** (cannot be looped/front-run).
- **Options are Derek's biggest predicted unlock** — TradFi options market cited as ~75x NYSE; needed for fixed-rate lending and hedging FX/currency risk. Partnership with **Panoptic** for options vaults (a prior attempt with **Stryke** died when Stryke was hacked the day before launch).
- **Matador** = flagship innovation: a **virtual machine inside the EVM** ("Docker for the EVM") with its own language, enforcing **pre/post-transaction policies** (MEV protection, LTV guards, TVL circuit breakers, on-chain investment mandates, dynamic block-aware intents).
- **Carry-trade vaults** (built with the hosts) live on-chain: borrow cheaply against BTC/RWAs, deploy into higher-yield strategies, capture the spread in a one-click **ERC-4626** vault.
- **Macro view:** Fewer token launches (TGEs), more **RWA / tokenization** (stocks, sovereign debt, FX, gold); ~2–3 new markets/week, mostly wrapped securities not TGEs. **2026** framed as the year of FX and major RWAs coming on-chain.

## Key Topics & Arguments

### Origin & Background
- Derek: professional developer since **2008**; crypto builder since **2017**, interested since **2016** while at **Capital One** (learned banks profit off deposits → cypherpunk motivation).
- **Volmex**: volatility indexes for ETH/BTC (visible on **Bloomberg Terminal**, **TradingView**). Attempted a Polymarket-style YES/NO token pegged to volatility (v1, v2) — did not take off; then designed a perps platform.
- Uniswap **V3 whitepaper** signaled a need for a new liquidity-management sub-industry → founded **Steer**, incubated by **Sushi Swap** (intro via **Joseph Delong**).

### AMM Evolution (V2 → V3 → V4) & the ALM
- **V2:** passive full-range liquidity (0→∞ pricing curve); simple, no decisions.
- **V3:** **concentrated liquidity** → higher capital efficiency but requires manual repositioning as price moves (impractical for most users).
- **ALM (Automated Liquidity Manager):** runs sophisticated strategies on historical data + volatility to keep liquidity **in range**; use cases: spot liquidity depth (reduce slippage/improve volume), treasury management, divest/accumulate assets.
- **Problem solved:** "stagnant liquidity" left un-updated → unhealthy markets for token holders / asset issuers.
- **V4 hooks:** V4 ≈ "V3 with hooks"; enables expressive logic.

### Steer Product Suite (~6 audits completed/underway)
- **Rehypothecation hooks** — for **Algebra**-style DEXes and Uniswap V4. Idea: keep capital in a money market earning yield (start at opportunity cost) until a trade needs it, rather than dead capital sitting in a pool.
- **Permissioned-pool hooks** — for **RWAs / regulated entities**; integrates with **verifiedpools.com** (a **Coinbase** platform; KYC via **Coinbase One**, so counterparties are known). Steer to be first to provide liquidity book-building/management for verified pools.
- **Hybrid collateral settlement hook** (name TBD; not yet audited) — merges **primary (mint/redeem)** and **secondary (swap)** markets for RWAs/stablecoins/collateralized assets. Issuer sets credit lines / rate limits; enables **just-in-time issuance & fulfillment**, solving the sizing/cold-start problem (e.g., fill a $10M swap by minting rather than blowing out price/peg).

### Security & Rebalancing Risk
- Rebalancing exploits are systemic: cited **Bunny** (recently down; Steer had considered acquiring it but lost the race to market), **Fluid** ("runaway train," couldn't turn it off), **Gamma** (~4 hacks, formerly different name), and a ~2020 position-management rebalance exploit.
- Referenced the **Mango Markets** "exploit vs. profitable trading strategy" debate (Avraham "Avi" Eisenberg, now dealing with the FBI).
- **Steer's defenses:** vault deposits **do not go directly into the market** (can't be looped); strategies compiled to **WASM (web assembly)** and run in a **distributed system** → rebalances are **non-deterministic / unpredictable** (vs. fully on-chain, readable strategies). Trade-off: refuses features like direct deposits despite user demand.
- **Steer Network:** IDE for building strategies; **revenue share** with external strategy builders.

### Options as the Big Unlock
- Partnership with **Panoptic** → launching options vaults. Prior attempt with **Stryke** aborted (Stryke hacked the day before launch).
- Argument: options underpin the real economy (e.g., airlines hedge fuel via options so ticket prices resist oil shocks like the Iran war). On-chain options → surfacing hidden financial instruments on-chain.
- Options needed for **deterministic/fixed-rate risk profiles** — current on-chain lending is variable-rate; fixed-rate markets need either large fixed-rate order books or options.

### Rate Discovery & Prediction Markets
- Beyond price discovery, the untold driver is **global rate discovery**. Example: Ukraine home-loan APR ~40% (local treasury rate ~16% on the hryvnia + vig + infrastructure); a global rate + FX hedging (borrow the FX, then lend for a home loan) could massively compress rates → banks should be scared.
- **PT/YT tokens** (Pendle-style): parties accept low fixed rates for optionality on YT, beating TradFi opportunity cost — regulatory arbitrage where TradFi accepts worse rates to meet fixed-rate mandates.
- Discussion of why lending markets fragment (Maker **ETH-A/ETH-B**, **Morpho** separate markets) vs. blended/fixed-rate markets.
- **Prediction markets** as "**fixings**" (TradFi oracle analog); **Polymarket** praised (BTC 5-minute market, elections, sports lines). Line between financial innovation and gambling: "investing" (e.g., war outcomes) vs. gambling; edge exists wherever there's a **passive counterparty**.

### Matador (flagship deep-dive)
- **World-first:** the **Matador Virtual Machine runs inside the EVM** — analogy: "Windows on a Mac" / "**Docker for the EVM**." Write higher-level **Matador** language → compiles to **bytecode** → read by an **on-chain VM interpreter** → executes logic.
- **Purpose:** enforce **pre- and post-transaction policies** — e.g., keep a healthy **LTV** on **Morpho** vaults (pause tx if breached), post-trade enforcement across protocols.
- **Architecture:** effectively **ACLs / a sandbox** on a wallet — turns any wallet into a programmable vault ("you be the vault"), avoiding costly bespoke vault architectures/audits.
- **Fully on-chain:** no keepers, no external servers/parties (unlike competitors who bolt a server next to the miner) → any chain, any wallet.
- **Use cases:** MEV/sandwich protection (checks slippage across full transaction state, not just at swap time); protocol security (**TVL circuit breakers** — reject withdrawals if TVL drops below threshold); encoding **investment mandates / ISDA-style policies** on-chain (vs. PDFs at **Anchorage**, "Fortify" — moving from "trust me" to trustless).
- **Dynamic intents:** unlike **CoW Swap** static intents, Matador exposes on-chain, **block-aware** liquidity offers (e.g., need 1.00 ETH this block, 1.01 next). Turns rebalancing from a cost into a **revenue center** — the vault becomes market **inventory**, earning fee + spread when aggregators route through it. Extends flash-loan-like capability beyond a single block.

### Carry-Trade Vaults (built with the hosts)
- **Carry trade defined:** borrow against an asset, deploy the proceeds at a higher rate, pocket the spread (good vs. bad debt).
- **BTC yield problem:** mining ≠ yield (not staking). Solution: borrow against BTC cheaply (~2–3% via a **CDP**, ~8% on **Avalon**), deploy dollars into looping / **PT-YT** strategies for higher yield; the maintained spread (subject to LTV/liquidation) is effectively BTC yield.
- **Implementation:** prefer **Liquity V2** (set your own borrow rate → lower than money markets); route funds for pass-through fees into stable **V4-type pools**; wrap into a single one-click **ERC-4626 vault** — **live on-chain now**.
- **Expansion:** applies to any asset expected to appreciate vs. USD (gold, silver, stocks, T-bills, BTC); **FX carry trades** flagged as a big theme for the next year+.

### Macro & Market Structure
- **RWA / tokenization** dominates over new tokens: ~2–3 new markets/week, mostly wrapped securities/stocks, **not TGEs/stables**. Hong Kong: energy rights, mineral rights, reinsurance, HELOC lending yield (**Figure**, top-25, recently hit). **2026** = FX currencies + major RWAs on-chain.
- **Meme-coin critique:** ~3,000 tokens/day (one team claimed 80k/month) = "exhaust of trash" that bloats networks and **fractionalizes liquidity and attention**; brand/attention windows keep shrinking ("TikTok-ing ourselves").
- **Anticipated risk:** future crypto crises will dwarf **Terra/Luna** and **FTX** ("scrapes" so far) once more real money and mainstream users are on-chain.
- **Forking without added value** will fail as margins/"funny money" shrink (market ~50% off highs).

## Entity Extraction
- **People:** Derek Barrera (founder, Steer Protocol); Joseph Delong (ex-Sushi Swap); Brian (co-host); Avraham "Avi" Eisenberg (Mango Markets, referenced, unnamed initially); Marc Andreessen ("software is eating the world"); mention of the Ethereum Foundation security researcher.
- **Companies / Protocols / Platforms:** Steer Protocol; Steer Network; Volmex; Sushi Swap; Uniswap (V1/V2/V3/V4); Coinbase; verifiedpools.com; Securitize; Morpho; Maker (MakerDAO); Liquity / Liquity V2; Avalon; Reserve (on-chain ETFs / "DTF"); Panoptic; Stryke; Bunny; Fluid; Gamma; Mango Markets; CoW Swap; Polymarket; Pendle (PT/YT, implied); Figure; Anchorage; "Fortify"; Capital One; YCombinator (YC); ESPN; Bloomberg (Terminal); TradingView; FBI.
- **Tokens / Assets:** Bitcoin (BTC); Ethereum (ETH); Dogecoin (Doge); gold; silver; uranium; diamonds; T-bills; sovereign debt; hryvnia (Ukrainian currency); Japanese yen; RWAs; stablecoins.
- **Blockchains / VMs:** Ethereum; EVM (Ethereum Virtual Machine); Matador / Matador Virtual Machine.
- **Frameworks / Standards / Concepts:** AMM; ALM (Automated Liquidity Manager); Uniswap V4 hooks; rehypothecation; Algebra-style DEXes; permissioned/KYC pools; ERC-4626 vaults; CDP (collateralized debt position); carry trade; PT/YT tokens; LTV; TVL; MEV / sandwich attacks; flash loans; intents; WASM (WebAssembly); bytecode; ISDA; investment mandates; "fixings"/oracles; TGE; rate/price discovery; ETH-A / ETH-B (Maker).
- **Events:** ETH Denver; the Iran war (referenced re: oil/airline hedging); Terra/Luna & FTX collapses.

## Chronological Flow
1. **Intro & ethos** — Derek's cypherpunk motivation; warning that the biggest crypto crises are still ahead (Terra/FTX were "scrapes").
2. **Background** — dev since 2008, crypto since 2016–17 (Capital One); Volmex volatility indexes → Steer, incubated by Sushi Swap via Joseph Delong.
3. **AMM primer** — V2 passive → V3 concentrated liquidity → the need for ALMs (data/volatility-driven auto-positioning).
4. **Product tour** — rehypothecation hooks; permissioned pools + verifiedpools.com/Coinbase KYC; hybrid collateral settlement hook (just-in-time RWA/stablecoin issuance).
5. **Security tangent** — rebalancing exploits (Bunny, Fluid, Gamma, Mango) → Steer's WASM/off-chain non-deterministic strategies + indirect deposits.
6. **ETH Denver anecdote** — helping a young founder growth-hack a crypto payday-loan startup → crypto adoption is early.
7. **Options thesis** — Panoptic partnership; Stryke hack; options run the world (~75x NYSE); needed for fixed-rate lending & FX hedging.
8. **Rate discovery** — global rate compression (Ukraine 40% APR example); PT/YT + fixed-rate mandates; prediction markets/Polymarket as "fixings"; gambling vs. investing.
9. **Matador deep-dive** — VM-in-EVM, policy enforcement, MEV/TVL guards, on-chain mandates, dynamic block-aware intents, rebalancing as revenue.
10. **Carry-trade vaults** — BTC borrow (Liquity V2/Avalon/CDP) → higher-yield deploy → live ERC-4626 vault; expands to FX/RWAs.
11. **Macro** — RWA/tokenization > token launches; meme-coin bloat critique; forking without value fails.
12. **1–5 year outlook** — US crypto legislation exceeded expectations; goal = mainstream ("mom's/grandma's" on-chain yield) = financial freedom / mission success.

## Key Takeaways / Conclusions
- **Automation + safety is Steer's moat:** off-chain non-deterministic (WASM) strategies and indirect deposits specifically counter the industry's chronic rebalancing exploits.
- **V4 hooks + rehypothecation** shift the mental model to "start at opportunity cost, earn above it," keeping capital productive until trades occur.
- **Matador is the standout bet:** a programmable VM-in-EVM turning wallets into policy-enforced vaults — MEV protection, circuit breakers, on-chain compliance mandates, and rebalancing-as-revenue via dynamic, block-aware intents.
- **Options are the next major DeFi unlock** — prerequisite for fixed-rate lending, FX hedging, and bringing hidden TradFi instruments on-chain.
- **The narrative is shifting from token launches to RWA/tokenization** (FX, securities, sovereign debt, commodities), with 2026 as the inflection year; meme-coin proliferation is seen as attention/liquidity-fragmenting noise.
- **Success metric:** mainstream, government-driven adoption delivering on-chain yield to ordinary families ("grandma with a wallet").
