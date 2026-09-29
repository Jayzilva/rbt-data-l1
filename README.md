# rbt-data-l1 — Data Engineer track (DATA-L1)

My work for the BISTEC Academy role-based training **Data Engineer** track: six modules, each a
self-contained project built spec-first with [specclaw](https://github.com/Jayzilva/specclaw)
(teaching mode on), shipped as one reviewed pull request, and written up publicly.

Carry-through dataset: RetailCo (extended across modules). The stack runs on Docker Compose, so start after OPS-L1-M02.

## Modules

| ID | Module | Scheduled | Headline target | Status | PR | Video | Post |
|---|---|---|---|---|---|---|---|
| DATA-L1-M01 | Data Pipeline Fundamentals | Fri 16 – Sun 18 Oct 2026 | working DAGs | Not started | – | – | – |
| DATA-L1-M02 | SQL & Data Modeling | Fri 23 – Sat 24 Oct 2026 | star schema | Not started | – | – | – |
| DATA-L1-M03 | Lakehouse & Warehousing | Wed 28 – Thu 29 Oct 2026 | bronze/silver/gold | Not started | – | – | – |
| DATA-L1-M04 | Data Quality & Testing | Wed 4 – Thu 5 Nov 2026 | quality suite | Not started | – | – | – |
| DATA-L1-M05 | Python for Data Engineering | Wed 11 – Thu 12 Nov 2026 | PySpark jobs | Not started | – | – | – |
| DATA-L1-M06 | End-to-End Platform (capstone) | Fri 13 – Sun 15 Nov 2026 | CSV to dashboard | Not started | – | – | – |

A module is done only when its PR is approved. Status values: Not started, Ready, Studying, Building,
Verifying, In review, Approved. A title becomes a link when its folder is created.

## How this repo works

- **One folder per module**, created on its start day with `node tools/start-module.mjs mNN`
  (or `/start-module mNN` in Claude Code at the repo root). Each folder has its own `CLAUDE.md`,
  `.claude/` rules and skills, `memory/`, `.specclaw/` and docs, so it works on its own:
  `cd mNN-* && claude`.
- **Spec-driven**: propose → teach → plan → build → verify → pr, one specclaw change per module.
- **Learning first**: teaching mode briefs unfamiliar concepts and hands design decisions to me.
- **Review**: PR titled `<MODULE-ID> <Title>`, self-scored against the rubric; reviewer: To confirm.
  After approval: merge, tag `<module-id>-v1`.

## Connected content

Every module links three ways: this repo ↔ a NotebookLM video on YouTube ↔ the weekly Substack
build log. Links live in the table above and in each module's README.

## Publishing

Academy material is confidential and never committed (`.academy/` and `*/academy/` are
gitignored). Only each module's `docs/PUBLIC.md` feeds public content.

- [ ] Written OK from the academy owner to publish build logs and videos (date, who):

## Setup after a fresh clone

    ACADEMY_PASSWORD=... node tools/fetch-academy.mjs      # decrypt track pages into .academy/
    node tools/start-module.mjs m01 --refresh-academy     # restore a module's academy/ files

Requires Node 18+. Pandoc is optional (better Markdown). Claude Code picks up the specclaw
plugin from each module's `.claude/settings.json`.
