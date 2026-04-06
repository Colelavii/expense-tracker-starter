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

Single-page React app with no routing. All application logic lives in `src/App.jsx` as one monolithic component using `useState` hooks for state management. No external state management library.

Key state: `transactions` array of `{id, description, amount, type, category, date}` objects, plus form input fields and filter controls.

Entry point: `index.html` → `src/main.jsx` (StrictMode) → `src/App.jsx`.

Styling is plain CSS (`App.css`, `index.css`), not CSS-in-JS.

## Lint Config

ESLint flat config (`eslint.config.js`) with react-hooks and react-refresh plugins. `no-unused-vars` ignores uppercase and underscore-prefixed variables.
