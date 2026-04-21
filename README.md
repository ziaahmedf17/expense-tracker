# Expense Tracker

A personal finance tracking web application built with **React + Vite**. Track your income and expenses, filter by category or type, and get a live summary of your financial balance — all in the browser with no backend required.

## Features

- **Add transactions** — log income or expense entries with a description, amount, category, and date
- **Delete transactions** — remove any entry from the list
- **Live summary** — see your total income, total expenses, and current balance update in real time
- **Filter transactions** — filter the list by type (income / expense) or by category
- **No backend / no persistence** — all state is in-memory; data resets on page refresh

## Tech Stack

| Tool | Purpose |
|------|---------|
| React 18 | UI components and state management |
| Vite | Dev server and production build |
| ESLint | Code linting |

## Getting Started

```bash
# Install dependencies
npm install

# Start the development server
npm run dev
```

Then open your browser at `http://localhost:5173`.

## Available Scripts

```bash
npm run dev      # Start dev server (hot reload)
npm run build    # Production build → dist/
npm run preview  # Preview the production build locally
npm run lint     # Run ESLint
```

## Project Structure

```
src/
├── App.jsx             # Root component — holds transactions state
├── Summary.jsx         # Displays total income, expenses, and balance
├── TransactionForm.jsx # Form to add a new transaction
├── TransactionList.jsx # Filterable table of all transactions
├── App.css             # Global styles
└── main.jsx            # React entry point
```

## Transaction Shape

Each transaction stored in state follows this structure:

```js
{
  id:          string,           // unique identifier
  description: string,           // e.g. "Salary", "Grocery run"
  amount:      number,           // always positive
  type:        "income" | "expense",
  category:    string,           // e.g. "Food", "Salary", "Utilities"
  date:        "YYYY-MM-DD"
}
```

## License

MIT
