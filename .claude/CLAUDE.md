# Time Tracking — Agent Instructions

## Purpose

This repo tracks developer hours for invoicing. You maintain it as part of your workflow. Each engagement forks this template and configures `config.md` with the actual projects, categories, and rate.

## When to Track

Track time after completing work: tickets, meetings, support, setup. Add entries to the current week's KW file.

## Handling Tracking Commands

When given a command like "Track 1h on this ticket", "Log 0,5h on PROJ-123", or "Add 2h to today":

1. **Hours** — extract the amount (minimum 0,25h; use European comma: `1,5` not `1.5`)
2. **Project** — determine from ticket key prefix, explicit mention, or current work context. Check `config.md` → Projects table.
3. **Ticket key** — include in description as `{TICKET-KEY}` (e.g. `PROJ-123`). For ticket work, the ticket key IS the description or its first word.
4. **Category** — use `TICKET` for issue/ticket work. Check `config.md` → Categories per Project.
5. **Date** — use today's date (DD.MM.) unless specified otherwise.

After writing the entry, confirm:
> Tracked: {hours}h → {Project} | {category} | {description} (KW{nn}, {date})

## How to Track (Step by Step)

1. **Find current week file**: `YYYY-MM/KW{nn}.md` (create if missing — see template below)
2. **Add entry** to the correct project table: date, hours, category, description
3. **Update Gesamt** row in the project table
4. **Update Tagesübersicht** at bottom of week file
5. **Update SUMMARY.md** in the month folder

## File Location Rules

- Week file goes in the month folder where **Monday** of that week falls
- If Monday is in January but Friday is in February, the whole KW file lives in the January folder
- New month = new folder + new SUMMARY.md

## Creating a New Week File

Read `config.md` for projects and categories. Use this structure:

```
# KW{nn} (DD.MM. - DD.MM.YYYY)

> **Wochenziel**: {total}h — {Project A} {n}h | {Project B} {n}h

## {Project A}

| Datum | Stunden | Kategorie | Beschreibung |
|-------|---------|-----------|--------------|
| **Gesamt** | **0** | | |

## Tagesübersicht

| Datum | Gesamt | {Project A} |
|-------|--------|-------------|
| **Woche** | **0** | **0** |
```

## Creating a Monthly Summary

```
# {Month YYYY}

## Monatsübersicht

| Projekt | Stunden | Ziel (h/Woche) |
|---------|---------|-----------------|
| {Project A} | 0 | {target} |
| **Gesamt** | **0** | **{total target}** |

## Wochen

| KW | {Project A} | Gesamt |
|----|-------------|--------|
| **Gesamt** | **0** | **0** |

## Rechnung

| Stunden | Rate | Betrag |
|---------|------|--------|
| 0 | {rate} | 0 |
```

## Validation

After updating, verify:
- Project Gesamt rows match sum of entries
- Tagesübersicht matches project tables
- SUMMARY.md matches week file totals