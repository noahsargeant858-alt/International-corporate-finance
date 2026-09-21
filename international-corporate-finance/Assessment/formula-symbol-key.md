# Formula Symbol Key
**What every letter in the module's formulas actually means**

---

## Notation That Turns Up Everywhere

| Symbol | Stands for | In plain English |
|--------|-----------|------------------|
| `Σ` | Sigma — "the sum of" | Add up every value in the list. `Σx` means "add all the x values together". |
| `x̄` `ȳ` | "x-bar" — the mean (average) | Add all the values up and divide by how many there are. |
| `₀` | Subscript zero — "now" / "at the start" | `D₀` = dividend just paid. `P₀` = today's share price. `I₀` = money spent at the very beginning. |
| `₁` | Subscript one — "next period" | `D₁` = the dividend expected one year from now. |
| `ₙ` `ᵢ` | Subscript n or i — "the n-th / i-th one" | A placeholder for any item in a list. `βᵢ` = "the beta for risk factor number i". |
| `ᵗ` `²` | Superscript — "to the power of" | `(1+r)ᵗ` = multiply (1+r) by itself t times. `x²` = x × x. |
| `⁻²⁵` | Negative power — "one divided by" | `1.1381⁻²⁵` is the same as 1 ÷ (1.1381 to the power of 25). |

---

## Cost of Capital

| Symbol | Stands for | In plain English |
|--------|-----------|------------------|
| `Ke` | Cost of equity | The % return shareholders demand for owning the shares. Usually your most expensive finance, because shareholders get paid last. |
| `Kd` | Cost of debt | The % interest rate paid to lenders, before any tax relief. |
| `Kd(1−t)` | After-tax cost of debt | Interest is tax-deductible, so debt really costs less than the headline rate. This is the **tax shield** on debt. |
| `Kp` | Cost of preference shares | The fixed % paid to preference shareholders. Unlike interest, it is **not** tax-deductible — so no shield. |
| `D₀` | Dividend just paid | Most recent dividend per share. For UK Oil: 6.5p. |
| `D₁` | Next year's expected dividend | `D₀` grown by one year: `D₁ = D₀ × (1 + g)`. |
| `P₀` | Current market price per share | What one share trades at today. For UK Oil: £3.50. |
| `g` | Dividend growth rate | How fast dividends rise each year, as a decimal (0.14) or % (14%). |
| `t` | Corporation tax rate | 25% in the UK. Used as `(1 − t)`. ⚠️ **Also means "year" in NPV — different t.** |
| `E` | Market value of equity | Shares × current share price. **Not** the book value from the balance sheet. |
| `D` | Market value of debt | Total borrowings — bonds plus loans. |
| `V` | Total value of the firm | `E + D` (+ preference shares). The whole capital structure. The denominator for all the weights. |
| `MVᵢ ÷ V` | The weight of one component | What proportion of total finance this source makes up. All weights add to 1. |
| `Rf` | Risk-free rate | Return on government bonds (UK gilts) — what you'd earn taking no risk. |
| `Rm` | Market return | Expected return on the whole stock market. |
| `Rm − Rf` | Market risk premium | Extra return investors demand for accepting market risk instead of holding gilts. |
| `β` | Beta | How much a share moves vs the market. β = 1 moves in step; β > 1 more volatile; β < 1 calmer. |
| `RPᵢ` | Risk premium for factor i | APM only — extra return for one specific macro risk (inflation, GDP, etc). |
| `WACC` | Weighted Average Cost of Capital | Blended cost of all finance, weighted by how much of each you use. Becomes your discount rate `r` in NPV. |

---

## Investment Appraisal

| Symbol | Stands for | In plain English |
|--------|-----------|------------------|
| `NPV` | Net Present Value | Today's value of all future cash flows, minus what you spend. Positive = adds value. |
| `CFₜ` | Cash flow in year t | Net cash in or out during one particular year. |
| `t` | Time — the year number | Year 0, year 1, year 2… ⚠️ **Different t from the tax rate.** |
| `r` | Discount rate | The rate used to shrink future money back to today's value. Normally your WACC. |
| `I₀` | Initial investment | Cash spent right at the start, in year 0. |
| `1 ÷ (1+r)ᵗ` | Discount factor (DF) | Multiply a future amount by this to find its value today. Gets smaller the further out the year. |
| `AF` | Annuity factor | All the discount factors added together, for a cash flow that's the **same** every year. Saves discounting 25 identical years one at a time. |
| `IRR` | Internal Rate of Return | The discount rate where NPV = exactly zero — the project's own % return. Accept if IRR > WACC. |
| `ARR` | Accounting Rate of Return | Average annual profit ÷ investment, as a %. Ignores time value of money. |

---

## Regression (Activity K)

| Symbol | Stands for | In plain English |
|--------|-----------|------------------|
| `x` | Independent variable | What you know or control. Here: output in 000 barrels. |
| `y` | Dependent variable | What you're predicting. Here: cost in £000. |
| `n` | Number of observations | How many data points — 10 previous projects. |
| `a` | Intercept | Where the line crosses the y-axis — cost when output is zero. Your **fixed cost** element (£28,518k). |
| `b` | Slope (gradient) | How much cost rises per extra unit of output. Your **variable cost** (£13.87 per 1,000 barrels). |
| `Σxy` | Sum of the products | Multiply each x by its **own** y, then add those answers up. |
| `Σx²` | Sum of the squares | Square each x first, then add them all up. |
| `(Σx)²` | Square of the sum | Add **all** the x values first, and only then square the total. ⚠️ **Not the same as `Σx²`.** |
| `R²` | Coefficient of determination | How well the line fits, 0 to 1. R² = 0.93 means output explains 93% of why costs vary. |

---

## Project Scheduling (PERT)

| Symbol | Stands for | In plain English |
|--------|-----------|------------------|
| `O` | Optimistic time | Fastest the activity could realistically finish if all goes right. |
| `M` | Most likely time | The realistic best guess — what usually happens. |
| `P` | Pessimistic time | Slowest it could take if things go wrong. |
| `(O + 4M + P) ÷ 6` | Expected duration | Weighted average trusting "most likely" four times more than best or worst case. |

---

## Mergers & Acquisitions

| Symbol | Stands for | In plain English |
|--------|-----------|------------------|
| `Goodwill` | Premium over net assets | Purchase price − fair value of net assets acquired. What you paid above what the assets are worth, covering brand, customers and expected synergies. |
| `P/E` | Price / Earnings ratio | Share price ÷ earnings per share. Roughly how many years of current profit you're paying for the company. |
| `Synergy ÷ WACC` | Capitalised synergy value | Turns a repeating annual saving into a single lump sum today, assuming it lasts forever. |

---

## The Two Traps

1. **`t` means two different things.** In `Kd(1−t)` it's the **tax rate** (25%). In `CFₜ` and `(1+r)ᵗ` it's the **year number**. Same letter, completely different job — context tells you which.

2. **`Σx²` is not `(Σx)²`.** Square-then-add is not the same as add-then-square. For UK Oil's data: `Σx²` = 292,785,000 but `(Σx)²` = 2,883,690,000. Getting these the wrong way round wrecks the regression.
