# Assessment Tracker — UK Oil Plc Case Study
**Update this throughout the semester**

---

## Key Dates

| Milestone | Date | Status |
|-----------|------|--------|
| Verbal Report presentation | Week of 23–27 Nov 2026 | Book your slot in seminars |
| Verbal Report feedback | 1 Dec 2026 | — |
| Written Report submission | **1.00pm, Monday 14 December 2026** | Confirmed by the official 2026 Assessment Brief (Sem 1 v1). The Week 1a slides said 14 Jan 2027 — ignore that |
| Written Report feedback | 25 Jan 2027 | — |

---

## ✅ Data Conflicts — Resolved by the Official 2026 Assessment Brief

| Item | 2026 Assessment Brief (USE THIS) | Older source | Status |
|------|----------------------------------|--------------|--------|
| Written report deadline | **1pm, 14 Dec 2026** | Week 1a slides: 14 Jan 2027 | Resolved |
| Option 2 (M&A) rights issue — minimum value of the right | **Over £1.00** | Week 3 slides: £1.50 (they also call the target "Euro Refinery", so they come from an older version of the case) | Resolved |
| Unsecured Bond redemption year | **2027** | Week 3 slides: 2025 | Resolved |

## ⚠️ AI Use — Tier Two (from the brief)

GenAI is allowed in an **assistive** role only. If you use it, your slides AND report must include an **AI Acknowledgement** that gives:
- the name and version of the tool
- the publisher/provider
- the web address
- a short description of how you used it
- whether it was free or paid, and which model

If you leave it out, it can be treated as an academic integrity breach.

---

## Rights Issue Model

`Assessment/UK-Oil-Rights-Issue-Model.xlsx` prices the rights issue for Option 1 (£310M) and Option 2 (80% = £260M, 100% = £325M) using the brief's figures. Base case is £1.25: every scenario passes the "over £1.00" test (£2.25 by the lecture definition, about £1.80 by TERP − issue). Book value per share falls from £1.70 to about £1.60. Debt ÷ equity gearing falls from 36.4% to about 31%. The **EUR/GBP rate on the Inputs tab is a placeholder**, so swap in the real-time rate before you use the Munchen figures.

---

## Real-Time Data Log
*Update these regularly — reference them in your report*

| Data Point | Value | Date Checked | Source |
|-----------|-------|-------------|--------|
| Brent Crude Oil Price | | | macrotrends.net / eia.org |
| USD/GBP | | | Bank of England |
| EUR/GBP | | | Bank of England |
| RUB/GBP | | | Bank of England |
| BoE Base Rate | | | bankofengland.co.uk |
| UK CPI (inflation) | | | ONS |
| UK Corporation Tax Rate | | | HMRC |

---

## Analysis Checklist

### Option 1: North Sea Reservoir

**PERT/Project Management**
- [ ] Calculate expected duration for each activity using (O + 4M + P) / 6
- [ ] Identify critical path
- [ ] Flag Activity F as potential bottleneck

**Material Supplier Comparison**
- [ ] Convert Russia (Rub 30,000/ton) to £ using current RUB/GBP
- [ ] Convert USA ($430/ton) to £ using current USD/GBP + add 0.25% collection charges
- [ ] Convert Netherlands (€390/ton) to £ using current EUR/GBP + add 0.75% LC charges
- [ ] Add insurance (3% on C&F) for Russia and USA
- [ ] Add freight (£5M p.a.) — check if this is per supplier or universal
- [ ] Recommend supplier with justification

**Platform Supplier Comparison**
- [ ] Convert Munchen €355M to £ using current EUR/GBP
- [ ] Compare to British £300M
- [ ] Consider 10% advance payment (both suppliers)
- [ ] Recommend with FX risk commentary

**Cash Flow Model (Excel)**
- [ ] Run regression on drilling cost data (10 previous projects)
- [ ] Establish cost equation for 7M barrels
- [ ] Build 25-year cash flow forecast **+ 1 extra year for the final tax payment (tax is paid 1 year in arrears — Week 2)**
- [ ] Apply UK inflation to all £ costs year-on-year
- [ ] Apply tax allowances on CAPEX (Activity J) — find the actual Writing Down Allowance/Annual Investment Allowance rate (Week 2 homework, not yet given)
- [ ] Find the real corporation tax rate for oil extraction companies — NOT the standard rate (Week 2 homework)
- [ ] Shift every tax cash flow one year later than the profit that generates it
- [ ] If any early year is a loss, treat the resulting group tax saving as a cash INFLOW (one year in arrears) — see Week 2 notes
- [ ] Exclude sunk costs (£50M rights + £20M geological = £70M)
- [ ] Include Activity E bidding cost (£10M) as year 0/1 outflow

**Investment Appraisal**
- [ ] Payback period
- [ ] ARR
- [ ] NPV (using WACC as discount rate)
- [ ] IRR
- [ ] Sensitivity analysis on oil price (±15%, ±25%)

**Finance Options**
- [ ] Calculate cost of equity (CAPM/Dividend Growth Model)
- [ ] Calculate cost of debt (after tax)
- [ ] Calculate WACC for 100% equity scenario
- [ ] Calculate WACC for 100% debt scenario
- [ ] Calculate WACC for optimal mix
- [ ] Compare rights issue pricing (£1.00–£1.25 range) vs current market £3.50
- [ ] Evaluate SPE structure
- [ ] **Do NOT list advantages/disadvantages of equity vs debt — give a justified recommendation based on evaluating them (explicitly a zero-mark answer otherwise, Week 3)**
- [ ] Factor in existing gearing (Equity £1,925M vs Debt £700M) — new debt likely prices ABOVE the existing 6–7% given the higher resulting leverage
- [ ] If recommending a $ loan or bond, explicitly address the FX risk it creates (you'd owe $, project earns £) unless it's hedging an existing $ cost

### Option 2: Arabic Oil Supplies M&A

**Valuation**
- [ ] Book value: Net assets $273M → convert to £
- [ ] Market value: 250M × $1.20 → convert to £
- [ ] Earnings-based valuation (P/E multiple)
- [ ] Calculate goodwill (acquisition price minus fair value of net assets)

**Merger Analysis**
- [ ] Model 1-for-1 share exchange: calculate dilution effect on UK Oil shareholders
- [ ] Calculate value of combined entity

**Acquisition Analysis**
- [ ] Cost of acquiring 80% at £1.30/share
- [ ] Cost of acquiring 100% at £1.30/share
- [ ] Calculate premium over current market price ($1.20 vs £1.30)
- [ ] Rights Issue: calculate value of rights (must be > £1.00)
- [ ] Or Debt: calculate impact on gearing

**Synergies & Financial Impact**
- [ ] Vertical integration saving: calculate annual cost saving vs external suppliers
- [ ] Tax saving: calculate annual profit × 0% (vs UK rate)
- [ ] Remittance restriction: calculate annual profit locked in Abu Dhabi (70%)
- [ ] Group Treasury: cost or profit centre? £1.5M management fees
- [ ] Transfer pricing: document the opportunity (complex — note it, don't over-engineer)

**Additional Sales (Activity I replacement)**
- [ ] Build contribution analysis for Arabic Oil (1M units × ($20 − $10) − $1M fixed = ?)
- [ ] Build contribution analysis for UK Oil additional sales

### Real-Time Information (10% of marks)
- [ ] Update data table above at least monthly
- [ ] Note any significant changes to oil price / exchange rates
- [ ] Record new information released during seminars
- [ ] Incorporate into cash flow forecasts when material

### Conclusion
- [ ] Compare NPV/IRR of Option 1 vs Option 2 directly
- [ ] State recommended option (1, 2, or both)
- [ ] State recommended financing method
- [ ] Identify conditions that would change recommendation
- [ ] Quantify the risk with sensitivity analysis

---

## New Information Log (Semester Updates)
*Add entries as new data/quotations emerge in seminars*

| Date | New Information | Impact on Analysis |
|------|----------------|-------------------|
| | | |
| | | |

---

## Verbal Report Prep Checklist

- [ ] 5-minute script drafted and timed
- [ ] PowerPoint slides (max 6) ready
- [ ] Slot booked during seminars
- [ ] Camera tested
- [ ] All Q&A questions in guide reviewed and answered
- [ ] Excel model open and ready for reference
