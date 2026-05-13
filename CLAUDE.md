# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This repository is an **image asset store** — there is no source code, build system, package manifest, tests, or runtime here. The repo holds marketing-style card images for broadband/fibre internet plans, intended to be consumed by another project (e.g. embedded in a website or design doc).

The repo name (`assest`) appears to be a typo of `assets` and is preserved as-is in the remote URL.

## Contents

Two unrelated visual sets live at the repo root (there are no subdirectories):

- **`BB1.jpg` – `BB4.jpg`, `BB3_new.png`** — Full-detail plan cards on a green background, styled after Australian nbn® plans. Tiered:
  - `BB1` Fast Fibre 500/50 — `$95/month`
  - `BB2` Superfast Fibre 750/50 — `$119/month`
  - `BB3` / `BB3_new` Ultrafast Fibre 1000/100 — `$129/month` (two crops of the same plan)
  - `BB4` Hyperfast 2000/200 — `$189/month`
  Each lists max speed, target audience size, "No lock-in contract / Unlimited Data", and eligible connection types (FTTP, HFC).

- **`plan1.png` – `plan4.png`** — Simpler light-blue tile cards for a different plan family:
  - `plan1` Basic Fiber 300 Mbps — `$49.99/month`
  - `plan2` Family Fiber 600 Mbps — `$69.99/month`
  - `plan3` Gaming Fiber 1 Gbps — `$89.99/month`
  - `plan4` Ultimate Fiber 2 Gbps — `$119.99/month`

The two sets are visually distinct and likely belong to different downstream consumers — don't assume edits to one set should propagate to the other.

## Working in This Repo

There is nothing to build, lint, or test. Typical tasks are:

- Adding, replacing, or renaming image files.
- Generating new tier/variant cards that match an existing visual style.

When replacing an image, **match the existing dimensions, aspect ratio, file format, and naming pattern** of its set (`BB*.jpg` vs `plan*.png`) so downstream consumers don't break. The `BB3` / `BB3_new` pair shows the convention used when a second variant is needed rather than overwriting the original.

## Git Workflow

- Remote: `ssnaveen10/assest` (only repository in scope for GitHub MCP tools).
- History so far is entirely "Add files via upload" commits from the GitHub web UI; when committing through Claude Code, write a descriptive message instead.
- Image files are binary — prefer `git add <specific-file>` over `git add .` and avoid committing source-design files (`.psd`, `.fig`, `.sketch`, `.xcf`) unless the user asks; they bloat history.
