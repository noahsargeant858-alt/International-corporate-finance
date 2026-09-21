# Case Study Master File — UK Oil Plc
**International Corporate Finance (6012LBSBW)**
**This file is your single source of truth for the entire assessment**

---

## The Setup

**UK Oil Plc** is an upstream oil exploration and production company operating in the North Sea. The Board wants to grow by investing approximately **£350M** and has two options on the table.

**Your job:** Evaluate both options, recommend one (or neither), recommend how to finance it, and defend that recommendation in a 15-minute verbal report followed by a 3,000-word written report.

**Hurdle rate:** Similar projects have previously made a return of **15%** — this is your benchmark.

---

## UK Oil Plc — Current Financial Structure

### Equity
| Item | £M |
|------|----|
| £1 Ordinary Shares | 1,000 |
| £1 6% Preference Shares | 225 |
| Retained Profits | 700 |
| **Total Equity** | **1,925** |

### Debt
| Item | £M |
|------|----|
| Unsecured 6% Bond 2027 | 500 |
| Secured Loan (Floating Rate 7%) | 200 |
| **Total Debt** | **700** |

**Total Capital Employed: £2,625M**

**Debt/Equity Ratio:** 700/1,925 = **36.4%** debt-to-equity (relatively leveraged but not extreme)

### Dividend History (Ordinary Shares)
| Year | Dividend |
|------|---------|
| 3 years ago | 5% |
| 2 years ago | 6% |
| 1 year ago | 6.5% |
| Growth trend | ~0.75% per year |

**Current Market Price per Ordinary Share: £3.50**

**Last year's PBT: £500M** (expected to continue from existing operations)

---

## OPTION 1: New North Sea Oil Reservoir

### Project Basics
- **Output:** 7,000,000 barrels per year
- **Duration:** 25 years of production
- **Stage now:** Entering Technical & Financial Evaluation (Activities B & C)

### Costs Already Incurred (SUNK COSTS — exclude from NPV)
| Item | Cost |
|------|------|
| Drilling Rights Acquisition | £50M |
| Geological Study (Activity A) | £20M |
| **Total sunk** | **£70M** |

> **Important:** Sunk costs do NOT appear in your NPV calculation. The Board already spent this money — it's gone regardless of which decision they make.

### Project Activity Schedule (PERT/Gantt Analysis Required)

| Activity | Description | Predecessors | Duration |
|----------|-------------|--------------|---------|
| A | Geological Study | — | 12 months (complete) |
| B | Technical Evaluation | A | O=2, M=4, P=10 months |
| C | Financial Evaluation (YOU) | A | 3 months |
| D | Board Consideration | B & C | O=1, M=2, P=3 months |
| E | Bidding Process (£10M) | D | O=1, M=2, P=8 months |
| F | Safety Report ⚠️ | E | O=1, M=4, P=7 months |
| G | Hire & Train Labour | E | O=1, M=2, P=3 months |
| H | Site Preparation | F & G | O=3, M=5, P=10 months |
| I | Delivery of Materials | H | O=1, M=2, P=3 months |
| J | Platform Construction | F & H | O=2, M=4, P=6 months |
| K | Drilling & Production | I & J | O=1, M=3, P=8 months (then ongoing) |
| L | Sales | K | Ongoing for 25 years |

**PERT Formula for expected duration:** `(O + 4M + P) / 6`

> **Critical path note:** Activity F (Safety Report) is flagged as potentially critical — a shortage of safety engineers could delay the whole project. This is a key risk for your risk management section.

### Activity I: Material Suppliers (100,000 tons/year required)

| Supplier | Price | Terms | Payment Method |
|----------|-------|-------|----------------|
| **Russia** | Rub 30,000/ton | CFR Ust Luga | Open Account — settlement 2 months after shipment |
| **USA** | US$ 430/ton | CFR Dover | D/A Bill of Exchange — 1 month after shipment; 0.25% collection charges (buyer pays) |
| **Netherlands** | € 390/ton | CIF Dover | Confirmed Irrevocable Documentary Credit — 3 months after shipment; 0.75% documentary credit charges (buyer pays) |

**Additional costs (all suppliers):**
- Freight/Shipping: £5,000,000 p.a.
- Insurance Premium: 3% based on C&F value (except Netherlands — already CIF, insurance included)

**Price increases:** In line with national inflation rate throughout project life.

> **You must compare these on a like-for-like £ basis using current exchange rates.** Convert all to £ per ton, add documentary charges, then compare total annual cost. Consider also: payment security (Netherlands offers best security via confirmed LC), FX risk (Russia/USA expose UK Oil to Ruble/USD movements), and geopolitical risk (Russia sanctions risk!).

### Activity J: Oil Platform Suppliers

| Supplier | Quote | Notes |
|----------|-------|-------|
| **British Oil Machinery** | £300,000,000 | Sterling — no FX risk |
| **Munchen Machinery (Germany)** | €355,000,000 | Euro — FX risk; advance payment of 10% required |

**Both require:** 10% advance payment — creates a large upfront cash outflow before construction starts.

**CAPEX eligible for tax allowances** — factor these into your cash flow model.

> **You need to reduce the risks of the contract** — consider performance bonds, stage payments, penalty clauses.

### Activity K: Drilling & Production Costs (Regression Analysis Required)

| Project | Output (000 barrels) | Costs (£000) |
|---------|---------------------|-------------|
| 1 | 5,000 | £100,000 |
| 2 | 5,500 | £104,000 |
| 3 | 5,300 | £101,000 |
| 4 | 5,600 | £105,000 |
| 5 | 6,000 | £115,000 |
| 6 | 5,750 | £112,000 |
| 7 | 5,900 | £110,000 |
| 8 | 6,100 | £108,000 |
| 9 | 3,800 | £80,000 |
| 10 | 4,750 | £95,000 |

**Run a regression analysis on this data** to find the cost equation for 7,000,000 barrels/year. The relationship between output and cost needs to be established for your cash flow model.

### Other Annual Costs
- All indirect labour, administration, marketing etc.: **£20,000,000/year**
- Increases in line with UK inflation throughout project life

### Financing Options for Option 1

The Board wants advice on **whether to form an SPE** and whether to finance via:

**A) 100% Equity (Rights Issue)**
- New Rights Issue of Ordinary Shares
- Investment bank fees: **£5M** (regardless of issue size)
- Suggested share price: **£1.00 – £1.25** (bank's recommendation for successful issue)

**B) 100% Debt**

*Sterling Bank Loan (25 years):*
- Base Rate + 2.0% p.a. (variable), OR
- Fixed 7.0% p.a. for 5 years (£1M fee)
- Security/Arrangement Fee: **£3M**

*Currency Loan:*
- Similar rates to sterling
- Security/Arrangement Fee: **£3.25M**

*Bond Issue:*
- S&P rating fee: **£5M**
- Underwriting fee: **£5M** (regardless of size)
- Likely credit rating: **BBB+**

**C) Combination of Equity & Debt**

> **You need to calculate WACC for each financing option** and determine which minimises the cost of capital while maintaining an acceptable capital structure. Consider tax shield on debt, financial distress risk, and the impact on existing shareholders.

---

## OPTION 2: Merger or Acquisition of Arabic Oil Supplies (Abu Dhabi)

### Arabic Oil Supplies — Balance Sheet (31.12.2023)

| | $'000 |
|-|-------|
| **Non-Current Assets** (net of £100M depreciation) | 323,000 |
| **Net Current Assets** (130,000 − 30,000) | 100,000 |
| **Total Assets less Current Liabilities** | **423,000** |
| **Non-Current Liabilities** (6% Bond 2025 + Secured Loan) | (150,000) |
| **Net Assets / Equity** | **273,000** |

**Equity breakdown:**
- Share Capital ($1 Ordinary Shares): $250,000k (250 million shares)
- Share Premium: $14,000k
- Retained Profits: $9,000k

**Current market price per share: $1.20**

**Market capitalisation:** 250M shares × $1.20 = **$300M**

**Book value of equity:** $273M → Market value slight premium to book

### Financials (Year ending 31.12.2023)
| | |
|-|-|
| Sales | $80,000,000 |
| Gross Profit | $20,000,000 (25% gross margin) |
| Net Profit | $9,000,000 (11.25% net margin) |

**P/E Ratio:** Market cap $300M / Net profit $9M = **33.3x** (high — implies growth expectations)

### Merger Option
- Structure: **1 for 1 share exchange**
- UK Oil issues new shares; Arabic Oil shareholders receive UK Oil shares
- No cash changes hands

### Acquisition Option
- Buy 80–100% at **£1.30 per share**
- Finance via Rights Issue or Debt
- Rights Issue viable if value of rights > **£1.00** (per bank guidance)

### Financial Opportunities

| Opportunity | Detail |
|------------|--------|
| **Vertical integration** | Arabic Oil supplies the materials (emulsifiers, corrosion inhibitors) that UK Oil needs — eliminates supplier dependency and margin |
| **Zero tax rate** | Abu Dhabi corporate tax rate is **0%** — massive benefit on Abu Dhabi profits |
| **Group Treasury** | Can establish treasury in UK, Abu Dhabi, or Greece as cost or profit centre. Management fees: £1.5M |
| **Internal transfer pricing** | Set transfer prices between UK and Abu Dhabi entities to optimise group tax position |

### Financial Problems

| Problem | Detail |
|---------|--------|
| **Remittance restriction** | Only **30% of profits** can be transferred back to UK each year — 70% stuck in Abu Dhabi |
| **FX risk** | Arabic Oil earns $USD; UK Oil reports in £GBP — currency translation risk on earnings and balance sheet |
| **Integration risk** | Different legal systems, culture, management styles |

### Additional Sales from Acquisition

| | Arabic Oil Supplies | UK Oil |
|--|--------------------|----|
| Sales Volume | 1,000,000 units | 1,000,000 units |
| Sales Price (per unit) | $20 | Oil Price |
| Variable Costs (per unit) | $10 | Production Costs |
| Fixed Costs p.a. (capacity: 1.5M units) | $1,000,000 | £2,000,000 |

---

## Marking Breakdown — What Earns What

| Section | % |
|---------|---|
| Verbal Report (defence of recommendation) | 20% |
| Option 1: North Sea Reservoir | 30% |
| Option 2: M&A of Arabic Oil Supplies | 30% |
| Real-time new information (emerges during semester) | 10% |
| Conclusion: Recommendation of A, B, or C | 10% |
| **TOTAL** | **100%** |

> **Failure to meet the Board's deadline = 0%.** No extensions. Treat every seminar deadline as if it's the final submission.

### What earns marks in Option 1:
- Accurate forecast cash flow
- Analysis of finance options (equity vs debt vs combo)
- Investment appraisal (NPV, IRR, ARR, Payback)
- Evidence-based risk & return evaluation

### What earns marks in Option 2:
- Business valuation (book value, market value, earnings-based)
- Benefits & problems of merger vs acquisition
- Goodwill calculation
- Finance options for the acquisition
- Clear recommendation: merge OR acquire (not "either could work")

---

## Key Real-Time Data You Need (reference these in your report)

| Data Point | Where to Find | Why It Matters |
|-----------|--------------|----------------|
| Brent crude oil price | www.macrotrends.net or www.eia.org | Revenue forecasts for Option 1 |
| USD/GBP exchange rate | Bank of England / XE.com | Material supplier comparison; Arabic Oil valuation |
| EUR/GBP exchange rate | Bank of England / XE.com | Munchen platform quote; Netherlands materials |
| RUB/GBP exchange rate | Bank of England / XE.com | Russian materials quote |
| UK Bank of England base rate | www.bankofengland.co.uk | Floating rate loan calculations |
| UK inflation rate (CPI) | ONS / www.ons.gov.uk | Inflating costs throughout project life |
| UK Corporation Tax rate | HMRC | Tax calculations on UK profits |
| Abu Dhabi tax rate | 0% | Already given — no research needed |

---

## AI Declaration Template (Required in Your Submission)

You must include this if you use any AI:

```
AI Acknowledgement:
Tool used: [Name and version, e.g. Claude Sonnet 4.6]
Provider: Anthropic
Access point: claude.ai
Use: [Brief description — e.g. "Used to clarify financial concepts and structure revision notes"]
Version: [Free/Pro/paid, and model]
```
