# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Expense tracker starter app built with React 19 and Vite 7. This is a learning project that intentionally contains bugs, poor UI, and messy code meant to be improved.

## Commands

- `npm run dev` — Start dev server (http://localhost:5173)
- `npm run build` — Production build
- `npm run lint` — ESLint (flat config, ESLint 9)
- `npm run preview` — Preview production build

## Architecture

Single-page React app with no routing. Uses `useState` hooks for state management with no external state library.

Entry point: `index.html` → `src/main.jsx` (StrictMode) → `src/App.jsx`.

### Component structure

- **`App.jsx`** — Root component. Owns the `transactions` array state and passes it down to children.
- **`Summary.jsx`** — Computes and displays `totalIncome`, `totalExpenses`, and `balance` from the `transactions` prop.
- **`TransactionForm.jsx`** — Owns form input state (`description`, `amount`, `type`, `category`). Calls `onAddTransaction` prop on submit.
- **`TransactionList.jsx`** — Owns filter state (`filterType`, `filterCategory`). Receives `transactions` prop and renders filtered table.

Transaction shape: `{id, description, amount (number), type, category, date}`.

Styling is plain CSS (`App.css`, `index.css`), not CSS-in-JS.

## Lint Config

ESLint flat config (`eslint.config.js`) with react-hooks and react-refresh plugins. `no-unused-vars` ignores uppercase and underscore-prefixed variables.
