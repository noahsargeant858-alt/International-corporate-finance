# Week 2 — International Cash Flow Forecasts & Financial Modelling
**International Corporate Finance (6012LBSBW)**

---

## The Big Idea

> *"Finance without Strategy is just Numbers. Strategy without Finance is just a Dream."*

Strategic planning decides the direction of the company. Financial planning is the task of working out how the company will actually afford to get there. This week is entirely about building the **project cash flow forecast** correctly — the single input everything else (NPV, IRR, the investment decision) depends on.

---

## 1. Preparing the Cash Flow Forecast

### What the forecast must capture — three things

1. **The CASH amounts** forecast to be received and paid
2. **CASH BENEFITS** created by the project (a project may save you tax — treat that as an inflow, not just direct revenue/cost)
3. **WHEN** amounts are actually received and paid — not when the sale happens, but when the cash moves. *Example: sell goods in January on 1 month's credit → record as a Cash IN for February.*

### Critical distinction: PROJECT cash flow, not COMPANY cash flow

The forecast you build is **only** for the project. You are not forecasting the whole company's cash position — you are answering one question: **is THIS PROJECT viable?** Every line in the model should be a cash flow that exists *because of* the project, and nothing else.

### Worked example structure (the model shape to copy)

| | Year | 0 | 1 | 2 | 3 | 4 | 5 |
|-|------|---|---|---|---|---|---|
| Investment Required | | −1,700,000 | | | | | |
| Revenue (inflation 1.08) | | | 750,000 | 810,000 | 874,800 | 944,784 | 1,020,367 |
| less Material (inflation 1.05) | | | 125,000 | 131,250 | 137,813 | 144,703 | 151,938 |
| less Labour (inflation 1.10) | | | 150,000 | 165,000 | 181,500 | 199,650 | 219,615 |
| **Net Cash Flow** | | **−1,700,000** | **475,000** | **513,750** | **555,488** | **600,431** | **648,813** |

Notice: **each cost line inflates at its own rate** — material and labour don't move at the same pace as revenue. This is exactly the structure your UK Oil model needs (materials inflate differently from labour, which inflates differently from revenue/oil price).

### Activity 3 — the Australian phosphate mining example (worked in the lecture)

This is the practice problem the lecture uses before turning you loose on the coursework. Data given:
- Initial capital: 100m AUD, Year 0
- Year 1 production: 1m tonnes; Years 2+: 3m tonnes/year
- Project life: 10 years
- Sales price: 170 AUD/tonne; Operating cost: 150 AUD/tonne
- Rehabilitation cost at end of mining (Year 11): 50m AUD
- Tax on gross profit: 28% (capital and rehabilitation costs excluded from the tax calc)

**Why this matters for you:** it's structurally identical to your North Sea reservoir — capex now, ramp-up production, steady-state years, decommissioning cost at the end, tax on operating profit only. Build this Australian example in Excel first as a dry run before touching your own coursework numbers.

---

## 2. Project Management & Network Analysis / Gantt Charts

### Why project management sits inside a finance lecture

Before you can forecast **WHEN** cash moves, you need to know **when each activity happens**. That's a scheduling problem, not a finance problem — hence PERT, critical path, and Gantt charts all show up here.

> **Definition:** Project management is *"the process of setting goals, developing strategies and outlining tasks and schedules to accomplish goals."*

> **Definition — Planning:** *"deciding in advance what is to be done, when, where, how and by whom."* Planning is the primary function of management — it bridges the gap between where you are and where you want to be.

### Critical Path Analysis

- The **critical path** is the longest route through the network — it sets the shortest possible time the whole project can take.
- Any delay to a task **on** the critical path delays the entire project.
- Tasks on the critical path have **zero float**.
- **Total float** — how long a task can slip without delaying the whole project.
- **Free float** — how long a task can slip without delaying the *next* task.
- Critical path analysis does **not** account for resource constraints (e.g. not enough safety engineers to run two tasks at once — that's a separate problem).
- Critical path tasks deserve the highest level of monitoring — they carry the most schedule risk.

This is exactly the calculation you already ran in the dashboard's Activities A–L tab: A→B→D→E→F→H→J→K→L is the critical path, and Activity F (Safety Report) sits on it with the widest O–P spread — precisely the "high monitoring, high risk" case this slide describes.

### PERT (Program Evaluation Review Technique)

**Formula (unchanged from what you already have):**
```
Expected Duration = (O + 4M + P) ÷ 6
```
- O = Optimistic estimate
- M = Most likely estimate
- P = Pessimistic estimate

The lecture's own activity table for **your coursework** matches what's in the case study brief exactly — Activities A through L, same predecessors, same O/M/P estimates. This confirms the PERT table you've already built in the dashboard is the correct one to use.

### Estimating duration — three techniques mentioned
1. **PERT Analysis** (the one you'll actually use)
2. **Probability Analysis** (covered below — the normal distribution / Z-score method)
3. Monte Carlo Simulation (flagged as "save this for later" — not covered yet)

---

## 3. Probability Analysis — Will the Project Finish on Time?

This is new material this week, and it's a real numerical technique, not just theory — expect it in your assessment.

### The normal distribution

Properties of a normal distribution:
1. Values of X run continuously from −∞ to +∞
2. Defined by its mean (μ) and standard deviation (σ)
3. Symmetrical, skew = 0
4. Mean = median = mode
5. Bell-shaped, kurtosis = 3 (excess kurtosis = 0)
6. A combination of normally distributed variables is itself normally distributed

### Common confidence levels (memorise this table)

| Z | Confidence Limit |
|---|---|
| ±1 | 68% |
| ±1.645 | 90% |
| ±1.96 (≈2) | 95% |
| ±2.58 | 99% |
| ±3 | 99.7% |

If a question doesn't state a confidence level, **assume 95%** — that's the convention.

### Worked example — the exact method to reproduce

**Question:** A task needs to finish in under 300 man-days to avoid a £10,000 penalty. On average it takes 240 man-days, with a standard deviation of 30 man-days. What's the probability it's delayed?

**Step 1 — Draw the distribution and mark the area of interest.**
Centre the curve on the mean (240), mark 300 as the threshold, and shade the area to the right of 300 (the "delayed" outcomes).

**Step 2 — Calculate the Z-score.**
```
Z = (Actual − Expected) ÷ Standard Deviation
Z = (300 − 240) ÷ 30 = 2
```

**Step 3 — Look up the Z-value in a statistical table and interpret.**
For Z = 2, the table value is **0.9772** (this is the probability of finishing in 300 days *or fewer*).
```
Probability of delay = 1 − 0.9772 = 0.0228 = 2.28%
```

**Conclusion:** There's a 2.3% chance the task takes more than 300 man-days.

> **Why this matters for your coursework:** Activity F (Safety Report) has the widest O–P spread of any activity in your PERT table. If you're given (or can estimate) a mean and standard deviation for a critical-path activity, this is exactly the method to quantify "what's the chance this activity — and therefore the whole project — is delayed?" It turns a vague risk-management paragraph into a number with a source.

---

## 4. Pointers When Preparing the Cash Flow

Four things the lecture flags explicitly as places students get the model wrong.

### 4.1 — Some amounts require a decision, not just a lookup

You are told to actively decide: which material supplier (Russia, USA or Netherlands — the lecture's own slide says "Norway" but your brief uses Netherlands), and which platform supplier (UK or Germany). These decisions feed numbers into the cash flow — they aren't optional extras, they're **inputs the model needs before it can run**.

### 4.2 — CAPEX and Financing: the rule you must not break

> **Treat the FULL CAPEX cost as an outflow at Time 0 (today).**

The logic: you're asking "does all future income minus costs cover the cost of buying this asset?" — i.e., is it worth buying at all, independent of how you pay for it.

**Do NOT include loan repayments in the project cash flow.** If you include both the full CAPEX at Year 0 *and* the loan repayments in later years, **you have paid for the asset twice.**

**Also ignore the cost of finance (interest)** in this cash flow — that's handled separately, through the discount rate (WACC), not as a line item in the cash flow itself.

**Worked illustration from the lecture:** the Australian 100m AUD investment, imagined as financed by a 10-year loan (10 AUD/year repayment):

| | Yr 0 | Yr 1 | Yr 2 | ... |
|---|---|---|---|---|
| Initial Capital | **−100.00** ✅ CORRECT | | | |
| Loan Repayment | ❌ INCORRECT | ❌ INCORRECT (10.00) | ❌ INCORRECT (10.00) | ... |

The loan repayment row should **never appear** in the project cash flow at all — showing it here is illustrating the mistake, not the fix.

### 4.3 — Cash benefits: taxation

Tax is a genuine cash flow of the project and must be included — but the *timing* is where most models go wrong (see below).

---

## 5. Corporation Tax — The Timing Trap

### Tax is paid the following year, not the same year

The simple Australian teaching example assumes tax is paid in the same year profit is earned (20 × 28% = 5.6). **In the real world, and in your assessment, this is wrong.**

> **Corporation tax is payable 1 year in arrears.** You calculate your profit at the end of the financial year, report it, and pay the tax the *following* year.

**Effect on the cash flow table:** compare the two versions from the lecture —

*Naive (same-year) version:*
| | Yr 1 | Yr 2 | Yr 3 | ... | Yr 10 |
|---|---|---|---|---|---|
| Taxation | 5.60 | 16.80 | 16.80 | ... | 16.80 |

*Correct (1-year-arrears) version:*
| | Yr 1 | Yr 2 | Yr 3 | ... | Yr 10 | Yr 11 |
|---|---|---|---|---|---|---|
| Taxation | — | 5.60 | 16.80 | ... | 16.80 | 16.80 |

Notice: **no tax payment in Year 1**, and the model now runs an **extra year (Year 11)** to pay the final year's tax liability after the project itself has finished.

> ⚠️ **This directly affects your UK Oil model.** If you've built a 25-year cash flow with tax deducted in the same year as profit, you need to shift every tax line one year later, and extend the model by one extra year to capture the final tax payment. This is a common and easy-to-miss error — fix it before you submit.

### Losses reduce tax — and you must think at the WHOLE COMPANY level

> Tax is **not** calculated project-by-project. It's calculated on the profit of the **whole company**.

If your project makes a loss in a given year, but the company is profitable overall from its *other* activities, the project's loss reduces the company's total taxable profit — which means **less tax paid overall**. That saving is a genuine cash benefit **of the project**, and should be treated as a cash inflow.

**Worked example:**
| | £ |
|---|---|
| Profit from other projects | 500 |
| Loss from THIS project | (20) |
| Overall taxable profit | 480 |
| Tax @ 28% | 134.40 |
| Tax the company would have paid without this project (28% × 500) | 140.00 |
| **Tax saving caused by this project** | **£5.60** |

This saving is booked as a cash inflow in **Year 2** (remember: tax effects land one year in arrears). Losses can also be **carried forward** to offset against future tax.

> **This is directly relevant to Option 1's bidding costs and early-stage outflows.** If your North Sea project runs a loss in early years while UK Oil is profitable group-wide (last year's PBT was £500M), those early losses generate a real tax-saving cash inflow — don't leave this out of your model.

---

## 6. Capital Allowances Also Reduce Tax

### The individual analogy (Personal Allowance)

Individuals get a tax-free Personal Allowance (£12,570). Companies get something conceptually similar for **capital investment**: they can offset part of the cost of eligible assets against profit before tax, which reduces the tax bill. Governments do this deliberately, to encourage investment.

### Writing Down Allowance (WDA) — worked mechanics

Example: an eligible asset costs £60,000, with a 25% p.a. Capital Allowance:

| | £ |
|---|---|
| Eligible CAPEX | 60,000 |
| Year 1 allowance (25%) | 15,000 |
| Balance end of Year 1 | 45,000 |
| Year 2 allowance (25% of remaining balance) | 9,000 (lecture shows 36,900 balance — reducing-balance method) |

**Effect on the tax calculation (Year 1):**
| | Without capital allowance | With capital allowance |
|---|---|---|
| Net Profit Before Tax | £20,000 | £20,000 |
| Less Capital Allowance | — | £15,000 |
| Taxable Profit | £20,000 | £5,000 |
| Tax Payable (@20%) | £4,000 | **£1,000** |

The capital allowance shields £15,000 of profit from tax in Year 1 alone — a substantial reduction in the actual cash tax paid, purely because the company invested in an eligible asset.

> ⚠️ **Action item flagged in the lecture, not yet answered:** find out (a) the actual corporation tax rate for oil extraction companies (Option 1) and refineries (Option 2) — it is **not** the standard 20-25% rate — and (b) what Capital Allowance / Annual Investment Allowance / Writing Down Allowance rates apply to the assets you're evaluating (the £300M+ platform CAPEX in particular). This is explicitly homework, not something covered in full in this lecture — "we will come to this later."

---

## 7. Risk — What Could Make the Forecast Wrong

The cash flow you build is **only ever a forecast**, and you're using it to support an investment decision of roughly **£350M**. Things that could differ from the forecast:

**Timing risk:**
- Delays in payment
- Bad debts

**Amount risk:**
- Changes in demand/volume
- Changes in prices
- Changes in exchange rates (where applicable — very relevant given your USD/EUR/RUB exposure)

### The frameworks for structuring this risk discussion

**LE PESTE & Co** (an expanded PESTLE):
- **L**egal
- **E**conomic
- **P**olitical
- **E**thical
- **S**ocial
- **T**echnological
- **E**nvironmental
- **Co**mpetition — analysed using **Porter's Five Forces**

You already have Porter's Five Forces built out in the dashboard's Sector tab — this lecture confirms it's the correct framework to reach for when discussing competitive risk specifically, with PESTLE (or "LE PESTE") covering the wider macro-environment.

---

## 8. Recap — Where This Fits in the Bigger Picture

> **Financial Management (repeated definition):** *"The management of all the processes associated with the efficient acquisition and deployment of both short-term and long-term financial resources, involving financial planning and financial control, with the objective of maximising shareholders' wealth."*

### The four-step sequence (this is the whole module's structure in one list)

1. **Prepare the Cash Flow** — forecast the cash flow over the life of the project *(this week)*
2. **Calculate WACC** — the minimum hurdle rate (example given: 13.4%)
3. **Calculate NPV** at WACC:
   - **+NPV** and IRR > WACC → **Invest**
   - **−NPV** and IRR < WACC → **Don't invest**
4. **Remember NPV's two dependencies**, both of which can move:
   - The cash flow forecast — it's only ever a forecast
   - The discount rate (WACC) — it may change; **IRR tells you how far it could rise before you break even**

### The Board's two decisions (this is the marking scheme, in the lecturer's own words)

**Financing decision** (Sections 4 & 5 of your report):
- Where does the money (capital) come from, to fund the Project or the M&A?
- How much will that finance actually cost?

**Investment decision** (Section 6):
- Is the expected future return **more than the amount invested**? ("I don't want to invest £320M to only earn £250M.")
- Is the expected future return **more than the cost of finance**? ("I don't want the £320M to cost me 5% if I can only make a 4% return.")

This is the clearest one-paragraph statement yet of exactly what the Board wants from your final recommendation — lead with these two comparisons.
