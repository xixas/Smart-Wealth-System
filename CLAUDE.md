# Smart Wealth System - Project Context

## Overview

A single-page interactive HTML financial planning tool for Indian investors. Built with vanilla HTML/CSS/JS (no frameworks). Dark gradient theme, mobile-responsive.

**Live file:** `smart-wealth-system.html` (rename to `index.html` for GitHub Pages)

---

## Core Philosophy

The system is designed around **keeping money in the right place for the right amount of time** for tax efficiency:

### Working Years (4-Level System)
Money flows like a waterfall through L0 → L1 → L2 → L3. Each level has a specific **holding period purpose**:

- **L0 (Bank):** Instant access. Pay daily expenses or credit card bills.
- **L1 (Arbitrage/Liquid):** Units sit here 12+ months. When you need cash beyond L0, you have 30-45 days (via CC billing cycle) to redeem aged units at 0% LTCG.
- **L2 (Goal-based):** Money parked for specific goals with 1-5 year timeline.
- **L3 (Equity):** Never touch until retirement. Compound for decades.

**The key insight:** L0 + Credit Card creates a TIME BUFFER that allows L1 units to age 12+ months before redemption → tax-free gains.

### Retirement (3-Bucket System)
Corpus is divided into 3 buckets to protect against sequence-of-returns risk.

---

## The 4-Level System (Accumulation Phase)

The levels are designed to **keep MF units in the right place for the right amount of time** for tax efficiency:

| Level | Purpose | Target Amount | Recommended Funds |
|-------|---------|---------------|-------------------|
| **L0** | Bank Buffer — instant access for daily ops | MAX(₹50k, 1 month expenses) | Savings Account |
| **L1** | Tax-Efficient Liquid Reserve — units aged 12+ months for 0% LTCG | 6 months expenses | Arbitrage Fund (15%+ bracket) or Liquid Fund (lower brackets) |
| **L2** | Goal-Based Savings — money parked for specific planned goals | Sum of specific goals | Based on timeline: 1-2yr → Arbitrage, 2-3yr → Equity Savings, 3-5yr → Balanced Advantage |
| **L3** | Long-Term Wealth — never touch until retirement | All remaining surplus | Equity SIPs (Large Cap + Flexi Cap + Mid/Small Cap) |

**Key Rule:** Money only flows to next level when current level is full.

**How L0 + L1 work together:**
- Most payments: L0 cash or Credit Card
- Credit card billing cycle gives you 30-45 days
- During this time, redeem L1 units (that are already 12+ months old)
- Result: Tax-free redemption (LTCG under ₹1.25L = 0%)

**L1 is NOT a traditional "emergency fund":**
- Medical emergencies → Health Insurance (prerequisite, not L1)
- L1 is simply a **tax-efficient second savings layer** with aged units ready for redemption
- The "emergency" framing is misleading — it's really about tax-optimized liquidity

**L2 is Goal-Based:** If user has no specific goals, L2 = ₹0 and money goes directly to L3.

---

## The 3-Bucket System (Decumulation Phase)

| Bucket | Purpose | Size | Fund Type |
|--------|---------|------|-----------|
| **B1** | Spending (SWP source) | 3 years expenses | Arbitrage/Liquid |
| **B2** | Stability (refills B1) | 3 years expenses | Debt/Hybrid |
| **B3** | Growth (refills B2) | Remaining corpus | Equity |

**Refill Strategy:**
- B1 refills from B2 when B1 drops below 1 year
- B2 refills from B3 ONLY when markets are above 200-DMA
- In bear markets: Don't touch B3, let B1+B2 deplete (6-year buffer)

---

## Tax Rules Implemented (FY 2025-26)

### New Tax Regime Slabs (Budget 2025)
| Income Range | Tax Rate |
|-------------|----------|
| Up to ₹4 Lakh | 0% |
| ₹4 - ₹8 Lakh | 5% |
| ₹8 - ₹12 Lakh | 10% |
| ₹12 - ₹16 Lakh | 15% |
| ₹16 - ₹20 Lakh | 20% |
| ₹20 - ₹24 Lakh | 25% |
| Above ₹24 Lakh | 30% |

**Section 87A Rebate:** ₹60,000 for income up to ₹12 Lakh = effectively 0% tax
**Salaried:** Standard Deduction ₹75,000 → Up to ₹12.75 Lakh tax-free

### Mutual Fund Taxation (Post-Budget 2024)

| Fund Type | LTCG (>12mo) | STCG (≤12mo) | Exemption |
|-----------|--------------|--------------|-----------|
| Equity & Arbitrage | 12.5% | 20% | ₹1.25L/year combined |
| Debt & Liquid | Slab rate | Slab rate | None (post-Apr 2023) |
| Hybrid (≥65% equity) | 12.5% | 20% | ₹1.25L/year |
| Hybrid (35-65% equity) | 12.5% after 24mo | Slab rate | None |
| Hybrid (<35% equity) | Slab rate | Slab rate | None |

### Tax Bracket Logic in App
- **15%+ bracket:** Recommend Arbitrage Funds (saves ~2.5-17.5% vs Liquid)
- **5-10% bracket:** Either works, Liquid is simpler
- **0% bracket (rebate eligible):** All options effectively tax-free, use simplest

### Key Tax Feature
- **ELSS Warning:** Under New Tax Regime, Section 80C is NOT available. ELSS has 3-year lock-in with NO benefit. App explicitly warns against this.

---

## App Structure (6 Tabs)

### 1. 📚 Guide Tab (Default)
- Two-phase system explanation
- 4-Level waterfall visualization
- 3-Bucket retirement explanation
- **Prerequisites section:** Term Insurance, Health Insurance, No high-interest debt

### 2. 🎯 Personalized Plan Tab
**Inputs:**
- Monthly salary, expenses
- Tax bracket (dropdown with FY 2025-26 slabs)
- Current age, retirement age
- Existing investments

**Outputs:**
- L0/L1/L2/L3 recommended amounts (dynamic based on expenses)
- Monthly money flow breakdown
- Fund recommendations (changes based on tax bracket)
- Tax comparison table
- Wealth projection with ISR options

**Sub-sections:**
- SEBI Fund Categories guide
- Asset Allocation models (Conservative/Moderate/Aggressive)
- L3 Management Rules (tax harvesting, rebalancing, step-up SIPs)
- Goal Planner (add/remove specific goals for L2)
- ISR Calculator (17.5 to 30 options)
- Bucket Refill Strategy

### 3. 📊 Working Years Tab
- Visual 4-level waterfall with progress bars
- Editable current/target amounts per level
- Real-time progress calculation
- Summary cards (total tracked, target, progress %)

### 4. 🏖️ Retirement Buckets Tab
- Configurable monthly expense and corpus inputs
- Automatic 3-bucket division
- SWP amount display

### 5. 🧮 Calculators Tab
- **ISR Calculator:** Monthly expense → Required corpus (with adjustable ISR)
- **SIP Calculator:** With annual step-up option (year-by-year calculation)
- **Lump Sum Calculator:** One-time investment growth
- **L0 + L1 Calculator:** Expenses × months → Liquid reserve split
- **Time to Goal Calculator:** Goal amount → Years needed

### 6. 📋 Rules Tab
- Golden rules as color-coded cards (green=do, yellow=warning, red=never)

---

## Key Design Decisions

### 1. No Specific Fund Names
- Only SEBI categories mentioned (Arbitrage, Liquid, Equity Savings, Large Cap, Flexi Cap, etc.)
- Selection criteria provided: "AUM > ₹1,000 Cr, Expense Ratio < 1%"
- Avoids the tool becoming outdated when fund performance changes

### 2. L2 is Goal-Based (Not Fixed Amount)
- Previous version had fixed ₹2-3L for L2
- Now: L2 = Sum of user's specific goals
- No goals = No L2 needed, money goes to L3
- Goal Planner allows adding goals with name, amount, timeline

### 3. Dynamic L0/L1 (Not Fixed)
- L0 = MAX(₹50,000, 1 month expenses)
- L1 = 6 months expenses (not fixed ₹3L)
- Scales with user's lifestyle

### 4. ISR Options (Not Fixed 17.5)
- Default: ISR 22 (4.5% withdrawal rate) - Moderate
- Options: 17.5 (Aggressive) to 30 (Very Conservative)
- Warning displayed for aggressive options

### 5. L3 Rules Added
- Tax harvesting: Redeem ₹1.25L LTCG annually in March, reinvest immediately
- Rebalancing: If allocation drifts >10% from target
- Step-up SIPs: Increase 10-15% yearly
- Never redeem for consumption before retirement

### 6. STCG Warning for Arbitrage
- Arbitrage LTCG (>12mo) = 0-12.5%
- Arbitrage STCG (≤12mo) = 20% flat
- App notes: "Plan for 12+ month holding"

### 7. Insurance Prerequisites
- Added warning in Guide: Term Insurance + Health Insurance required before starting
- This system assumes major medical emergencies are covered by insurance, not L1

---

## Technical Details

- **Single HTML file:** ~3,700 lines (HTML + CSS + JS inline)
- **No dependencies:** Vanilla JS, no frameworks
- **Mobile responsive:** Flexbox/Grid with media queries
- **Dark theme:** Gradient background (#1a1a2e → #16213e → #0f3460)
- **Indian currency formatting:** Lakh/Crore conversion
- **All calculations client-side:** No server needed

### Key JavaScript Functions
- `generatePlan()` - Main function that updates all recommendations
- `updateFundRecommendations(taxBracket)` - Changes fund cards based on bracket
- `updateFundCategories(taxBracket)` - Updates SEBI category section
- `updateTaxTable(taxBracket)` - Updates tax comparison table
- `addGoal()` / `removeGoal()` / `renderGoals()` - Goal management
- `updateL2Display()` - Calculates total L2 from goals
- `updateISRProjection()` - Updates corpus based on ISR choice
- `calculateSIP()` - SIP with step-up (year-by-year loop)

---

## Potential Improvements (Not Implemented)

1. **Inflation adjustment** in retirement bucket calculations
2. **EPF/PPF integration** - Where does mandatory retirement savings fit?
3. **Debt repayment priority** - Logic for when to pay debt vs invest
4. **Child goal tracking** - Separate from main L2
5. **Export/Import** - Save state to JSON
6. **Charts** - Visual wealth growth projection

---

## File for GitHub

Rename `smart-wealth-system.html` to `index.html` for GitHub Pages hosting.

Suggested repo structure:
```
smart-wealth-system/
├── index.html          # Main app
├── README.md           # User-facing documentation
├── CLAUDE.md           # This file (dev context)
└── LICENSE             # MIT recommended
```

---

## Git Commit Conventions

This project uses **Conventional Commits** (https://www.conventionalcommits.org/en/v1.0.0/)

### Format
```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

### Types
- **feat**: New feature
- **fix**: Bug fix
- **docs**: Documentation changes
- **style**: Code style changes (formatting, no logic change)
- **refactor**: Code refactoring (no feature or bug fix)
- **perf**: Performance improvements
- **test**: Add or update tests
- **chore**: Build process, dependencies, tooling

### Examples
```
feat: add inflation adjustment to retirement calculator
fix: correct LTCG calculation for arbitrage funds
docs: update tax slabs for FY 2026-27
refactor: split CSS into separate file
chore: add localStorage for goal persistence
```

### Rules
- Use lowercase for type and description
- Keep description concise (50 chars or less)
- Use imperative mood ("add" not "added")
- No period at the end of description
- Never mention authorship in commits

---

## Commands for Claude Code

When working on this project, useful prompts:

- "Add a new calculator for [X]"
- "Update the tax slabs for FY 2026-27"
- "Split the CSS into a separate file"
- "Add localStorage to persist goals"
- "Create a README.md for users"