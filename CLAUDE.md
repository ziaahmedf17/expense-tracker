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

This is a React + Vite app with no routing, no backend, and no persistence — all state is in-memory and resets on page refresh.

### Component structure

- **`App`** (`src/App.jsx`) — root component, holds the `transactions` array in state and passes it down
- **`Summary`** (`src/Summary.jsx`) — receives `transactions`, computes and displays total income, expenses, and balance
- **`TransactionForm`** (`src/TransactionForm.jsx`) — owns its own form state (description, amount, type, category), calls `onAdd(transaction)` prop on submit
- **`TransactionList`** (`src/TransactionList.jsx`) — receives `transactions`, owns its own filter state (filterType, filterCategory), renders the filtered table

### Transaction shape

```js
{ id, description, amount (number), type ("income" | "expense"), category, date ("YYYY-MM-DD") }
```

### Shared constants

`categories` array is defined locally in both `TransactionForm` and `TransactionList` — not yet extracted to a shared file.
