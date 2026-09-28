# Week 2 — Revision Sheet
**Cash Flow Forecasts & Financial Modelling**

---

## The Four-Step Sequence (memorise this order)

1. **Prepare the Cash Flow** — forecast over the project's life
2. **Calculate WACC** — the hurdle rate (e.g. 13.4%)
3. **Calculate NPV** at WACC
   - +NPV & IRR > WACC → **Invest**
   - −NPV & IRR < WACC → **Don't invest**
4. Remember NPV depends on two things that can move: the forecast itself, and the discount rate

---

## The Cash Flow Model — Five Rules That Get Tested

| Rule | One-liner |
|------|-----------|
| 1. Project only | Never model the whole company — only cash flows caused by this project |
| 2. Full CAPEX at Year 0 | Whole asset cost as one outflow, day one, regardless of financing |
| 3. No loan repayments | They're already covered by rule 2 — including them double-counts the asset |
| 4. No interest cost | Handled by the discount rate (WACC), not as a cash flow line |
| 5. Tax lags by 1 year | Profit in Year N → tax paid in Year N+1 → model needs an extra final year |

---

## PERT — Quick Formula Card

```
Expected Duration = (O + 4M + P) ÷ 6
```
O = Optimistic · M = Most Likely · P = Pessimistic

**Critical path** = longest route through the network = shortest possible project time.
**Zero float** = a task on the critical path — any delay here delays everything.

---

## Z-Score Worked Method (copy this exact sequence in an exam)

**Formula:** `Z = (Actual − Expected) ÷ Standard Deviation`

1. Draw the distribution, mark the mean and the threshold value, shade the area you want
2. Calculate Z
3. Look up Z in the standard table → gives P(X ≤ threshold)
4. If you want P(X > threshold): subtract from 1

**Worked example (know this one cold):**
- Task needs < 300 man-days. Mean = 240, SD = 30.
- Z = (300 − 240) / 30 = **2**
- Table value for Z=2 → 0.9772
- P(delay) = 1 − 0.9772 = **2.28%**

**Confidence levels to have memorised:**
| Z | Confidence |
|---|---|
| ±1 | 68% |
| ±1.645 | 90% |
| ±1.96 | 95% ← assume this if not told |
| ±2.58 | 99% |

---

## Tax — Two Traps in One Table

| Trap | Wrong way | Right way |
|------|-----------|-----------|
| **Timing** | Tax deducted same year as profit | Tax paid **1 year later** (arrears) |
| **Losses** | Ignore a loss-making project year | A loss reduces group tax → the **saving is a cash inflow** |

**Tax saving formula:** `Saving = Loss × Tax rate` (booked as inflow, one year in arrears)

**Capital allowance effect (worked example):**
| | No allowance | With allowance |
|---|---|---|
| Profit before tax | £20,000 | £20,000 |
| Less capital allowance | — | £15,000 |
| Taxable profit | £20,000 | £5,000 |
| Tax @ 20% | £4,000 | **£1,000** |

---

## Risk Frameworks — One Line Each

- **LE PESTE & Co**: Legal, Economic, Political, Ethical, Social, Technological, Environmental, Competition (→ Porter's 5 Forces)
- **Porter's Five Forces**: covers the "Competition" factor in depth (already built out in your Sector tab)

---

## Flash Card Q&A

**Q: Why treat the full CAPEX as an outflow at Year 0 rather than spreading loan repayments across the years?**
A: Because you're testing whether the asset is worth buying at all. Including both the full cost AND the loan repayments pays for the asset twice.

**Q: Why is there no tax payment in Year 1 of a correctly built model?**
A: Because UK corporation tax is paid one year in arrears — Year 1's profit generates a tax bill paid in Year 2.

**Q: A project loses £20 in Year 2 but the company makes £500 profit elsewhere. What happens to tax?**
A: Tax is calculated on the whole company's profit (£480 instead of £500), saving 28% × £20 = £5.60 — treated as a cash inflow to the project in Year 3 (one year in arrears).

**Q: What's the difference between total float and free float?**
A: Total float = how long a task can slip without delaying the *whole project*. Free float = how long it can slip without delaying the *next task*.

**Q: A task has mean 240 days, SD 30 days. What's the probability it takes over 270 days?**
A: Z = (270−240)/30 = 1 → table value 0.8413 → P(>270) = 1 − 0.8413 = **15.87%**

**Q: What does IRR tell you that NPV alone doesn't?**
A: How far the discount rate (WACC) could rise before the project's NPV hits zero — i.e., your margin of safety against the cost of capital changing.

---

## Cross-Reference to Your Coursework

- The Activities A–L PERT table in this lecture is **identical** to your case study brief — the dashboard's Activities A–L tab already uses the correct data.
- Activity F (Safety Report) has the widest O–P spread → the natural candidate for a Z-score/probability delay calculation in your risk section.
- ⚠️ **Check your NPV model**: if tax is deducted in the same year as profit, shift it one year later and add a final tax-only year.
- ⚠️ **Research needed** (flagged as homework in the lecture, not yet covered): actual UK corporation tax rate for oil extraction vs refineries, and applicable Capital Allowance / Writing Down Allowance rates for the platform CAPEX.
