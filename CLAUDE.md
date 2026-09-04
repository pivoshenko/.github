# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

`git@github.com:pivoshenko/.github.git` — GitHub's special `.github` repository for the `pivoshenko` account. It holds default community health files that GitHub applies to every repository under the account that does not define its own copy. There is no application code.

Consequences of that role:

- There is no build, lint, typecheck, test, run, or release tooling — no package manifest, Makefile, Taskfile, CI workflows, or pre-commit config exist. Do not invent or run commands; the only lifecycle here is editing files and committing.
- Every file is configuration consumed by GitHub itself. A change to a default file takes effect across all of the account's repositories that lack their own override, so treat edits as account-wide changes, not local ones.
- GitHub only picks up defaults from the repo root, `.github/`, or `docs/`. Adding a new default (`CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`, `FUNDING.yml`, `ISSUE_TEMPLATE/`, etc.) means placing it in one of those locations — currently everything sits at the root.

## Current contents

- `PULL_REQUEST_TEMPLATE.md` — the account-wide default PR template: an optional commented-out `Resolves: #n` line, a `## Summary` section, and a five-item author checklist.
- `.editorconfig` — editor settings for this repo only (`root = true`); unlike the health files, it is not inherited by other repositories.
- `README.md` — one line describing the repo's purpose.

## Conventions

- Editor settings from `.editorconfig`: UTF-8, LF, final newline, trimmed trailing whitespace, 120-column max. Two-space indent by default; four spaces for `*.py`, `*.pyi`, `*.ipynb`, and `*.rs`.
- Commit messages follow Angular conventional-commit format — existing history uses `chore:` and `docs:` prefixes.
- The checklist wording in `PULL_REQUEST_TEMPLATE.md` addresses contributors of the *consuming* repositories; do not reword it to describe changes made in this repo.
