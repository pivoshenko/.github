# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repository Is

`pivoshenko/.github` is GitHub's special community-health repository for the `pivoshenko` account. It contains no
application code, no build system, and no tests - only Markdown and config files that GitHub reads.

The entire point is propagation: GitHub serves a file from this repository as the default for **every** repository under
the `pivoshenko` account that does not ship its own copy. A change here is therefore an account-wide change, not a local
one. Treat edits accordingly.

## How GitHub Resolves These Files

- for a file that may live in more than one place, GitHub checks the `.github/` folder first, then the repository root,
  then `docs/`. This repository keeps its own files at the root
- a repository that has its own copy of a file always wins over the default served from here
- this repository must stay public - a private `.github` repository propagates nothing
- only specific filenames are recognized (`CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`, `FUNDING.yml`, `ISSUE_TEMPLATE/`,
  `PULL_REQUEST_TEMPLATE.md`, `SECURITY.md`, `SUPPORT.md`, `DISCUSSION_TEMPLATE/`). A file with any other name is
  inert - it sits in the repository and does nothing
- several of those names are pinned to one location: `FUNDING.yml` must be in `.github/`, issue templates and their
  `config.yml` in `.github/ISSUE_TEMPLATE/`, discussion category forms in `.github/DISCUSSION_TEMPLATE/`. Only
  `CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`, `PULL_REQUEST_TEMPLATE.md`, `SECURITY.md` and `SUPPORT.md` may sit at the
  root
- `profile/README.md` does not belong here: rendering a profile README out of a `.github` repository is an
  organization-only feature, and `pivoshenko` is a user account. Its profile README lives in the same-named repository
  `pivoshenko/pivoshenko`

When asked to add a community-health file, get the filename and location exactly right - a near-miss name silently has
no effect anywhere.

## Current Contents

- `README.md` - describes the repository itself, shown only to someone browsing it
- `PULL_REQUEST_TEMPLATE.md` - default PR body for account repositories without their own template
- `.editorconfig` - editor settings; local to this repository, not inherited by others
- `CLAUDE.md` / `AGENTS.md` - agent instructions

## AGENTS.md Is a Symlink

`AGENTS.md` is a symbolic link to `CLAUDE.md`, so both agent conventions read one source of truth.

- edit `CLAUDE.md`; never write to `AGENTS.md`
- do not replace the symlink with a regular file, and do not let a tool that rewrites files in place dereference it

## Build, Lint, Test

There are none. No package manager, no task runner, no CI configuration. Verification is reading the Markdown and
confirming a file's name and path match what GitHub expects.

## Conventions

- formatting follows `.editorconfig`: UTF-8, LF endings, final newline, trailing whitespace trimmed, 2-space indent
  (4 for Python and Rust), 120-column limit
- commits use Angular conventional format with a lowercase imperative subject - the history here is almost entirely
  `docs:` and `chore:`
- Markdown prose wraps at 120 columns rather than running as one long line
