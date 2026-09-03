# ITC Ltd. — DCF Valuation & Financial Model

A self-directed 5-year discounted cash flow (DCF) valuation of ITC Ltd., built from public financial data, with supporting diagnostics for capital costs, credit risk, and profitability.

## Key Outputs

| Metric | Value |
|---|---|
| Intrinsic Value per Share | ₹223.60 |
| Market Price (as on 02.09.2026) | ₹268.00 |
| Premium to Intrinsic Value | 1.20x |
| WACC | 10.47% |
| Terminal Growth Rate | 2.50% |
| Start Growth Rate (fading to terminal) | 13.79% |
| DuPont ROE (Mar-26) | 25.95% |
| Altman Z-Score (Mar-26) | 13.17x — well above the 2.99x "safe zone" threshold |

## Model Architecture

- **DCF** — 5-year explicit forecast with a linearly fading growth rate, terminal value via Gordon Growth, and a full equity value bridge
- **WACC / Cost of Capital** — CAPM-based cost of equity, post-tax cost of debt, capital structure anchored to management's long-term target weights
- **Comps Beta Calculation** — both a Blume-adjusted standalone beta and a peer-comps unlevered/relevered beta, for cross-checking
- **Altman's Z-Score** — bankruptcy/solvency risk diagnostic
- **DuPont Analysis** — 3-stage ROE decomposition (margin × turnover × leverage)
- **VAR** — Historical Simulation and Monte Carlo Value-at-Risk on daily returns
- **Ratio Analysis / Common Size Statements** — full 10-year historical ratio and margin trends
- **Master Input Center** — every key assumption (tax rate, beta, WACC inputs, growth rates, reinvestment rate) is centralized here, so the entire model recalculates dynamically off a single input sheet

## Methodology Notes & Judgment Calls

This model was built, then deliberately stress-tested and revised — the notes below document the reasoning behind each key assumption, not just the assumption itself:

1. **Growth fade, not a flat rate:** EBIT growth fades linearly from the historical Start Growth Rate (13.79%) to the Terminal Growth Rate (2.50%) over the 5-year explicit forecast, rather than holding growth flat and then dropping abruptly into the terminal value. This avoids an unrealistic valuation discontinuity and keeps the implied ROIC (Growth ÷ Reinvestment Rate) consistent with the model's own Target Terminal ROIC of 25%.

2. **Investments added back to the equity bridge:** ITC's standalone balance sheet carries ₹38,128 Cr in Investments (₹19,409 Cr non-current per Note 4, ₹19,702 Cr current per Note 9 of the FY26 Annual Report) — verified directly against the filed accounts. Since the income these generate is excluded from EBIT ("Other Income"), they represent non-operating value not otherwise captured by the DCF, and are added back explicitly in the equity value bridge.

3. **Beta — standalone over peer comps:** The model uses ITC's own Blume-adjusted beta (0.90) rather than a peer-comps-derived beta (0.95, based on HUL, Nestlé, Britannia, Godrej Consumer, and Dabur). ITC is a diversified conglomerate spanning cigarettes, FMCG, agribusiness, and paperboards — the available peer set is FMCG-only and not a true business-mix comparable.

4. **Tax rate — statutory over historical median:** 25.17% (India's statutory rate under Section 115BAA: 22% base + surcharge + cess) is used rather than ITC's 5-year historical median effective rate (27.50%), on the basis that effective tax rates tend to converge toward the statutory rate over a multi-year forecast.

5. **VaR methodology:** Historical Simulation VaR is used as the primary measure rather than a Parametric (Normal) VaR, since it reflects the actual observed shape of ITC's return distribution — which may be skewed or fat-tailed — rather than assuming normality.

6. **A known limitation, disclosed rather than hidden:** ITC Hotels Limited was demerged during FY25, and the transfer of PP&E, working capital, and associated earnings occurred mid-year (per the FY26 Annual Report, Note 3A). This means historical growth, ROIC, and reinvestment rate figures spanning FY25 are not on a clean continuing-operations basis. Excluding FY25, the four-year median growth rate is 15.64% versus the 13.79% used in this model — suggesting the demerger year meaningfully depressed the calculated organic growth trend, and that this model's Start Growth Rate is likely conservative relative to a clean continuing-operations view.

## Conclusion

At a market price of ₹268.00 (as on 02.09.2026), ITC Ltd trades at a **1.20x premium** to its DCF-derived intrinsic value of ₹223.60. This reflects a fading growth assumption, a stable long-term-target-weighted cost of capital, and a full accounting of ITC's substantial non-operating investment portfolio — while flagging, rather than smoothing over, the one area (FY25 demerger-affected historicals) where the model's own inputs carry a documented limitation.

## Data Sources

- [Screener.in](https://www.screener.in) — historical financial statements
- Yahoo Finance — market pricing and return data
- ITC Ltd. FY26 Annual Report (Standalone Financial Statements) — used to verify Investments, PP&E, and demerger-related figures directly against primary filings

## Tools

Built entirely in Microsoft Excel, using dynamic formulas and native Excel Data Tables for sensitivity analysis (no external add-ins).
