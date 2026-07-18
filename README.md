# Corporate Financial Model & Analytical Dashboard: ITC Ltd.

An interactive Microsoft Excel workspace linking valuation, credit risk, and operational diagnostics for **ITC Ltd.** 

---

## 🎯 Project Motive & Conclusion

*   **Motive:** To build an integrated financial intelligence framework that bridges the gap between forward-looking cash flow valuations (DCF) and core operational health metrics (DuPont, Altman's Z-Score, and Value at Risk).
*   **Final Findings:** The model establishes a conservative intrinsic baseline value of **₹246.60 per share**. Compared to a Current Market Price (CMP) of **₹276.65**, the stock trades at a **1.12x premium**. Operational metrics are stellar, featuring a **25.95% DuPont ROE** driven by organic **23.45% net margins**, and an **Altman Z-Score of 13.17x** indicating zero insolvency risk.
*   **Conclusion:** While trading at a slight premium (~12%) to its conservative DCF base, ITC's top-tier margin safety profile, low leverage, and structural efficiency justify its premium market positioning.

### 💡 Reconciling the Analyst "Undervalued" Consensus
1.  **Post-Demerger Re-rating:** Following the clean spin-off and listing of ITC Hotels Limited, ITC Ltd. is now a leaner, capital-light vehicle. Analysts argue this structural shift warrants pure FMCG multiples (40x–50x P/E) which standard DCF models lag in pricing.
2.  **Conservative Growth Floors:** The baseline model applies a conservative perpetual growth rate ($g_n$) of **2.50%**. Institutional buy ratings frequently bake in growth curves (>3.5%) driven by scaling non-cigarette FMCG verticals.
3.  **Baseline Margin Buffer:** The model anchors tightly to historical margins. Shifting assumptions on the `Master Input Center` by a mere 50–100 bps in Agri/FMCG yields an intrinsic value exceeding market price, aligning perfectly with bullish market consensus.

---

## 📊 Workbook Architecture

*   **Valuation & Capital Costs:** `DCF>` (FCFF projections & dynamic matrices) | `WACC` (CAPM calculations) | `Intrinsic Growth` | `Comps Beta Calculation` (Peer group regressions).
*   **Diagnostics & Risk:** `VAR` (95% & 99% Value at Risk models) | `Altman's Z Score` (Credit health) | `DuPont Analysis` (3-stage ROE breakdown) | `Ratio Analysis`.
*   **Master Feeds:** `Master Input Center` (Global variables) | `Common Size Statements` | `Historicals FS` | `Comps Data`.

---

## 🔍 Core Component Highlights

### 1. DCF Valuation & Sensitivity Matrix
*   **Projections:** Mar-27E FCFF at ₹18,187.20; Mar-31E Terminal FCFF at ₹32,883.32 (Terminal Value: ₹3,00,067.34).

| Terminal Growth \ WACC | 9.47% | 9.97% | 10.47%* | 10.97% | 11.47% |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **2.00%** | 256.35 | 246.60 | 238.00 | 230.37 | 223.53 |
| **2.50%*** | 267.50 | 256.35 | **246.60*** | 238.00 | 230.37 |
| **3.00%** | 280.37 | 267.50 | 256.35 | 246.60 | 238.00 |
| **3.50%** | 295.40 | 280.37 | 267.50 | 256.35 | 246.60 |

### 2. Value at Risk (VAR) Risk Profile
*   **Historical:** 95% Confidence Interval = **2.81%** (₹7.78 per share max expected loss).
*   **Monte Carlo:** 95% Confidence Interval = **3.20%** (₹8.86 drawdown boundary).

### 3. Operational Diagnostics (Mar-26 Baseline)
*   **DuPont ROE:** **25.95%** (Net Margin: 23.45% | Asset Turnover: 0.43x | Equity Multiplier: 2.55x).
*   **Altman Z-Score:** **13.17x** (Safe "Green Zone" > 2.99x, proving bulletproof balance sheet health).

---

## 🛠️ Quick User Guidelines
1.  **Input Isolation:** Make all strategic adjustments inside the `Master Input Center` only.
2.  **Data Precision:** Intermediate formulas use unrounded floating-point precision; check the Excel formula bar to reconcile minimal rounding variations.

---

## 📌 Disclaimers & Sources
*   *Educational Purpose Only. Does not constitute financial or investment advice.*
*   *Historical Data: **Screener.in** | Market Volatility & Equity Pricing: **Yahoo Finance**.*
