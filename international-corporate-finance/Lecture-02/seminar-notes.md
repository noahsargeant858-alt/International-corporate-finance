# Week 2 Seminar — Building the Cash Flow Model in Excel
**International Corporate Finance (6012LBSBW)**

---

## Learning Outcomes (what this seminar is actually assessing)

1. Apply PERT to estimate coursework activity durations (O, M, P estimates)
2. Construct and interpret a Gantt chart showing sequencing, dependencies and timing
3. Prepare an **integrated project cash-flow forecast** for the coursework, using the same principles as the Australian mining example
4. Analyse how project timing and key financial assumptions affect cash flows and the investment decision

This seminar is the hands-on Excel-building session that sits directly behind Week 2's lecture — same case studies (Australian mining + UK Oil), but here you actually build the model step by step rather than just seeing the finished table.

---

## Activity 1 (30 min) — PERT and Gantt for UK Oil Plc

Compute the PERT expected duration for every activity in the case study, then draw the corresponding Gantt chart. This is the same Activities A–L table already in your case study brief — the dashboard's **Activities A–L tab** already has this calculated (expected durations, critical path A→B→D→E→F→H→J→K→L, ≈38.5 months to first production). Nothing new to calculate here; use the seminar time to make sure you can explain *how* each number was derived, not just read it off the dashboard.

---

## Activity 2 (60 min) — Building the Project Cash Flow in Excel

### The 10-row model structure (memorise this build order)

```
1. Initial Capital Investment
2. Production
3. Sales Revenue
4. Operating Costs
5. Tax
6. After-Tax Operating Cash Flow
7. Rehabilitation (or equivalent decommissioning/end-of-life cost)
8. Net Project Cash Flow
9. Discounting
10. NPV & IRR
```

**The golden rule of the whole exercise:**
> Enter each assumption **once**, then use cell references and formulas so the entire model updates automatically.

Read that again — it's the single most important instruction in the seminar. If you change the oil price assumption in one cell and your model doesn't recalculate every downstream number automatically, the model is built wrong, regardless of whether today's numbers happen to look right.

**The five-stage flow the model follows:**
```
ASSUMPTIONS → FORMULAS → PROJECT CASH FLOW → NPV / IRR → DECISION
```

---

## Step 1 — Set Up the One-Sheet Model (Assumptions → Formulas)

| Cash-flow item (AUDm) | Year 0 | Year 1 | Year 2 | … | Year 10 | Year 11 |
|---|---|---|---|---|---|---|
| Initial Capital Investment | (100.0) | – | – | … | – | – |
| Production (m tonnes) | – | 1 | 3 | … | 3 | – |
| Sales price (AUD/tonne) | – | 170 | 170 | … | 170 | – |
| **Sales Revenue** | – | 170 | 510 | … | 510 | – |
| Operating cost (AUD/tonne) | – | 150 | 150 | … | 150 | – |
| **Operating Costs** | – | (150) | (450) | … | (450) | – |
| **Gross Profit** | – | 20 | 60 | … | 60 | – |

**Two formulas, not two numbers to memorise:**
```
Sales Revenue = Production × Sales Price
Gross Profit  = Revenue − Operating Costs
```

**Excel rule stated explicitly in the seminar:** do not type 510 or 60 manually. Calculate them using formulas linked to the assumption cells. If a marker changes your oil price assumption and your "Gross Profit" row doesn't move, you've hardcoded a number that should have been a formula.

---

## Step 2 — Convert Operating Results into Project Cash Flow

| Cash-flow item (AUDm) | Year 0 | Year 1 | Year 2 | … | Year 10 | Year 11 |
|---|---|---|---|---|---|---|
| Gross Profit | – | 20.0 | 60.0 | … | 60.0 | – |
| Tax @ 28% | – | (5.6) | (16.8) | … | (16.8) | – |
| After-Tax Operating Cash Flow | – | 14.4 | 43.2 | … | 43.2 | – |
| Initial Capital Investment | (100.0) | – | – | … | – | – |
| Rehabilitation Cost | – | – | – | … | – | (50.0) |
| **NET PROJECT CASH FLOW** | **(100.0)** | **14.4** | **43.2** | … | **43.2** | **(50.0)** |

```
Net Project Cash Flow = After-Tax Operating Cash Flow − Capital Investment − Rehabilitation Cost
```

**Result:** Year 0 = −100m · Year 1 = +14.4m · Years 2–10 = +43.2m each · Year 11 = −50m

> ⚠️ **Important — this is the teaching (simplified) version.** This seminar's model deducts tax **in the same year** as the profit that generates it (Gross Profit of 20 in Year 1 → Tax of 5.6 in Year 1). The Week 2 **lecture** then goes on to correct this: real UK corporation tax is paid **one year in arrears**. Treat the seminar model as the scaffolding — the structure, formulas and layout are exactly right — but layer the arrears timing on top for your actual coursework submission. Don't confuse "this is how you learn to build the model" with "this is the version to submit."

---

## Step 3 — Discount the Cash Flows and Make the Investment Decision

| | Year 0 | Year 1 | Year 2 | … | Year 10 | Year 11 |
|---|---|---|---|---|---|---|
| Net Project Cash Flow | (100.0) | 14.4 | 43.2 | … | 43.2 | (50.0) |
| Discount Factor @ 7% | 1.000 | 0.935 | 0.873 | … | 0.508 | 0.475 |
| Present Value | (100.0) | 13.46 | 37.72 | … | 21.94 | (23.75) |

**NPV ≈ AUD 152.75m** *(verified by recalculation — exact match)*
**IRR ≈ 32.83%** *(verified by recalculation — exact match)*

**Decision rules, both satisfied:**
- NPV > 0 ✓
- IRR > 7% (the discount rate) ✓

**Case conclusion:** financially acceptable — **but** the seminar deliberately ends on the question: *"what happens when price, cost, timing or other assumptions change?"* That's your cue that sensitivity analysis isn't optional extra credit — it's the explicit next step the module wants from you, and it only works if Step 1's golden rule (formulas, not hardcoded numbers) was followed properly.

---

## Discount Factor Formula (in case you need to build the table by hand)

```
Discount Factor (Year t) = 1 ÷ (1 + r)^t
```
At r = 7%: Year 1 = 1/1.07 = 0.935, Year 2 = 1/1.07² = 0.873, ... Year 10 = 1/1.07¹⁰ = 0.508, Year 11 = 1/1.07¹¹ = 0.475 — all confirmed against the table above.

---

## How This Maps Onto Your UK Oil Coursework

| Seminar model row | UK Oil equivalent |
|---|---|
| Initial Capital Investment | Platform CAPEX (£300M+) + Activity E bidding cost (£10M) |
| Production | 7,000,000 barrels/year (ramp-up profile if any, per your Activity K regression) |
| Sales Revenue | Barrels × Brent crude price (in £, converted from $) |
| Operating Costs | Production cost (regression) + materials (Activity I) + other annual costs |
| Gross Profit | Revenue − all operating costs, before tax |
| Tax | UK oil-sector corporation tax rate × Gross Profit — **shift one year later** per the lecture's arrears rule |
| Rehabilitation Cost | Not explicitly given for UK Oil in the brief — check whether decommissioning costs apply; if none are stated, this row may simply be zero, but flag that you checked rather than silently omitting it |
| Net Project Cash Flow | Same structure — after-tax operating flow, minus CAPEX, minus any end-of-life cost |
| Discount Factor | Use your calculated WACC (~13.8%), not the Board's 15% hurdle, as the actual discount rate — but test against both |

The one-sheet, formulas-only build discipline from this seminar is exactly what a marker will expect to see when you submit your Excel appendix — a model where every number traces back to an assumption cell, not a model where the final NPV is typed in as a static result.
