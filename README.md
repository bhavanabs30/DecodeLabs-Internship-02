# 💰 DecodeLabs Expense Tracker v2

> **Project 2 — Industrial Training Kit | Batch 2026**
> A production-style Python CLI that tracks expenses using the **IPO Model**, **Accumulator Pattern**, and **Defensive Coding** principles.

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Tests](https://img.shields.io/badge/Tests-6%20Passing-success)

---

## 📖 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Demo](#-demo)
- [Installation](#-installation)
- [Usage](#-usage)
- [Commands Reference](#-commands-reference)
- [Project Structure](#-project-structure)
- [Architecture](#-architecture)
- [Running Tests](#-running-tests)
- [Learning Objectives](#-learning-objectives)
- [Screenshots](#-screenshots)
- [Tech Stack](#-tech-stack)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)
- [Author](#-author)
- [Acknowledgements](#-acknowledgements)

---

## 🎯 Overview

The **Expense Tracker v2** is the milestone deliverable for **Project 2** of the DecodeLabs Industrial Training Kit (Batch 2026). It is a fully-featured command-line expense manager that demonstrates:

- **Data Accumulation** — persistent state across continuous input
- **Real-time processing** — every transaction updates totals instantly
- **Error resilience** — the program never crashes on bad input
- **Backend engineering fundamentals** — the same patterns used in real banking systems

This isn't just arithmetic. It's a **state-preserving backend engine**.

---

## ✨ Features

| # | Feature | Description |
|---|---------|-------------|
| 1 | **IPO Model** | Clean Input → Process → Output separation |
| 2 | **Accumulator Pattern** | `total += expense` at the core |
| 3 | **Defensive Coding** | `try/except ValueError` Poka-Yoke shield |
| 4 | **Sentinel Kill Switch** | Type `quit` for a graceful shutdown |
| 5 | **Expense Categories** | Track *where* money goes, not just *how much* |
| 6 | **Transaction History** | Full list of every logged expense |
| 7 | **Undo Last Entry** | One-command rollback of the last transaction |
| 8 | **Colored Terminal Output** | ANSI-based visual feedback (✅ ❌ ⚠️) |
| 9 | **Amount Validation** | Rejects negatives, zeros, and $1M+ outliers |
| 10 | **JSON Persistence** | Data survives program restarts |
| 11 | **CSV Export** | Spreadsheet-ready exports for Excel/Sheets |
| 12 | **Budget Alerts** | Warns at 80% and 100% of monthly budget |
| 13 | **Mini CLI Parser** | `help`, `history`, `summary`, `export`, `undo` |
| 14 | **Daily Totals** | Automatic per-day spending aggregation |
| 15 | **Multi-User Login** | Each user gets an isolated account |
| 16 | **Audit Logging** | Timestamped `tracker.log` of every action |
| 17 | **Unit Tests** | 6 passing tests via `unittest` |
| 18 | **Graceful Ctrl+C** | Interrupt-safe with auto-save |

---

## 🎬 Demo

```console
$ python expense_tracker_v2.py

====================================================
   DECODELABS EXPENSE TRACKER v2
====================================================
  Login name: alice
  🆕 New user 'alice' created.

  Type help for commands, quit to exit.
  Type a number to log an expense.

[alice] $0.00 > 100
  Category [General]: Food
  ✅ Added $100.00 to 'Food' | Running Total: $100.00

[alice] $100.00 > 50
  Category [General]: Travel
  ✅ Added $50.00 to 'Travel' | Running Total: $150.00

[alice] $150.00 > ten
  ❌ Invalid Data. Enter a number or a command.

[alice] $150.00 > undo
  ↩️  Undid $50.00 from 'Travel'

[alice] $100.00 > summary

====================================================
         FINAL EXPENSE REPORT — ALICE
====================================================
  Transactions Processed : 1
  FINAL TOTAL            : $100.00

  Breakdown by Category:
    Food         $   100.00  100.0%  ████████████████████

  Daily Totals:
    2026-10-03  ->  $100.00

====================================================

[alice] $100.00 > quit

  [SYSTEM] Saving and shutting down...
