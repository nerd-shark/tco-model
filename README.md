# tco-model

**A working five-year TCO calculator for build vs. buy vs. automate decisions. Live formulas, sensitivity analysis, yours to use.**

The build estimate is the deposit. Maintenance is the mortgage. This is a spreadsheet model for the decision every engineering team gets wrong the same way: by pricing the build and forgetting the maintenance.

It's the companion to **"Build vs. Buy vs. Automate: The Real TCO Nobody Models"** (Engineering Economics, Part 5). The article makes the argument. This tool lets you run it against your own numbers.

> **Download:** [`build-buy-automate-tco-calculator.xlsx`](./build-buy-automate-tco-calculator.xlsx)

---

## Why this exists

Across decades of software engineering research, maintenance is 60 to 80% of a system's lifetime cost. Initial development, the part everyone estimates in planning, is the small end. So "we can build this in a quarter" has priced maybe a fifth of the real total.

This calculator forces the other four-fifths onto the page. You enter a yearly maintenance number and a time horizon, and it multiplies the thing most estimates quietly leave out.

---

## What's in the workbook

Three tabs:

### 1. Start Here
A one-screen orientation: how to use it, the 20/80 idea it enforces, what each column means, and the honest limits.

### 2. Calculator
The working model. **Edit only the shaded blue cells.** Everything else is a formula.

Shared assumptions:
- **Time horizon (years)** — how long you'll own the capability.
- **Fully loaded engineer cost ($/year)** — salary + benefits + payroll tax + equipment + overhead. Not base salary. If you only have base, multiply by ~1.4.

Per-option inputs (BUILD, BUY, AUTOMATE):
- Initial build / setup / integration cost
- Annual license / subscription (year 1) and its annual escalation %
- Annual maintenance effort as an FTE (e.g. 0.5 = half an engineer)
- One-time switching / exit cost, and the probability you invoke it

Computed for you:
- License total over the horizon (with compounding escalation)
- Maintenance total (FTE × loaded cost × years)
- Expected switching cost (cost × probability)
- **Five-year total** per option
- **Initial build as % of total** (watch this land near 20% for anything you build)
- **Lowest-cost option**, selected automatically

### 3. Sensitivity
Sweeps the BUILD maintenance assumption from 0.1 to 2.0 FTE and re-runs the model. If the winner is the same down every row, maintenance uncertainty isn't your problem. If it flips, you've found the one assumption worth most of your estimation effort.

---

## How to use it

1. Open `build-buy-automate-tco-calculator.xlsx` in Excel, Google Sheets, LibreOffice Calc, or Numbers.
2. On **Calculator**, set the two shared assumptions (horizon, loaded cost).
3. Fill the blue cells down each option column with your own numbers.
4. Read the five-year totals, the build-share-of-total, and the winner at the bottom.
5. Open **Sensitivity** and check whether the winner holds across maintenance levels. Set BUY and AUTOMATE inputs on the Calculator tab first; the Sensitivity tab mirrors them.

The defaults reproduce the worked example from the article (BUILD ~$750K, BUY ~$703K, AUTOMATE ~$130K, build share ~17%) so you can see it working before you replace the numbers.

---

## The one caveat

The calculator prices **cost**, not value or capability. It will usually say AUTOMATE is cheapest, because automating a narrower capability costs less than building or buying the full one. Cheapest is not the same as enough. The tool tells you what each option costs; you still have to decide whether the cheaper, narrower option actually does the job.

A few more honest limits:
- The maintenance figure drives the whole result and is the hardest to predict. That's what the Sensitivity tab is for.
- Don't build a five-year model to decide on a $50/month tool. Use it for large, durable, hard-to-reverse decisions.
- All default numbers are illustrative, from the article. Replace every blue cell with your own.

---

## The decision framework behind it

The spreadsheet answers "what does each option cost?" The prior question is "what kind of capability is this?"

| Capability | The question that identifies it | Default |
|------------|--------------------------------|---------|
| **Core** | Would a customer ever pay more because you built it yourself? | **Build** |
| **Commodity** | Does a mature market of vendors already solve it? | **Buy** |
| **Glue** | Is it just plumbing between systems you already run? | **Automate** |

Build your competitive edge. Buy the commodity. Automate the glue. Then use the calculator to put five-year numbers on whichever path the framework points to.

---

## Read the full article

**[Build vs. Buy vs. Automate: The Real TCO Nobody Models](#)** — Engineering Economics, Part 5.
*(Replace this with the published article URL.)*

Part of the Engineering Economics series: why good technical decisions are also financial decisions.

---

## License

Released under the [MIT License](./LICENSE). Free to use, copy, and adapt for your own build-vs-buy decisions. Attribution appreciated but not required. No warranty: the numbers are only as good as the assumptions you put in the blue cells.
