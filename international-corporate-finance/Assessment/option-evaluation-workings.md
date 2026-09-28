# Option 1 vs Option 2 — Worked Evaluation
**All formulas, substitutions and results — rebuild every one of these yourself in Excel**

---

## ✅ CORRECTED — Week 2's Tax-Timing Rule Now Applied Below

Week 2's lecture (Cash Flow Forecasts & Financial Modelling) states explicitly: **UK corporation tax is paid one year in arrears** — profit earned in Year N is taxed in cash terms in Year N+1. Step 4 below has been **rebuilt** to reflect this (tax shifted one year later, model extended to Year 29 to capture the final tax payment). The corrected NPV is **+£511.2M** (up from the original same-year-tax figure of £481.7M) — deferring a cash outflow by a year makes it cheaper in present-value terms, so the original version was an understatement, not an overstatement.

**Still not incorporated, and flagged as open research:**
- **Tax losses in early years are a cash inflow**, not just "no tax paid" — if Option 1 runs a loss while UK Oil is profitable group-wide (last year's PBT was £500M), the loss reduces the group's tax bill, and that saving belongs in your Option 1 cash flow as an inflow, one year in arrears
- **Capital allowances / Writing Down Allowance** on the £300M+ platform CAPEX will materially reduce early-year tax — not modelled at all below. Research the actual WDA/Annual Investment Allowance rate before submission; it isn't the same as the standard rate and could be a significant NPV improvement you're currently leaving out
- The **actual UK corporation tax rate for oil extraction companies** is not the standard 25% used throughout this file — oil and gas extraction is taxed differently (historically includes a supplementary charge/ring fence regime). Confirm the real rate; it changes every number in Steps 2, 4 and 5

None of this changes the *conclusion* (Option 1 still clears the hurdle comfortably), but the exact NPV, IRR and payback figures below should be treated as directionally right, not final.

---

## ⚠️ Assumptions (PLACEHOLDERS — REPLACE BEFORE SUBMISSION)

| Variable | Placeholder used | Where to get the real figure |
|----------|-----------------|------------------------------|
| Brent crude | $70/bbl | eia.org / macrotrends.net |
| USD/GBP | 1.27 | bankofengland.co.uk |
| EUR/GBP | 1.17 | bankofengland.co.uk |
| RUB/GBP | 108 | bankofengland.co.uk |
| UK Corporation Tax | 25% | HMRC |

Sourcing live data is worth **10% of the mark**. Every number below moves when these rates move.

---

## STEP 1 — Activity K Regression (Production Cost)

**Formula:**
```
b = (nΣxy − Σx·Σy) ÷ (nΣx² − (Σx)²)
a = ȳ − b·x̄
```

**Intermediates** (x = output in 000 barrels, y = cost in £000):
```
n = 10          Σx  = 53,700              Σy  = 1,030,000
x̄ = 5,370       Σxy = 5,592,350,000       Σx² = 292,785,000
ȳ = 103,000
```

**Slope:**
```
b = (10 × 5,592,350,000 − 53,700 × 1,030,000) ÷ (10 × 292,785,000 − 53,700²)
  = (55,923,500,000 − 55,311,000,000) ÷ (2,927,850,000 − 2,883,690,000)
  = 612,500,000 ÷ 44,160,000
  = 13.870
```

**Intercept:**
```
a = 103,000 − (13.870 × 5,370) = 28,518
```

**COST EQUATION: `y = 28,518 + 13.870x`**
**R² = 1 − (60,461,390 ÷ 910,000,000) = 0.9336** (93% of variation explained)

**Applied to 7,000k barrels:**
```
y = 28,518 + (13.870 × 7,000) = 28,518 + 97,090 = £125,608k = £125.6M/year
Cost per barrel = 125,608,000 ÷ 7,000,000 = £17.94
```

> ⚠️ **Flag this yourself:** 7,000 is outside the sample range (3,800–6,100). You are extrapolating ~15% beyond observed data. Acknowledging this limitation earns marks.

---

## STEP 2 — Cost of Capital

### 2a. Cost of Equity (Dividend Growth Model)

**Formula:** `Ke = D₁ ÷ P₀ + g` where `D₁ = D₀(1+g)` and `g = (Dₙ ÷ D₀)^(1/n) − 1`

```
g  = (6.5 ÷ 5.0)^(1/2) − 1 = 1.14018 − 1 = 14.02%
D₁ = 6.5p × 1.14018 = 7.411p
P₀ = £3.50 = 350p

Ke = 7.411 ÷ 350 + 0.14018
   = 0.02117 + 0.14018
   = 16.14%
```

> ⚠️ **Very likely Q&A question:** 14% dividend growth in perpetuity is economically impossible. This inflates Ke and therefore WACC. Cross-check with CAPM `Rf + β(Rm − Rf)` using a real oil-sector beta and current gilt yield, and show a sensitivity on g.

### 2b. Cost of Debt & Preference Shares

**Formula:** `Kd(after tax) = Kd × (1 − t)`, t = 25%

| Instrument | Calculation | Result |
|------------|-------------|--------|
| Unsecured 6% Bond 2027 | 6.00% × 0.75 | **4.50%** |
| Secured Loan (7% fixed) | 7.00% × 0.75 | **5.25%** |
| 6% Preference Shares | not tax deductible | **6.00%** |

### 2c. WACC

**Formula:** `WACC = Σ (MVᵢ ÷ V) × kᵢ`

Market values (ordinary equity at market price, not book):
```
Ordinary    1,000M shares × £3.50  = £3,500M
Preference                          = £  225M
Bond                                = £  500M
Loan                                = £  200M
                                      ────────
V                                   = £4,425M
```

| Component | Weight | Cost | Contribution |
|-----------|--------|------|-------------|
| Ordinary | 0.79096 | 16.14% | 12.762% |
| Preference | 0.05085 | 6.00% | 0.305% |
| Bond | 0.11299 | 4.50% | 0.509% |
| Loan | 0.04520 | 5.25% | 0.237% |
| **WACC** | | | **13.81%** |

Book value weights (V = £2,625M) give WACC = **12.22%**.

> **Key point:** WACC ~13.8% sits *below* the Board's 15% hurdle rate. The 15% benchmark is more conservative than UK Oil's actual cost of capital.

---

## STEP 3 — Activity I Material Supplier Comparison

**Formula:** `Landed cost = (Price ÷ FX × 100,000 tons) + Freight + Insurance + Documentary charges`

### Russia — CFR (insurance NOT included)
```
Goods      Rub 30,000 ÷ 108 = £277.78/ton × 100,000  = £27.78M
Freight                                              = £ 5.00M
C&F value                                            = £32.78M
Insurance  3% × 32.78                                = £ 0.98M
TOTAL                                                = £33.76M
```

### USA — CFR (insurance NOT included)
```
Goods      $430 ÷ 1.27 = £338.58/ton × 100,000       = £33.86M
Freight                                              = £ 5.00M
C&F value                                            = £38.86M
Insurance  3% × 38.86                                = £ 1.17M
Collection 0.25% × 33.86                             = £ 0.08M
TOTAL                                                = £40.11M
```

### Netherlands — CIF (freight AND insurance included)
```
Goods      €390 ÷ 1.17 = £333.33/ton × 100,000       = £33.33M
LC charges 0.75% × 33.33                             = £ 0.25M
TOTAL                                                = £33.58M  ← CHEAPEST
```

**RECOMMEND: NETHERLANDS.** Cheapest on landed cost *and* lowest risk — confirmed irrevocable LC is the most secure payment method available, 3-month settlement is best for working capital, no sanctions exposure. Russia looks £6M cheaper on sticker price but the gap disappears once insurance is added.

---

## STEP 4 — Option 1 NPV, IRR & Payback
### ✅ REBUILT with Week 2's tax-in-arrears rule (this replaces the earlier same-year-tax version)

### 4a. Annual Operating Result

```
Revenue      7,000,000 bbl × $70 ÷ 1.27         = £385.83M
Less  Production (regression, Step 1)           = £125.61M
Less  Materials (Netherlands, Step 3)           = £ 33.58M
Less  Other annual costs                        = £ 20.00M
GROSS PROFIT (pre-tax)                          = £206.64M
Tax @ 25% of Gross Profit                       = £ 51.66M
```

Per Week 2: **tax is paid one year in arrears** — the £206.64M gross profit is received as cash in the year it's earned, but the £51.66M tax bill it generates isn't paid until the *following* year. So these two figures now sit in **different years** of the cash flow, not netted off in the same year as before.

### 4b. Cash Flow Profile & NPV — corrected timing

**Formula:** `NPV = Σ [CFₜ ÷ (1 + r)ᵗ] − I₀`, r = WACC = 13.81%

```
Year 0      Bidding £10M + platform advance 10% (£30M)      = −£40.0M
Year 1–3    Platform balance £270M ÷ 3                      = −£90.0M each
Year 4–28   Gross profit (pre-tax) — 25 years of production = +£206.64M each
Year 5–29   Tax on the PRECEDING year's profit               = −£51.66M each

SUNK COSTS OF £70M EXCLUDED (£50M rights + £20M geological study)
```

Notice the model now runs to **Year 29**, not Year 28 — Year 29 carries only the tax due on Year 28's production, with no offsetting gross profit of its own (the field has stopped producing). This is exactly the "extra final year" Week 2 describes for the Australian mining example, applied here.

**PV of the gross-profit inflows (25-year annuity deferred 3 years):**
```
Annuity factor  AF₂₅ = (1 − 1.1381⁻²⁵) ÷ 0.1381     = 6.9558
Discount factor DF₃  = 1 ÷ 1.1381³                  = 0.6784
PV = 206.64 × 6.9558 × 0.6784                       = £975.5M
```

**PV of the tax outflows (25-year annuity deferred 4 years, since tax starts Year 5):**
```
Discount factor DF₄  = 1 ÷ 1.1381⁴                  = 0.5961
PV = 51.66 × 6.9558 × 0.5961                        = £214.2M
```

**PV of the CAPEX outflows:**
```
= 40 + 90 × (0.8787 + 0.7720 + 0.6784)
= 40 + 209.6                                        = £249.6M
```

**NPV = 975.5 − 214.2 − 249.6 = +£511.7M** → ACCEPT

| Metric | Old (same-year tax) | **Corrected (tax in arrears)** |
|--------|---------------------|--------------------------------|
| NPV @ WACC 13.81% | +£481.7M | **+£511.2M** |
| IRR | 33.3% | **35.4%** |
| Payback | Year 5 | **Year 4.7** |

The corrected NPV is **higher**, not lower — deferring a cash *outflow* by a year makes it cheaper in present-value terms, so the same-year-tax version was understating the project's value. The conclusion doesn't change (Option 1 still clears the 15% hurdle by miles), but this is the number to actually use.

> Not yet included even in this corrected version: (1) the tax saving from any early-year loss offsetting group profit, and (2) Capital Allowances/WDA on the platform CAPEX — both still flagged as open research items below. Both would push NPV higher still.

### 4c. Oil Price Sensitivity (corrected model)

| Brent | Annual gross profit | NPV | Decision |
|-------|---------------------|-----|----------|
| $40 | £41.3M | −£98M | REJECT |
| $45 | £68.8M | +£4M | BREAK-EVEN |
| $50 | £96.4M | +£105M | ACCEPT |
| $60 | £151.5M | +£308M | ACCEPT |
| **$70** | **£206.6M** | **+£511M** | **ACCEPT** |
| $80 | £261.8M | +£714M | ACCEPT |
| $90 | £316.9M | +£917M | ACCEPT |

```
NPV break-even oil price (corrected) = $44.81/bbl
```

Barely moved from the earlier (wrong) $45.31/bbl figure — the tax-timing correction changes the *level* of NPV noticeably (+6%) but the *break-even price* only marginally, since both the gross profit and its tax scale together with the oil price.

---

## STEP 5 — Option 2: Merger vs Acquisition

### 5a. The Merger Trap

**Formula:** `Value transferred = (New shares ÷ Total shares) × Combined value − Value contributed`

```
UK Oil      1,000M shares × £3.50            = £3,500.0M
Arabic Oil    250M shares × $1.20 ÷ 1.27     = £  236.2M
Combined value                               = £3,736.2M

New shares issued to Arabic holders          =    250M
Their stake = 250 ÷ (1,000 + 250)            = 20.0%

Value they RECEIVE   0.20 × £3,736.2M        = £747.2M
Value they CONTRIBUTE                        = £236.2M
VALUE TRANSFERRED AWAY FROM UK OIL           = £511.0M
```

**REJECT THE MERGER.** A 1-for-1 exchange treats a £3.50 share and a £0.94 share as equal, handing £511M of UK Oil shareholder wealth away for a company worth £236M. Existing holders diluted from 100% to 80%.

### 5b. Acquisition — Premium & Goodwill

**Formula:** `Goodwill = Purchase price − Fair value of net assets acquired`

```
Market price per share:  $1.20 ÷ 1.27 = £0.9449
Offer price:             £1.30

Premium = (1.30 ÷ 0.9449) − 1                = 37.6%

Cost at 100%   250M × £1.30                  = £325.0M
Cost at  80%   200M × £1.30                  = £260.0M

Goodwill (100%):
  Purchase price                             = £325.0M
  Fair value of net assets  $273M ÷ 1.27     = £215.0M
  GOODWILL                                   = £110.0M  (34% of price)

Return on standalone earnings:
  Net profit  $9M ÷ 1.27                     = £7.09M
  £7.09M ÷ £325.0M                           = 2.18%   vs WACC 13.81% ✗
```

### 5c. Synergies

**Formula:** `PV of perpetual synergy = Annual synergy ÷ WACC`

```
Tax saving (0% Abu Dhabi vs 25% UK):
  $9M × 25% = $2.25M ÷ 1.27                  = £1.77M/yr

Spare capacity (500,000 unused units):
  (1,500,000 − 1,000,000) × ($20 − $10) = $5.00M ÷ 1.27  = £3.94M/yr

Total annual synergy                         = £5.71M/yr
Capitalised:  5.71 ÷ 0.1381                  = £41.3M

Against merger value transfer:
  £511.0M − £41.3M = shortfall of £469.7M
```

### 5d. Remittance Restriction

```
Only 30% of Abu Dhabi profits may transfer to the UK each year.

Reaches UK shareholders   £7.09M × 0.30      = £2.13M/yr
Trapped in Abu Dhabi      £7.09M × 0.70      = £4.96M/yr
```

Cash UK shareholders cannot access is not fully shareholder value. Either discount the trapped 70% or ring-fence it as Abu Dhabi reinvestment.

---

## STEP 6 — Scorecard

| Test | Option 1 — North Sea | Option 2 — Acquisition | Winner |
|------|---------------------|------------------------|--------|
| Capital required | ~£310M | £325M (100%) / £260M (80%) | — |
| NPV | +£511.2M (tax-in-arrears corrected) | Negative on standalone earnings | **Option 1** |
| Return vs 13.81% WACC | 35.4% IRR | 2.18% | **Option 1** |
| Clears 15% hurdle? | Yes — by over 20 points | No — fails badly | **Option 1** |
| Revenue added p.a. | ~£386M | $80M (~£63M) | **Option 1** |
| Cash actually accessible | 100% | 30% | **Option 1** |
| Payback | Year 4.7 | Beyond 25 years on earnings alone | **Option 1** |
| Principal risk | Oil below $44.81/bbl | £110M goodwill impairment | — |
| Scale vs UK Oil | 7M bbl/yr new production | $9M profit = 1.4% of UK Oil PBT | **Option 1** |

> Note: Option 1's corrected NPV (£511.2M) and the merger's value-transfer figure (£511.0M, Step 5a) are close by coincidence only — they measure completely different things and aren't meant to be compared to each other.

---

## RECOMMENDATION — OPTION 1

Proceed with the **North Sea reservoir**, built by **British Oil Machinery (£300M, no FX risk)**, supplied by the **Netherlands under CIF terms**, financed by a **debt/equity mix** that keeps gearing acceptable while capturing the tax shield on debt. **Reject the merger** outright on the £511M dilution maths.

### The Nuance That Earns Higher Marks

Option 2's real value is not its earnings — it is a **hedge on Option 1**. Building the platform commits UK Oil to buying 100,000 tons of materials annually for 25 years; owning the supplier removes that dependency permanently. But at £325M for a business earning £7.1M it is an extraordinarily expensive hedge — the same FX and supply risk could be managed with forward contracts and a dual-supplier agreement for a fraction of the cost. Treat the acquisition as a **conditional future option**, revisited nearer market value once Option 1's cash flows are established.

### Conditions That Would Change This Recommendation

If Brent falls below **~$44.81/bbl** sustainably, Option 1's NPV turns negative and Option 2's defensive, tax-free earnings — not linked to the oil price — become comparatively attractive. Include this in your conclusion: the brief explicitly asks for the conditions under which your recommendation would change.

---

## Before You Submit — Rebuild Checklist

- [ ] Re-run the regression in Excel (`=SLOPE()` / `=INTERCEPT()` / `=RSQ()`) and confirm 13.870 / 28,518 / 0.9336
- [ ] Replace all four FX rates and the oil price with live sourced figures
- [ ] Re-derive Ke with a defensible growth rate, and cross-check against CAPM
- [ ] Rebuild the 25-year cash flow year by year (not as an annuity shortcut) with inflation applied — use the seminar's one-sheet, formulas-only structure (Assumptions → Formulas → Project Cash Flow → NPV/IRR → Decision)
- [x] ~~Add capital allowances~~ — tax timing (arrears) now corrected above; capital allowances/WDA still outstanding — find the real rate and apply it, this will improve NPV further
- [ ] Model any early-year loss as a group tax-saving cash inflow, one year in arrears (Week 2)
- [ ] Find the real UK corporation tax rate for oil extraction — not the standard 25% used throughout
- [ ] Re-run the sensitivity at your own oil price assumptions
- [ ] Be able to explain every figure above without notes — the verbal report tests exactly this
