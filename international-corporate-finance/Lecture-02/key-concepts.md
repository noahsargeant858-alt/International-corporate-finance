# Week 2 — Key Concepts & Definitions

---

## Cash Flow Forecasting

### Project Cash Flow (vs Company Cash Flow)
**What it is:** The cash flow forecast you build is for the **project only** — never the whole company. Its only job is to answer: is this project worth doing?

**The three things it must capture:**
1. The cash amounts forecast to be received/paid
2. Cash benefits created by the project (e.g. tax savings — treat as an inflow)
3. WHEN those amounts actually move (not when the sale/purchase happens)

**Example:** sell goods in January on 1 month's credit → the cash arrives in **February**, so that's when it's recorded.

---

## Project Management

### Critical Path
**What it is:** The longest route through a project's task network — it sets the shortest possible total project duration. Any delay to a task *on* this path delays the whole project.

### Float
**Total float:** how long a task can slip without delaying the whole project.
**Free float:** how long a task can slip without delaying the very next task.
Critical path tasks have **zero float** — no room to slip at all.

### PERT (Program Evaluation Review Technique)
**Formula:** `Expected Duration = (O + 4M + P) ÷ 6`
**What it is:** A weighted average of three time estimates (Optimistic, Most Likely, Pessimistic) that gives a single realistic duration for an activity, trusting the "most likely" figure four times more than either extreme.

---

## Probability & Risk

### Normal Distribution
**What it is:** A symmetrical, bell-shaped probability distribution where mean = median = mode, and the shape is fully described by just two numbers: the mean (μ) and the standard deviation (σ).

### Z-Score
**Formula:** `Z = (Actual value − Expected value) ÷ Standard deviation`
**What it is:** How many standard deviations a value sits away from the mean. Convert a Z-score to a probability using a standard statistical table (or Excel's `NORM.S.DIST`).

**Common confidence levels to remember:**
| Z | Confidence |
|---|---|
| ±1 | 68% |
| ±1.645 | 90% |
| ±1.96 | 95% (the default if none is stated) |
| ±2.58 | 99% |

---

## Cash Flow Modelling Rules

### CAPEX Treatment
**The rule:** Treat the **full cost** of a capital asset as a single outflow in **Year 0** — regardless of how it's actually financed.

**Why:** You're testing whether the asset is worth buying at all, independent of the financing method. If you also deduct loan repayments in later years, you've paid for the asset twice in the model.

### The Two Things You Must NOT Include in a Project Cash Flow
1. **Loan repayments** (already captured by the full CAPEX outflow at Year 0)
2. **Interest/cost of finance** (handled separately, through the discount rate — WACC — not as a cash flow line)

### Corporation Tax — Timing
**The rule:** Corporation tax is paid **one year in arrears**. Profit earned in Year N is taxed, but the cash payment happens in Year N+1.

**Practical effect:** your model has **no tax outflow in Year 1**, and needs an **extra final year** to capture the tax due on the project's last year of profit.

### Tax Losses as a Cash Benefit
**The rule:** Tax is calculated on the profit of the **whole company**, not project-by-project. If a project makes a loss while the company is profitable overall, that loss reduces the company's total tax bill — and the resulting **tax saving is a cash inflow for the project**.

**Formula:** `Tax saving = Project loss × Corporation tax rate`

### Capital Allowances / Writing Down Allowance (WDA)
**What it is:** The company version of a personal tax-free allowance — a portion of an eligible asset's cost can be deducted from taxable profit each year, reducing the actual tax paid. Usually calculated on a reducing-balance basis (e.g. 25% of what's left each year).

**Why it matters:** It can dramatically cut the tax a company pays in the early years of a large capital project — a £15,000 allowance on a £60,000 asset cut one worked example's tax bill from £4,000 to £1,000 in Year 1 alone.

---

## Risk Frameworks

### LE PESTE & Co (this module's expanded PESTLE)
| Letter | Factor |
|---|---|
| L | Legal |
| E | Economic |
| P | Political |
| E | Ethical |
| S | Social |
| T | Technological |
| E | Environmental |
| Co | Competition (use Porter's Five Forces here) |

---

## Assessment Terms

| Term | Meaning |
|------|---------|
| **Hurdle Rate** | The minimum acceptable rate of return for a project — usually the WACC |
| **Float (Total/Free)** | Spare time a task can slip without consequence (see above) |
| **Writing Down Allowance (WDA)** | UK tax mechanism reducing taxable profit on eligible capital assets |
| **Arrears** | Payment made after the period it relates to (tax is paid in arrears — one year late) |
