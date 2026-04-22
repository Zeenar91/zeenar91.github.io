---
title: OER reporting pipeline
year: 2025
category: Data infrastructure
summary: A Python pipeline that turns messy multi-source OER adoption data into clean institutional reports — composite-key matched, myID-normalized, and ready for leadership.
role: Designer and lead developer
tools: Python, Google Colab, pandas, Google Sheets API
featured: true
tags: [data pipeline, OER, analytics, Python]
---

Institutional OER (Open Educational Resources) data arrives from a dozen
places in a dozen shapes: faculty self-reports, LMS exports, library
records, grant program rosters. Getting from that mess to a clean
leadership report is less a reporting problem than a data engineering one.

## What the pipeline does

- **Normalizes email inputs** — lowercases, strips whitespace, resolves
  myID-style variants to primary institutional addresses
- **Composite-key matches** adoptions against a canonical People Sheet
  (last name + first initial + department) to catch records missing clean
  identifiers
- **Handles external emails** gracefully — flags them for review rather
  than dropping them
- **Transforms wide to long** so each adoption becomes an atomic record
- **Outputs a two-sheet Excel workbook**: processed records on one sheet,
  missing/unmatched records on the other, so the humans reviewing it know
  exactly what still needs attention

## Why this is the interesting part

The reporting numbers are easy once the matching is right. Ninety percent
of the work is the matching. Ninety percent of the *value* is surfacing
the records that didn't match — because that's where the institutional
blind spots live.
