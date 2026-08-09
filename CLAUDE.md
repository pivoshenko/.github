# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

`git@github.com:pivoshenko/.github.git` — the GitHub special `.github` repository for the `pivoshenko` account. It contains no application code, only default community health files that GitHub falls back to for every repository under the account that does not define its own.

Consequences of that role:

- There is no build, test, lint, or dependency tooling. No package manager manifest, no Makefile/justfile, no CI workflows exist. Do not invent commands; there is nothing to run.
- Every file here is user-facing configuration consumed by GitHub, not by a program. A change takes effect for all of the account's repositories at once, so treat edits as broad-blast changes rather than local ones.
- For a file to be picked up as an account-wide default it must live at the repo root, in `.github/`, or in `docs/`. Adding a new default (e.g. `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`, `ISSUE_TEMPLATE/`) means creating it in one of those locations — currently everything sits at the root.

## Current contents

- `PULL_REQUEST_TEMPLATE.md` — account-wide PR template: a commented-out `Resolves: #n` line, a Summary section, and a five-item author checklist.
- `.editorconfig` — `root = true`, so it is the terminating config for this repo only; it is not inherited by other repositories the way the community health files are.
- `README.md` — one line; rendered on the account profile only if a `profile/README.md` is absent.

## Conventions

- Editor settings: UTF-8, LF, final newline, trimmed trailing whitespace, 120-column max. Two-space indent by default; four for `*.py`, `*.pyi`, `*.ipynb`, `*.rs`.
- Commits follow Angular conventional-commit format (`chore:`, `docs:` in the existing history).
- The PR checklist in `PULL_REQUEST_TEMPLATE.md` describes expectations for the *consuming* repositories; do not reword it to fit a change being made in this repo.
