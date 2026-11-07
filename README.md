# Options Visual Guide (`options-visual-guide`)

Interactive single-file visual guide and payoff simulator explaining stock options (Bullish, Bearish, Stock Owner Income/Hedges, and Volatility strategies) using a $10,000 investment in Google (`GOOGL` @ $100/share).

## Files

- `index.html`: Self-contained single-page application (HTML + Tailwind CSS + vanilla JS SVG payoff chart + bidirectional P&L bars + comparison tables).

## How Another Agent Can Edit This

1. **Adding or modifying strategies in the simulator:**
   - Open `index.html` and locate `const catalog = { bullish: [...], bearish: [...], income: [...], volatility: [...], versus: [...] }`.
   - Each strategy object defines:
     - `id`, `name`, `shortLabel`, `color` (hex string)
     - `subtitle`, `breakeven`, `eli5` (plain-English explanation)
     - `calc: (p) => ({ endVal, profit })` where `p` is the ending stock price ($70 to $130)
     - `verdict: (p, profit) => string` (dynamic takeaway at price `p`)
2. **Updating the live public link:**
   - Commit changes to `main` and run `git push`. GitHub Pages deploys automatically from the `main` branch root to `https://jctkerr.github.io/options-visual-guide/`.
