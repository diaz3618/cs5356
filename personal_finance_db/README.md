# Personal Finance Tracker — Database Project

Database for tracking personal income and expense transactions.

---

## Project Structure

```
personal_finance_db/
├── schema/
│   └── schema.sql          # CREATE DATABASE, tables, triggers
├── seed/
│   └── seed.sql            # Sample users, categories, and transactions
├── queries/
│   └── report_queries.sql  # Five required report queries
├── docs/
│   └── schema_notes.md     # Table definitions, constraints, design notes
└── README.md               # This file
```

## What the Queries Produce

| # | Query | Description |
|---|-------|-------------|
| 1 | Monthly Expense Totals | Sum of all expenses grouped by month |
| 2 | Monthly Income Totals | Sum of all income grouped by month |
| 3 | Spending by Category | Total spent per expense category |
| 4 | Income vs Expense by Month | Side-by-side income, expenses, and net savings |
| 5 | User Transactions by Date | All transactions for a given user, chronological |

---

## Key Constraints

- `amount > 0` — no zero or negative amounts
- `category_type` / `transaction_type` — restricted to `'income'` or `'expense'`
- **Type-mismatch trigger** — a transaction's type must match its category's type
- `email` is UNIQUE across users
- Foreign keys enforce referential integrity between all three tables

---

## Documentation

See [docs/schema_notes.md](docs/schema_notes.md) for detailed table
definitions, constraint explanations, and design decisions.
