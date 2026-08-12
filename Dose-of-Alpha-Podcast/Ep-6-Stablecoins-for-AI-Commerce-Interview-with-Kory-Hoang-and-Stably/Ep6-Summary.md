# Stablecoins for A.I. Commerce — Interview with Kory Hoang & Stably — Dose of Alpha Ep. 6

## TL;DR

- **Guest:** Kory Hoang, CEO & Co-founder of **Stably**, a Seattle-based stablecoin technology/advisory firm (founded 2018); one of the earliest "stablecoin-as-a-service" pioneers.
- **Thesis:** Stablecoins "weren't made for humans; they're made for the machines / the AI." The next wave of stablecoin demand comes from **agentic / machine-driven commerce** (machine-to-consumer, machine-to-business, machine-to-machine).
- **Core new work:** Kory authored a research report proposing a **top-down stablecoin taxonomy** plus a **stablecoin money-supply model (M0–M2)** mapped against traditional fiat monetary aggregates.
- **Central insight:** Fiat money is **endogenous, fractional-reserve** — credit creation *is* money creation (more credit → more money). Stablecoins are **exogenous, full-reserve** — the dynamic **inverts**: credit expansion can *reduce* circulating stablecoin supply (via redemptions) unless secondary-market liquidity absorbs it.
- **Multiplier gap:** Fiat M2/M0 multiplier ≈ **4.2x**; stablecoin M2/M1 multiplier ≈ **1.13x** today — low mainly because stablecoin credit markets are still immature (~$10–15B loans outstanding vs. ~$40–50T global credit).

## Key Topics & Arguments

### Origin story of Stably
- **Background:** Kory was an analyst at **PitchBook** (private equity / VC data); traded crypto since 2013 ("unsuccessfully"), heavily from 2016.
  - Hobby algorithmic trader; aggressively **shorted VIX derivatives** during the low-rate, low-volatility era.
  - Met co-founder/CTO **David** (then an **Amazon** engineer) at a Seattle algorithmic-trading meetup (2016); shared volatility strategies.
- **Pivot to crypto:** In 2017 they applied basic **trend-following** algos to Bitcoin, Ethereum, and ICOs; made money in the 2017 bull run.
  - Realized **USDT was the only stablecoin** available and that there "had to be more than one" issuer — the founding insight.
- **Founding:** Left jobs end of 2017; raised **~$500K seed** in early 2018.
  - Launched first stablecoin **USDS (Stably USD)** by end of 2018; listed on **Bittrex**, then **Binance** by early 2019.
  - Were the **5th USD stablecoin** in the world and **5th listed on Binance**.
  - Raised ~$1M more in 2019.

### The first "stablecoin war" (liquidity war)
- On entering Binance, discovered a **stablecoin war** already underway (USDC, Paxos, TUSD on Binance; Gemini elsewhere).
- **Mechanic of the war:** Well-funded issuers (e.g., Circle, Paxos) sold stablecoins to **market makers / OTC desks at a discount** (e.g., 98–99¢) with **redemption lockups** (larger discount → longer lockup).
  - Locked market makers were forced to **redistribute** — swapping the discounted coin for another stablecoin near 1:1, **realizing the discount as profit** without redeeming.
  - Stably was the **coin being swapped INTO**, then redeemed — explaining constant redemption pressure on their small, underfunded coin.
- **Conclusion:** "A stablecoin war is a liquidity war." Without huge capital to match incentives, competing head-on was untenable.

### Pivot to stablecoin-as-a-service
- **Early 2020** (pre-COVID): delisted from Binance; pivoted from running own brand to **stablecoin infrastructure / stablecoin-as-a-service / advisory**.
  - Claims to be ~2nd SaaS pioneer after **Paxos** (which white-labeled **BUSD** for Binance).
- **Early clients** were emerging blockchain foundations lacking fiat on/off ramps and stablecoin infra: **Stellar, Tezos, VeChain, Harmony, XRP Ledger**.
- Has helped launch **20+ stablecoins** for itself, clients, and partners.

### Why now — the AI / agentic angle
- Bear-market irony: crypto built massive infrastructure hoping for billions of users; **Claude / AI arrival** supplies the "billions/trillions of users."
- AI agents using stablecoins as a native medium of exchange is a "no-brainer" for autonomous, on-chain, transactional settlement — but Kory repeatedly stresses it is **still very early**.
- Prompted his research: before agents scale, the industry needs a rigorous framework for **what kinds of stablecoins exist** and how they behave.

### Proposed stablecoin taxonomy (top-down)
- **Problem with old model:** The legacy "stablecoin trilemma" (fiat-backed / crypto-backed / algorithmic) was a **bottom-up, collateral-first, surface-label** approach — inadequate now that DeFi composability blends flavors.
- **New top-down split — first branch:**
  - **Exogenous** = backed by external assets/reserves.
  - **Endogenous** = backed by something the system creates itself (e.g., **Terra Luna**; also the **US dollar** — "backed by something," not nothing).
- **Subcategories under Exogenous:**
  - **RBS — Reserve-Backed Stablecoin:** static pool of liquid, high-quality reserves (>90% of all stablecoins are fiat-backed).
  - **CDP — Collateralized Debt Position stablecoin:** collateral posted *first*, then coin minted.
  - **SBS — Strategy-Backed Stablecoin:** backed ≥1:1 by a capital pool, but more speculative — requires hedging/risk management.
- **Hybrids:** Elements combine. The **largest decentralized stablecoin, USDS from Sky (formerly Maker)**, is a **RBS + CDP hybrid** (started pure CDP, evolved).
  - Anecdote: **USDS ticker was originally Stably's**, sold to **Sky (~2024)**.
- Newer categories noted: **yield-bearing stablecoins**, **private-credit-backed**, **pegless stablecoins** — each with different redemption/liquidation policies.

### Traditional fiat money creation (context)
- **M0 (monetary base):** physical cash (US Treasury) + central bank reserves (Federal Reserve, "created out of thin air," endogenous; gold-backing ended post-1971 **Nixon shock**). ~$5–6T.
- **Commercial-bank money creation:** banks extend loans → deposit into borrower's account → those become **deposit liabilities (M1)**; the loan is the bank's asset.
  - Modern banks lend **first**, source reserves after (sell/pledge loans to the Fed).
  - **Ex-post collateralization:** loan/money created first, collateral (e.g., house) secures it afterward.
  - **Money multiplier:** re-deposited loans cascade through banks, expanding supply. **Credit creation = money creation.**
- **Aggregates:**
  - **M1** = M0 + deposit liabilities ("narrow money," highly liquid; Venmo/ACH ride on this).
  - **M2** = M1 + term deposits + retail money-market funds ("near money"); ~>$20T total.
  - **M3** = M2 + large institutional deposits, institutional MMFs, Eurodollars; **Fed stopped tracking in 2006** (cost vs. insight).
  - **M4** = rarely used; economists/central bankers focus on M2–M3.

### Stablecoin money supply — the inverted dynamic
- **Key contrast:** Fiat = **endogenous fractional reserve**; stablecoin = **exogenous full reserve** — "yin and yang," dynamics inverted.
- **CDP vs. fiat:** CDP is **ex-ante** collateralization (collateral first, then mint) vs. fiat's ex-post — so CDP is *similar* to fiat but flipped in order.
- **Reserve-backed inversion:** Borrowing a stablecoin → you **sell or redeem it** → redemption pulls the underlying "final settlement liquidity" out → **circulating supply shrinks**.
  - Even if sold not redeemed, whoever holds the "hot potato" eventually redeems — unless they willingly provide liquidity.
- **Aggregate definitions for stablecoins:**
  - **M0** = the backing reserve (e.g., USDC's bank deposits / T-bills / reverse repo).
  - **M1** = circulating token liabilities. For stablecoins **M0 = M1, always 1:1** (no credit creation — only money creation / token issuance).
  - **M2** = M1 + debt from **credit intermediation** (stablecoins deposited into lending protocols like **Aave** and borrowed out). The **M2−M1 delta = outstanding debt**.
- **Credit intermediation ≠ credit creation:** lending protocols need **pre-funded supply** to match lenders/borrowers; banks create credit from nothing.
- **Deposit-liability claim:** A lender's Aave balance still shows a claim even after the token is borrowed/redeemed out of circulation; repayment forces borrowers to **buy back or re-mint** → buy pressure. **Credit contraction re-expands** circulating supply (opposite of fiat).
- **Role of secondary-market liquidity:** Deep liquidity (e.g., **Curve**, Coinbase) lets borrowers **sell instead of redeem**, diverting redemption pressure and sustaining circulating supply.
  - **Curve innovation** noted: concentrated/tight stablecoin liquidity pools vs. **Uniswap V2** full-range liquidity ("we don't need liquidity at 20¢").

### Money multipliers & the "meta money supply"
- **Fiat M2/M0 ≈ 4.2x (4.21x):** each $1 base money creates ~$3.21 additional via debt; increases **progressively** (grows).
- **Stablecoin M2/M1 ≈ 1.13x:** each $1 circulating stablecoin creates ~13¢ in debt/utilized deposit liabilities.
  - Low mainly due to **immature credit markets** (2026): ~$10–15B stablecoin loans outstanding vs. ~$40–50T global credit.
- **Regressive vs. progressive:** A high stablecoin multiplier can arise because circulating supply **shrank** (redemptions) rather than grew — a fundamentally different mechanism.
- **Meta money supply:** The core M0–M2 aggregate understates reality. **DeFi composability** — wrapped tokens, receipt tokens (derivatives), collateralized re-use of USDC/USDT — stacks additional claims/liabilities on top, forming a **"meta M0"** for new receipt tokens.
  - Kory's **next research:** build a dashboard for the full "money view" of the stablecoin ecosystem.
  - **Risk warning:** more composability = more systemic/interconnection risk; a downstream blowup can propagate rapidly upstream.

### RWA / institutional redemption structuring
- Money-market curators for **RWAs** model depositor types as **whales, sharks, minnows**:
  - **Minnows** exit via spot secondary liquidity.
  - **Sharks** exceed secondary depth → need base redemptions (T+8h, T+1, sized).
  - **Whales** lack immediate redemption in the first T+1; traditional markets use rolling **90-day** windows (noted **BlackRock froze redemptions**).
- Redemptions/liquidations without fees beat fat slippage when waiting ~8h is acceptable.
- **Trajectory:** T+1/T+2/T+3 settlement collapses toward **T+0** as tokenized equities and RWAs move on-chain.

### Real-world leverage examples (illustrating debt-based claims)
- Big acquisitions aren't cash: **Lakers ~$10B**, **Elon Musk / Twitter ~$45B** (loans against stock, not checks).
- **Plaid CEO** anecdote: pledged a couple billion in Plaid stock at ~**5% LTV**, bought a **bank for ~$70M**.

### Stably's current business model
- Positioned as a **"fractional stablecoin team" / "stablecoin doctors"** for institutions.
- Serves large institutions wanting **proprietary stablecoin infrastructure/engine** (vs. renting/white-labeling) due to risk-management and compliance needs.
- Provides **battle-tested infra (running since 2018)** plus **strategic advisory/consulting**: go-to-market, liquidity building, peg management, risk management, credit-market integration.
- Network of **regulated stablecoin-as-a-service issuers** can ship a white-label stablecoin in **~1–2 weeks** at low cost.

## Entity Extraction

- **People:** Kory Hoang (CEO/Co-founder, Stably); David (Co-founder/CTO); Bryan (host); Elon Musk; Plaid CEO (unnamed); Richard Nixon (via "Nixon shock").
- **Companies / Institutions:** Stably; PitchBook; Amazon; Circle; Tether; Paxos; Gemini; Sky (formerly Maker / MakerDAO); BlackRock; Plaid; Coinbase; Los Angeles Lakers; Twitter; US Treasury; Federal Reserve (the Fed).
- **Exchanges:** Binance; Bittrex; OKEx; Curve; Uniswap (V2).
- **Protocols / DeFi:** Aave; Curve; Sky Protocol; Maker.
- **Tokens / Stablecoins:** USDS (Stably USD; ticker later sold to Sky's USDS); USDT (Tether); USDC; TUSD (TrueUSD); BUSD (Binance USD); Terra Luna (endogenous example).
- **Blockchains:** Bitcoin; Ethereum; Stellar; Tezos; VeChain; Harmony; XRP Ledger.
- **AI / Tools:** Claude (cited as the AI driving new user demand).
- **Instruments / Concepts:** VIX derivatives; ICOs; T-bills; reverse repo; Eurodollars; money-market funds; CDP (collateralized debt position); RWAs (real-world assets); receipt tokens.
- **Frameworks / Models:** Stablecoin taxonomy & money-supply report (Kory's paper); stablecoin trilemma (legacy: fiat/crypto/algorithmic); top-down taxonomy — Exogenous vs. Endogenous; RBS / CDP / SBS categories; monetary aggregates M0–M4; "meta money supply"; money multiplier.
- **Firm / product:** stably.io (website); kory@stably.io (contact).

## Chronological Flow

1. **Guest intro:** Stably = Seattle stablecoin tech/advisory firm since 2018; 5th USD stablecoin; 5th on Binance; 20+ stablecoins launched.
2. **Origin (2013–2018):** Crypto trading since 2013; PitchBook analyst + VIX-short algo trader; met David (Amazon) in 2016; applied trend-following algos to BTC/ETH/ICOs in 2017; recognized USDT-only gap → left jobs, raised $500K seed, launched USDS.
3. **Binance & the first stablecoin war (2019):** Discovered discount-to-market-maker + lockup scheme (Circle/Paxos); realized "stablecoin war = liquidity war"; Stably was the swap-into/redeem target.
4. **Pivot (early 2020):** Delisted from Binance; became a stablecoin-as-a-service pioneer (after Paxos/BUSD); served Stellar, Tezos, VeChain, Harmony, XRP Ledger.
5. **"Why now":** AI/agentic economy reframes demand; "stablecoins made for machines"; motivates the research paper. Notes evolution to yield-bearing, private-credit, and pegless stablecoins.
6. **Taxonomy:** Critiques bottom-up trilemma; proposes top-down Exogenous vs. Endogenous → RBS/CDP/SBS → hybrids (USDS/Sky as flagship hybrid; USDS ticker origin story).
7. **Fiat money mechanics:** M0 base → bank credit creation → M1/M2; ex-post collateralization; money multiplier; M3 discontinued 2006; M4 rarely used.
8. **Stablecoin money supply:** Endogenous vs. exogenous inversion; CDP = ex-ante; borrowing → redemption → supply contraction; M0=M1 1:1; M2 = credit intermediation (Aave); repayment → re-mint buy pressure; credit contraction re-expands supply.
9. **Liquidity & multipliers:** Secondary liquidity (Curve vs. Uniswap V2) diverts redemptions; RWA whale/shark/minnow redemption structuring; T+X → T+0 future; fiat 4.2x (progressive) vs. stablecoin 1.13x (regressive); "meta money supply" from composability + systemic-risk caveat.
10. **Real-world leverage tangent:** Lakers, Musk/Twitter, Plaid CEO buying a bank — all debt-against-stock claims.
11. **Business model & close:** Stably as fractional stablecoin team / "doctors"; proprietary infra + advisory; ~1–2 week white-label issuance; contact via stably.io / kory@stably.io.

## Key Takeaways / Conclusions

- **Stablecoins are infrastructure for machine commerce**, not just human payments — the AI/agentic economy is the demand catalyst crypto's infrastructure was waiting for (though "still very early").
- **A better classification is needed:** top-down taxonomy (Exogenous/Endogenous → RBS/CDP/SBS + hybrids) beats the legacy trilemma for a composable, multi-flavor ecosystem.
- **Fiat and stablecoin monetary dynamics are inverse:** fiat credit expansion creates money; reserve-backed stablecoin credit expansion contracts circulating supply (via redemptions) absent secondary-market liquidity.
- **Stablecoins have no true credit creation** — only 1:1 money creation (M0=M1) plus **credit intermediation** (M2) that requires pre-funded supply.
- **The 1.13x stablecoin multiplier is low chiefly due to market immaturity**; it will rise as credit markets mature, but "regressively" (via supply contraction) rather than "progressively," and the true figure is far higher once **DeFi composability / meta money supply** is counted — carrying elevated systemic risk.
- **Deep, tightly-designed secondary liquidity** (Curve-style) is essential to sustain circulating supply and enable practical redemption structuring for whales/sharks/minnows; settlement is trending toward **T+0**.
- **Stably's value proposition:** a proven (since-2018) infrastructure + advisory partner acting as a "fractional stablecoin team," able to stand up regulated white-label stablecoins in ~1–2 weeks and guide liquidity, peg, risk, and credit-market integration.
