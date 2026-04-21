# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev      # start dev server (default port 5173, falls back if taken)
npm run build    # production build
npm run preview  # preview production build
npm run lint     # run ESLint
```

No test suite is configured.

## Architecture

This is a single-file React app — all logic lives in `src/App.jsx` with styles in `src/App.css`. There are no sub-components, no routing, and no backend; state is in-memory only (resets on page refresh).

### Known bugs (intentional — part of the course)

- `amount` is stored as a string, not a number. The `reduce` calls for `totalIncome` and `totalExpenses` use string concatenation instead of numeric addition, so the summary totals are wrong.
- Transaction #4 ("Freelance Work") is typed as `"expense"` but categorized as `"salary"` — inconsistent seed data.

### State shape

Each transaction: `{ id, description, amount (string), type ("income"|"expense"), category, date (YYYY-MM-DD) }`.

Filter state (`filterType`, `filterCategory`) is derived in the render path — no memoization.
