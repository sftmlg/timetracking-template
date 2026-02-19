# Time Tracking

LLM-friendly developer time tracking. Markdown-based, designed for AI coding agents to read and write automatically.

## How It Works

Weekly markdown files track hours per project. Each project corresponds to a repo or codebase in the engagement. Monthly summaries aggregate for invoicing. All files follow a strict format so LLMs can parse and update them reliably.

## Structure

- `YYYY-MM/KW{nn}.md` — Weekly time entries (one file per calendar week)
- `YYYY-MM/SUMMARY.md` — Monthly totals for invoicing
- `config.md` — Projects, categories, rates, and rules for this engagement

Each week file is divided by **project** (repo/codebase). Within each project section, entries include date, hours, category, and description. Ticket work uses the ticket key as description.

## Workflow

1. **Track** — Add entry to current week file, in the correct project section
2. **Summarize** — Update monthly SUMMARY.md
3. **New week** — Create new KW file when calendar week changes
4. **New month** — Create new YYYY-MM/ folder with fresh SUMMARY.md

## Week File Format

Each week file is structured by project, then by day. Ticket numbers appear directly in the description.

### Per-Project Tables

```markdown
## {Project Name}

| Datum | Stunden | Kategorie | Beschreibung |
|-------|---------|-----------|--------------|
| 10.02. | 2 | TICKET | PROJ-123 Fix login redirect |
| **Gesamt** | **2** | | |
```

### Daily Overview

```markdown
## Tagesübersicht

| Datum | Gesamt | {Project A} | {Project B} |
|-------|--------|-------------|-------------|
| 10.02. | 5 | 3 | 2 |
| **Woche** | **5** | **3** | **2** |
```

## Monthly Summary Format

```markdown
# {Month Year}

## Monatsübersicht

| Projekt | Stunden | Ziel (h/Woche) |
|---------|---------|-----------------|
| {Project A} | 48 | 20 |
| **Gesamt** | **48** | **20** |

## Wochen

| KW | {Project A} | Gesamt |
|----|-------------|--------|
| KW06 | 20 | 20 |
| **Gesamt** | **48** | **48** |

## Rechnung

| Stunden | Rate | Betrag |
|---------|------|--------|
| 48 | 100 | 4.800 |
```

## Time Units

| Minutes | Hours |
|---------|-------|
| 15 | 0,25 |
| 30 | 0,5 |
| 45 | 0,75 |
| 60 | 1 |

Minimum unit: 0,25h (15 minutes). Use comma as decimal separator (European format).

## Rules

- **Frequency**: Track daily (end of workday)
- **Minimum**: 0,25h per entry
- **Granularity**: Category + short description per entry
- **Ticket format**: Use ticket key in description (e.g. `PROJ-123`)
- **Week boundary**: KW file belongs to the month where Monday of that week falls
- **Weekend work**: Only with pre-approval (note in description)

## Setup

1. Fork this repo
2. Edit `config.md` with your projects, categories, and rate
3. Create first month folder: `mkdir YYYY-MM`
4. Start tracking

## For LLM Agents

This repo is designed for Claude Code and similar AI coding assistants. The `.claude/CLAUDE.md` contains instructions for automatic time tracking, including how to handle commands like "Track 1h on ticket PROJ-123". When placed as a sibling to project repos, agents can track time as part of their normal workflow.