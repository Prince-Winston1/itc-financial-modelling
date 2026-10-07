# Corporate Financial Model & Analytical Dashboard: ITC Ltd.
 
An interactive Microsoft Excel workspace combining a full Discounted Cash Flow (DCF) valuation with a Sum-of-the-Parts (SOTP) valuation, cross-checked against each other, plus core credit-risk and operational diagnostics — built for ITC Ltd., a diversified conglomerate spanning Cigarettes, FMCG, Agri Business, and Paperboards & Packaging.

[Download the PDF here](itc_financial_model.pdf) | [Download the full Excel model](itc_financial_model.xlsx) 
---
 
## Project Motive & Key Findings
 
**Motive:** Most single-method valuations understate the value of diversified conglomerates by forcing one blended growth/risk profile onto structurally different businesses. This project builds two independent, fully audited valuation methods — DCF and SOTP — to test that hypothesis directly on ITC, then reconciles the gap between them rather than picking one and ignoring the other.
 
**DCF (consolidated cash-flow basis):** Intrinsic value of **₹267.41/share** against a market price of ₹262.75 — the stock trades at a **~1.7% discount** (0.98x) to a whole-company DCF view, effectively in line with fair value.
 
**SOTP (segment-by-segment basis):** Intrinsic value of **₹455.6/share** against the same ₹262.75 market price — the stock trades at a **~42.3% discount** when each segment is valued independently against its own industry peers.
 
**Why the two methods disagree — and what that reveals:** ITC's Cigarettes segment (mature, ~57% EBITDA margin) and FMCG–Others segment (early-stage, ~10% EBITDA margin, per the company's own segment disclosure citing ongoing brand-building and gestation costs) have fundamentally different growth and risk profiles. A single consolidated DCF cannot capture that divergence — it averages it away. The SOTP is built specifically to isolate it, and the resulting ~1.7x gap between the two methods is read as a **conglomerate discount signal**: evidence the market may be pricing ITC's individual businesses well below what they'd be worth as standalone, independently-valued entities.
 
---
 
## Sum-of-the-Parts (SOTP) Breakdown
 
| Segment | Metric Used | Multiple Source | Multiple | Segment EV (₹ Cr) |
|---|---|---|---|---|
| Cigarettes | EBITDA | Godfrey Phillips (EV/EBITDA) | 16.1x | 3,42,454.2 |
| FMCG–Others | Total Revenue | Median of 7-peer EV/Sales | 7.6x | 1,84,487.3 |
| Agri Business | External Revenue | AWL Agri Business (EV/Sales) | 0.3x | 3,694.1 |
| Paperboards | EBITDA | Median of 3-peer EV/EBITDA | 8.3x | 9,834.7 |
| Others | — | Net segment assets | — | 159.7 |
 
Less unallocated corporate costs (capitalized as a perpetuity, not a single-year deduction) → **Total Enterprise Value: ₹5,31,843.3 Cr** → bridged to **₹455.6/share** via the same Cash/Investments/Debt figures used in the DCF, ensuring both valuations share a single balance-sheet date.
 
**Methodology choices worth noting:**
- **EV/Sales over EV/EBITDA for FMCG–Others and Agri** — both segments have currently-depressed margins driven by reinvestment/commodity-cycle effects rather than weak underlying economics, per the company's own segment disclosures. Applying a mature peer's EV/EBITDA multiple to a deliberately suppressed EBITDA base would understate these segments.
- **External revenue only for Agri** — excludes inter-segment leaf-tobacco transfers to Cigarettes, since internal transfer volume isn't comparable to an external peer's market-facing revenue.
- **Outlier peer exclusion** — Andhra Paper was excluded from the Paperboards comp set; its elevated multiple reflects temporarily depressed earnings, not a genuine valuation premium.
**Stress-tested limitation, stated plainly:** Cigarettes and Agri Business each rest on a *single* listed peer rather than a median. Sensitivity testing shows this matters a great deal for one and not at all for the other — a ±30% swing in the Cigarette multiple moves the SOTP output by ~₹80–90/share, while an identical swing in the Agri multiple moves it by less than ₹1/share, simply because Cigarettes is ~93x the size of Agri in this model. Even in the most conservative Cigarette-multiple scenario tested, the SOTP still implies a discount to market price — the *direction* of the finding is robust even where the exact magnitude is sensitive to one assumption.
 
---
 
## DCF Valuation & Sensitivity Matrix
 
FCFF is projected over a 5-year explicit forecast with a linearly fading growth rate (13.79% → 2.50% terminal), discounted at a WACC of 10.47% anchored to management's long-term target capital structure.
 
| Terminal Growth \ WACC | 9.47% | 9.97% | 10.47%* | 10.97% | 11.47% |
|---|---|---|---|---|---|
| 2.00% | 277.5 | 267.4 | 258.5 | 250.6 | 243.5 |
| 2.50%* | 289.1 | 277.5 | **267.4*** | 258.5 | 250.6 |
| 3.00% | 302.4 | 289.1 | 277.5 | 267.4 | 258.5 |
| 3.50% | 318.0 | 302.4 | 289.1 | 277.5 | 267.4 |
| 4.00% | 336.4 | 318.0 | 302.4 | 289.1 | 277.5 |
 
Across every WACC/terminal-growth combination tested, output stays within ₹243.5–₹336.4/share — a bounded range.
 
**A documented robustness check:** the starting growth rate (13.79%) is the five-year median of ROIC × reinvestment-rate growth. The `Intrinsic Growth` sheet flags that the FY25 ITC Hotels demerger distorted that year's invested capital and growth calculation (21.2%, an outlier). Excluding FY25, the four-year median is 13.65% — only ~0.14pp below the rate used — so the starting growth assumption is not sensitive to the demerger-affected year.
 
---
 
## Workbook Architecture
 
- **Valuation & Capital Costs:** `DCF` (FCFF projections & dynamic sensitivity matrices) | `WACC` (CAPM calculations) | `Intrinsic Growth` | `Comps Beta Calculation` (peer group regressions)
- **Sum-of-the-Parts:** `SOTP - Valuation` (segment-by-segment calculation, bridge, methodology note) | `SOTP - Segment Data` (raw segment financials, Annual Report Note 30)
- **Diagnostics & Risk:** `VAR` (95% & 99% Value at Risk, Historical Simulation & Monte Carlo) | `Altman's Z Score` (credit health) | `DuPont Analysis` (3-stage ROE breakdown) | `Ratio Analysis`
- **Master Feeds:** `Master Input Center` (global variables, single source of truth for all assumptions) | `Common Size Statements` | `Historicals FS` | `Comps Data` (18-company peer set, tagged by SOTP segment for auditable median calculations)
---
 
## Operational Diagnostics (Mar-26 Baseline)
 
- **DuPont ROE:** 25.95% (Net Margin: 23.45% | Asset Turnover: 86.84% | Equity Multiplier: 1.27x)
- **Altman Z-Score:** 13.17x (Safe "Green Zone" > 2.99x — strong balance sheet, low insolvency risk)
- **Value at Risk:** Historical Simulation 95% CI = 2.81% (₹7.39/share). Historical Simulation VaR is used as the primary measure over Parametric VaR, since it reflects the actual (potentially skewed/fat-tailed) return distribution rather than assuming normality.
---
 
## Quick User Guidelines
 
1. **Input Isolation:** Make all strategic adjustments inside `Master Input Center` only — every downstream sheet (DCF, WACC, SOTP) references it, so a single assumption change flows through consistently.
2. **Data Precision:** Intermediate formulas use unrounded floating-point precision; check the formula bar to reconcile minor rounding differences against displayed values.
3. **Consistency by design:** Debt, Cash, Investments, and Shares Outstanding are linked once (in `DCF`) and referenced identically in `SOTP - Valuation`, ensuring both valuation methods share the same balance-sheet date and never silently diverge on a shared input.
---
 
## Disclaimers & Sources
 
- *Educational purpose only. Does not constitute financial or investment advice.*
- *Segment financials: ITC Ltd. FY2026 Annual Report, Note 30 (Segment Reporting). Historical financials: Screener.in. Market pricing & peer betas: Yahoo Finance / Screener.in.*
- *Independent educational analysis; not affiliated with or endorsed by ITC Ltd.*
