# Bringing MicroStrategy's STRC Onchain — Dose of Alpha Ep. 11

**Guest:** Kevin Lee — Co-founder & CEO of **Saturn** (Saturn Credit; app at `app.saturn.credit`)

## TL;DR

- **Saturn** brings MicroStrategy's (Strategy's) **STRC / "Stretch"** preferred-equity credit instrument **onchain**, wrapping it into a stablecoin (**USDAT**) and yield-bearing staked token (**SUSDAT**).
- **Stretch = perpetual preferred equity, NOT debt**: no maturity date, cannot be redeemed to par ($100); board can discretionarily pay/skip the dividend each quarter. The trade is underwriting **Strategy's ability + willingness to pay**.
- Current headline yield ~**11.5%**; it is a **market-determined rate** (adjusts via Stretch's price vs. par band), positioned as a potential **onchain benchmark / "beta rate."**
- **Core alpha thesis:** TradFi **misprices Bitcoin as collateral** (S&P treats BTC on Strategy's balance sheet as **negative capital**). The Stretch yield spread persists as long as that mispricing exists.
- **Overcollateralization:** Stretch has **~25% LTV** = **~4x Bitcoin backing** ($4 BTC per $1 Stretch). Sailor publicly stated willingness to **sell BTC if needed** to defend the peg/dividend — viewed by Kevin as positive.
- **Saturn traction:** launched ~1 month ago; **$167M TVL**. Targets holding only **10–20% of the Stretch market**.
- **Stretch market:** grew from **$2.7B → $8.5B in a bear market**; Kevin's original forecast was $10B by end-2027, already nearly hit.
- **Product stack:** Pendle (yield trading), Loop (leveraged Stretch), and **tranching** (senior/junior via "Strata markets").

## Key Topics & Arguments

### Guest Background
- **Kevin Lee** — Co-founder/CEO of **Saturn**.
- Prior: **lead analyst at Artemis** (Web3 analytics firm); led its **DAT** (Digital Asset Treasury) initiative in 2024.
- Before Artemis: **VC fund in Asia**, focused on **AI**; boss was a **STEPN** fan.
- Personally invested in **MicroStrategy in 2023**.
- Entry epiphany (~Sept, during DAT research): onchain yields had collapsed; realized Strategy's digital-credit instruments were "the best credit instrument in TradFi" and should be **bridged onchain**.

### What Stretch (STRC) Is
- **Perpetual preferred equity** issued by Strategy; **not debt**.
- **Two structural risks:**
  - **No maturity date** — cannot redeem to par ($100).
  - **Discretionary dividend** — board can choose to pay or not each quarter.
- Therefore the investment = **underwriting Strategy's ability & willingness to pay**.

### Strategy's Ability to Pay (3 mechanisms)
- **Equity issuance:** issued ~**$16B equity in 2024–2025**; annual interest obligation ~**$1.6B** = only ~**10%** of issuance capacity.
- **Cash buffer:** ~**$2.25B** → covers ~**16 months** of obligations.
- **Bitcoin sales:** ~**800k BTC** on balance sheet; **25% LTV → 4x overcollateralization**.

### The "Willingness to Sell BTC" Debate
- FUD: if Strategy never sells BTC, the 4x overcollateralization metric is **meaningless** ("trust me, bro").
- Sailor (last earnings call): **will sell BTC if needed**, driven mathematically by whatever **maximizes Bitcoin-per-share** (equity sale vs. cash vs. BTC sale).
- Kevin frames this as **positive** — a credible commitment to defend the peg and pay the dividend.
- **Investor focus metrics** when assuming no BTC sale: **MNAV** and **cash buffer**.
- Analogy: locked **Canton** holders who can't move/sell/leverage — illiquid assets can't be "put to work"; BTC willingness-to-sell makes the collateral real.

### The Three Stages of MicroStrategy (Kevin's framing)
- **Stage 1 — Pre-ETF:** equity investors' proxy for Bitcoin access.
- **Stage 2 — Hedge funds/derivatives engine:** liquid option chain + converts to arb BTC/MSTR volatility (ETF lacked options; options later approved end-2024 with limits, limits raised end-2025 — eroding this edge).
- **Stage 3 — Fixed income / digital credit:** sell credit instruments backed by BTC to fixed-income buyers — something an ETF **cannot** do. Viewed as Strategy's "final transformation" and a **platform to build on**.

### Yield Mechanics & Compression
- Stretch yield is **market-determined** by supply/demand around the price band (above ~$101 → rate cut; below ~$99 dynamics).
- If demand rises but Strategy **issues more Stretch to match the curve**, yield **stays constant** (balance-sheet transformation: replace debt with Stretch).
- **Sailor at Miami:** willing to pay **11%**, even **+200 bps more** if it 10x-speeds the digital-credit / BTC ecosystem — cost is trivial vs. capital inflow benefit.
- **Long-run trajectory:** as TradFi learns to price BTC as collateral, Strategy's cost of capital (Stretch yield) **falls** — 11.5% → 9 → 8 → toward **corporate bond rates**; alternatively Strategy could **cut overcollateralization (4x → 2x)** to keep yields high.
- Rebuttal to "11.5% forever is unsustainable": it was **never assumed constant** — it's a market-determined risk premium on Bitcoin, analogous to a **Fed rate** for onchain.
- Most-wanted trade: **borrow against looped Stretch** in DeFi → raises lending/borrow rates → all onchain yields **converge to Stretch**.

### The Alpha (Core Thesis)
- TradFi **does not know how to price Bitcoin as collateral**.
- **S&P report** views BTC on Strategy's balance sheet as **negative capital** — harmed Strategy's credit rating, prompting the cash-buffer raise.
- Spread persists **until TradFi reprices BTC as collateral**. If repriced correctly, MSTR moons but Stretch becomes less viable at high yields.

### Saturn Products & Business Model
- **USDAT:** stablecoin, currently **100% backed by T-bills** (true stablecoin); may back with Stretch as it matures.
- **SUSDAT (staked):** on stake, Saturn **sells T-bills → backs with Stretch**; priced off **vault NAV** (dips if Stretch dips / dividend unpaid).
- **Revenue:** **100% of interest revenue** on the unstaked (USDAT T-bill yield, ~4%) + **~10% of yields** on the staked. Currently passing T-bill yield to stakers to bootstrap ("amplified Stretch exposure").
- **Governance token:** planned, timing **TBD**; incentive program exists.
- **DeFi stack (all three already live):** **Pendle** + **Loop** + **Tranching (Strata markets)**.
- **Strata markets (tranching):**
  - **Senior tranche:** ~**7–8% zero-volatility** yield = Sailor's "digital money" vision; receives risk-premium protection.
  - **Junior tranche:** ~**15–25% yield**, leveraged Stretch exposure; **first-loss capital** protecting the senior; **no formal liquidation** but can be "wiped" (yield varies with coverage ratio).
- **Loop Stretch (distinct product):** borrow against SUSDAT (= Stretch); liquidation only if **Stretch NAV falls**; more certainty than tranching but a 10x loop wipe = total loss.
- **Oracles:** **NAV-based oracle** (always tied to Stretch NAV, not onchain USDAT depeg) → avoids cascading liquidations from onchain price dislocations.

### Risk Management
- **Dynamic Reserve:** monitors Strategy's LTV/leverage in **real time**; auto-sells Stretch for T-bills backing SUSDAT as risk/LTV rises ("real-time risk" advantage of digital credit).
- Watches **SATA** (Strive Management's Stretch-like instrument) as a **leading indicator** — SATA has **50% LTV vs. Stretch's 25%**, yet trades near par, giving comfort on how Stretch behaves if BTC falls further.
- **Strategy's discipline:** targets leveraging only **~25–30% of BTC held**; avoiding ~50% LTV is critical to survive a bear market.
- **Flywheel vs. Athena contrast:** every $1 of Stretch flows into **more BTC** (expands balance-sheet room to issue more) — reflexively bullish; Athena instead adds a short position per dollar.

### Distribution & Go-to-Market
- Access via **app.saturn.credit**; wallet integrations (e.g., **Binance Wallet** announced this week; more planned).
- Chains: launched on **Ethereum**, expanding to **BNB Chain**, then others.
- **Sailor's #1 lesson to Saturn: extreme focus** — "once you find the thing that works, focus and distribute." Saturn's mandate: perfect Pendle/Loop/Tranche and distribute across chains/wallets to reach **$1B+ TVL**, not chase new features.

### Market Outlook (Bullish → Bearish ranking)
- **Most bullish: AI** — but "real AI," **not** AI-in-crypto.
- **2nd: DeFi Mullet** — DeFi as an infrastructure layer with UX/complexity abstracted away (cites **Morpho / Morpho Blue vaults**, e.g., **Coinbase** users lending without knowing it). Easiest path to 10x crypto growth.
- **3rd / most bearish (short-term): RWAs** — bigger long-term sector but slow: heavy standardization, asset selection, compliance, many parties.
- **AI + crypto:** bearish short-term — unproven until AI has massive consumer success stories first; low confidence in the call.

## Entity Extraction

### People
- **Kevin Lee** (guest; Saturn co-founder/CEO; X: **Kevin_LHR88**)
- **Michael Sailor / "Sailor"** (Michael Saylor, MicroStrategy/Strategy)
- Host(s) / co-host referenced as **"Eric"**

### Companies / Organizations
- **Saturn** / **Saturn Credit**
- **MicroStrategy / Strategy (MSTR)**
- **Artemis** (Web3 analytics firm; Kevin's former employer)
- Unnamed **VC fund in Asia** (Kevin's prior employer)
- **S&P** (S&P Global — ratings report on Strategy)
- **Strive Management** (issuer of SATA)
- **Coinbase** (referenced re: Morpho lending UX)
- **Binance** (Binance Wallet integration)
- Accelerator: **"Easy Labs" / "EZ Labs" accelerator** (transcript garbled; Kevin was accepted into it)

### Tokens / Instruments
- **STRC / "Stretch"** (Strategy perpetual preferred equity)
- **USDAT** (Saturn stablecoin, T-bill backed)
- **SUSDAT / SUSD** (Saturn staked, Stretch-backed, NAV-priced)
- **SATA** (Strive Management's Stretch-analog instrument, 50% LTV)
- **MSTR stock** (Strategy equity)
- **Bitcoin (BTC)**
- **Canton** (locked Canton holders referenced)
- **STEPN / "GST"** token (move-to-earn; Kevin's early crypto intrigue)
- **Axie Infinity** (play-to-earn reference)
- **T-bills / U.S. Treasury bills** (USDAT backing)

### Protocols / Platforms / Frameworks
- **Pendle** (yield tokenization; PT tokens)
- **Morpho / Morpho Blue** ("Morflow" in transcript; vaults / lending liquidity)
- **Strata markets** (Saturn's tranching product)
- **Dynamic Reserve** (Saturn's risk mechanism)
- **DeFi Mullet** (narrative/framework)
- **DATs** (Digital Asset Treasuries)
- **RWAs** (Real-World Assets)
- **NAV oracle** (Saturn pricing mechanism)
- Prediction markets (referenced as potential hedge)

### Blockchains
- **Ethereum (ETH)**
- **BNB Chain (BNB)**

### Concepts / Metrics
- **MNAV**, **LTV (25% Stretch / 50% SATA)**, overcollateralization (4x), Bitcoin-per-share, Bitcoin yield charts, coverage ratio, senior/junior tranches, first-loss capital, "beta rate" / benchmark rate, cost of capital

### Events / Places
- **Miami Consensus** conference (Sailor meeting)

### Distribution Channels
- Website **app.saturn.credit**; **X (@Saturn Credit, @Kevin_LHR88)**; **Telegram (TG)** community; **Discord**

## Chronological Flow

1. **Cold open (thesis teaser):** hosts ask if Stretch is an "infinite money glitch"; Kevin previews the two risks (no maturity, discretionary dividend) and the S&P "negative capital" point; Sailor's willingness to pay 11%.
2. **Guest intro:** Kevin's path — VC (AI) → Artemis (DAT lead) → personal MSTR investment (2023) → epiphany to bridge digital credit onchain → founding Saturn.
3. **STEPN tangent:** early crypto intrigue (move-to-earn, Axie), later revealed unsustainable.
4. **Stretch defined:** perpetual preferred equity, not debt; two structural risks; underwriting Strategy's ability/willingness to pay.
5. **Ability-to-pay breakdown:** equity issuance ($16B / $1.6B obligation), $2.25B cash buffer (16 months), 800k BTC at 25% LTV / 4x.
6. **BTC-sale debate:** FUD around never selling; Sailor's mathematical willingness to sell; positive credibility signal; Canton illiquidity analogy.
7. **Three stages of MicroStrategy:** equity proxy → derivatives/hedge-fund engine → fixed-income digital credit ("final transformation," platform).
8. **The leap to Saturn:** Kevin's edge (understands Strategy + DeFi); RWA issuers say "if you can't beat Stretch yield, don't come onchain" → Stretch as onchain benchmark. Accelerator acceptance ("3 guys, 3 pieces of paper") triggered going all-in.
9. **Traction & TAM:** $167M TVL in 1 month; cap at 10–20% of Stretch market; Stretch already at $8.5B vs. $10B-by-2027 forecast.
10. **Yield compression discussion:** market-determined rate; Sailor willing to pay 11% (+200bps) to accelerate ecosystem; long-run compression toward corporate bond rates; "Fed rate for onchain."
11. **The alpha:** TradFi misprices BTC as collateral; S&P negative-capital view; spread persists until repricing.
12. **Saturn products:** USDAT/SUSDAT mechanics, NAV pricing, Pendle yield market, dividend-skip → SUSDAT collapse → PT markets down.
13. **Strata tranching:** senior (7–8%, digital money) vs. junior (15–25%, leveraged, first-loss); long-run goal to sell structured products **back to TradFi**.
14. **Oracle/liquidation mechanics:** NAV-based, no cascading liquidations; loop vs. tranche liquidation differences.
15. **Business model:** T-bill interest + 10% of staked yield; governance token TBD.
16. **Focus philosophy:** Sailor's lesson — perfect Pendle/Loop/Tranche, distribute across chains/wallets (ETH → BNB), reach $1B.
17. **Deeper risk Q&A:** demand > allowed purchase (TradFi lending liquidity ~infinite); flywheel (Stretch → BTC → more issuance); reflexivity in a bull market; no hard cap (Sailor "buys everything") but capped at 25–30% BTC leverage for prudence.
18. **Dynamic Reserve & SATA indicator:** real-time LTV monitoring; SATA (50% LTV, near par) as comfort/leading indicator.
19. **Host wrap on risk:** conclusion — safe absent "massive contagion"; Saturn in "pole position."
20. **Bull/bear ranking:** AI > DeFi Mullet > RWAs; bearish AI+crypto short-term.
21. **Contact/outro:** X, Telegram, Discord, app.saturn.credit.

## Key Takeaways / Conclusions

- **Stretch onchain is a bet on Strategy's creditworthiness**, not a risk-free yield — the two failure modes are dividend suspension and the perpetual/no-par structure.
- **The yield is a market-determined risk premium**, engineered by Strategy issuing supply to match demand; expect gradual compression (toward ~7–9% / corporate-bond territory), **not collapse to ~4%**, and **not a static 11.5%**.
- **The durable alpha is a TradFi mispricing** of Bitcoin-as-collateral (S&P "negative capital"); it erodes only when TradFi reprices BTC — at which point Strategy's cost of capital falls anyway.
- **Willingness to sell BTC is a feature, not a weakness** — it converts a "trust me, bro" collateral claim into a credible, mathematically-driven peg defense (maximize BTC-per-share).
- **Saturn's moat is the TradFi × DeFi intersection** — deepest Strategy/credit understanding among DeFi players, deepest DeFi understanding among Strategy watchers.
- **Product strategy = focus + distribution:** Pendle + Loop + Tranche, abstracted behind clean UX ("DeFi Mullet"), distributed across chains and wallets; endgame is selling structured onchain credit products **back into TradFi**.
- **Risk is actively managed** via NAV oracles (no cascading liquidations), the **Dynamic Reserve** (real-time de-risking into T-bills), and **SATA** as a stress-test proxy.
- **Reflexive upside:** every dollar into Stretch funds more BTC, expanding issuance capacity — most explosive growth expected in a **bull market**, with strong resilience already demonstrated in a **bear market** ($2.7B → $8.5B).
- **Macro view:** bullish real AI, then DeFi Mullet; RWAs slow due to compliance/standardization; bearish AI+crypto near-term.
