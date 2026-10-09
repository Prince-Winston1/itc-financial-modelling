# Corporate Financial Model & Analytical Dashboard: ITC Ltd.

[View the PDF summary](itc_financial_model.pdf) | [Download the full Excel model](itc_financial_model.xlsx)

An Excel workspace combining a Discounted Cash Flow (DCF) valuation with a Sum-of-the-Parts (SOTP) valuation of ITC Ltd., cross-checked against each other, plus credit-risk and operational diagnostics. ITC is a diversified conglomerate spanning Cigarettes, FMCG, Agri Business, and Paperboards & Packaging.

---

## Project Motive & Key Findings

**Motive:** A single blended valuation can mis-price a conglomerate by forcing one growth/risk profile onto structurally different businesses. This project builds two independently documented methods, DCF and SOTP, and then reconciles the gap between them.

| Method | Value / Share | Market Price (30.09.2026) | Price ÷ Value |
|---|---|---|---|
| DCF (consolidated cash flows) | ₹248.2 | ₹262.75 | 1.06x (~5.9% premium) |
| SOTP (segment-by-segment) | ₹414.6 | ₹262.75 | 0.63x (~36.6% discount) |

**Reading the gap:** SOTP is ~1.67x the DCF. ITC's Cigarettes segment (mature, ~57% EBITDA margin) and FMCG–Others segment (early-stage, ~10% EBITDA margin, with brand-building and gestation costs per the company's segment note) have very different growth and risk profiles. One blended DCF averages that difference away; the SOTP isolates it. The result is read as a possible conglomerate-discount signal, not as proof: the SOTP leans heavily on a single-peer Cigarette multiple (see limitations).

---

## Sum-of-the-Parts (SOTP) Breakdown

| Segment | Metric Used | Multiple Source | Multiple | Segment EV (₹ Cr) |
|---|---|---|---|---|
| Cigarettes | EBITDA | Godfrey Phillips (16.1x) less 15% discount | 13.7x | 2,91,086.1 |
| FMCG–Others | Total Revenue | Median of 7-peer EV/Sales | 7.6x | 1,84,487.3 |
| Agri Business | External Revenue | AWL Agri Business (EV/Sales) | 0.3x | 3,694.1 |
| Paperboards | EBITDA | Median of 3-peer EV/EBITDA | 8.3x | 9,834.7 |
| Others | n/a | Net segment assets | - | 159.7 |

Sum of segment EVs ₹4,89,261.9 Cr, less unallocated corporate costs capitalised as a perpetuity (₹8,786.7 Cr), bridged to equity with the same cash, investments, debt and share count as the DCF → **₹414.6/share**.

**Methodology choices:**
- **EV/Sales for FMCG–Others and Agri:** both have currently depressed margins (reinvestment; commodity cycle), so applying a mature peer's EV/EBITDA to current EBITDA would understate them.
- **External revenue only for Agri:** excludes inter-segment leaf-tobacco transfers to Cigarettes.
- **15% discount on the Cigarette peer multiple:** Godfrey Phillips is a far smaller company than ITC's cigarette business, and Cigarettes carries excise/tax-policy risk. The discount is an explicit input (`Master Input Center`) and is a judgment call; ITC's own EV/EBITDA is ~10.9x for reference.
- **Peer exclusions:** Andhra Paper (multiple inflated by temporarily depressed earnings); alcohol, bottling and tea/coffee-heavy names (no equivalent business in FMCG–Others).

**Limitations, stated plainly:** Cigarettes (~60% of segment value) rests on a single listed peer, and Agri does too. Each 1x change in the Cigarette multiple moves SOTP value by ~₹17/share:

| Cigarette multiple | SOTP value / share | Discount to market price |
|---|---|---|
| 10.9x (ITC's own EV/EBITDA) | ~₹368 | ~29% |
| 13.7x (base case) | ₹414.6 | ~37% |
| 16.1x (peer multiple, no discount) | ~₹456 | ~42% |

The Agri multiple is immaterial (<₹1/share), and WACC/tax-rate changes move SOTP by under 1%. Across this range the SOTP stays well above the market price, but its size depends on one peer and one judgment-based discount.

---

## DCF Valuation & Sensitivity

Five-year explicit FCFF forecast with growth fading linearly from 13.79% to a 2.50% terminal rate, reinvestment rate fading from 18.2% to 10%, mid-year discounting, WACC ≈ 10.47%. Terminal value is Year-5 FCFF × (1 + g) ÷ (WACC − g), discounted once.

| Terminal Growth \ WACC | 9.47% | 9.97% | 10.47% | 10.97% | 11.47% |
|---|---|---|---|---|---|
| 2.00% | 263.7 | 249.1 | 236.2 | 224.8 | 214.6 |
| 2.50% | 279.4 | 262.7 | **248.2** | 235.4 | 224.0 |
| 3.00% | 297.5 | 278.4 | 261.8 | 247.4 | 234.6 |
| 3.50% | 318.7 | 296.4 | 277.4 | 260.9 | 246.5 |
| 4.00% | 343.7 | 317.5 | 295.4 | 276.4 | 260.0 |

**Things worth knowing:**
- Terminal value is ~69% of DCF enterprise value, so the result is sensitive to WACC and terminal growth (range above: ₹214.6–₹343.7).
- The 13.79% starting growth is the five-year median of ROIC × reinvestment-rate growth. FY25 (ITC Hotels demerger year) inflated that year's figure (21.2%); excluding it, the median is 13.65%, so the result is not sensitive to the treatment.
- Non-operating investments of ₹38,128 Cr (current and non-current) are added back after discounting, since the related income is excluded from EBIT.

---

## Workbook Architecture

- **Valuation & Capital Costs:** `DCF` | `WACC` | `Intrinsic Growth` | `Comps Beta Calculation`
- **Sum-of-the-Parts:** `SOTP - Valuation` (calculation, bridge, methodology note) | `SOTP - Segment Data` (Annual Report Note 30)
- **Diagnostics & Risk:** `VAR` | `Altman's Z Score` | `DuPont Analysis` | `Ratio Analysis` | `Common Size Statements`
- **Inputs & Data:** `Master Input Center` (single source for assumptions, including the valuation-date share price and SOTP multiple discounts) | `Comps Data` (18-peer set, tagged by SOTP segment) | `Historicals FS` | raw data sheets

---

## Operational Diagnostics (Mar-26 Baseline)

- **DuPont ROE:** 25.95% (Net Margin 23.45% × Asset Turnover 86.84% × Equity Multiplier 1.27x, on average total assets)
- **Altman Z-Score:** 13.17x (above the 2.99x "safe" threshold)
- **Value at Risk (₹262.75 base):** Historical Simulation 95% = 2.81% (₹7.39/share); Monte Carlo 95% ≈ 3.1% (≈₹8.3/share; varies slightly with each recalculation). Historical Simulation is the primary measure because it reflects the observed return distribution rather than assuming normality.

---

## Notes for Users

1. Change assumptions in `Master Input Center` only; DCF, WACC, SOTP and VaR all reference it.
2. Debt, cash, investments and shares are linked once and shared by both valuations, so both use the same balance-sheet date (FY2026). WACC uses a market-snapshot debt figure for capital-structure weights, documented on the WACC sheet.
3. Intermediate cells use full precision; displayed values are rounded.

---

## Disclaimers & Sources

- *Educational purpose only; not financial or investment advice. Independent analysis, not affiliated with or endorsed by ITC Ltd.*
- *Segment financials: ITC Ltd. FY2026 Annual Report, Note 30. Historical financials: Screener.in. Market data and peer betas: Yahoo Finance / Screener.in / Bloomberg adjusted-beta weights.*
