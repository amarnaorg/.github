# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

`amarnaorg/.github` is GitHub's special org-level defaults repository — not an
application. There is no source code, no package manifest, no build, no test
suite and no CI. Every file here is Markdown that GitHub renders or hands to
other repositories.

Three files, and each one is load-bearing for a different GitHub feature:

- `profile/README.md` — renders as the org landing page at github.com/amarnaorg
- `PULL_REQUEST_TEMPLATE.md` — prefills the PR body in every org repo that
  doesn't define its own
- `README.md` — documents this repo for people browsing it; has no GitHub-level
  special meaning

## The inheritance model (the thing to get right)

Changes here propagate to every repository in the org, so the blast radius of
an edit is the whole org, not this repo.

- **Fallback, not override.** GitHub uses a file from here only when the target
  repo has no copy of its own. A repo overrides a default by adding the file to
  its root, `.github/` or `docs/` folder. Nothing in this repo changes to
  accommodate that.
- **This repo must stay public.** A private `.github` repo is ignored entirely —
  including by the org's private repos. Never propose making it private.
- **Location matters.** `profile/README.md` is the only file that belongs in a
  subdirectory; it is the org profile precisely because of that path. Every
  community health file (`CONTRIBUTING.md`, `SECURITY.md`, `SUPPORT.md`,
  `CODE_OF_CONDUCT.md`, `GOVERNANCE.md`, `FUNDING.yml`, `ISSUE_TEMPLATE/`) goes
  at the repo root, not under `profile/` and not under a nested `.github/`.

## Editing the PR template

`PULL_REQUEST_TEMPLATE.md` is consumed by repos with wildly different stacks
(.NET, React, Optimizely CMS, Amarna Studio). Keep it stack-agnostic — no
project-specific commands, paths or tooling. Its HTML comments are guidance
addressed to the human opening the PR; they are meant to survive in the
template and be deleted by the author, so preserve them when editing.

Note the recursion hazard: when *you* open a PR in another org repo, this file
is the template you're filling in. When you edit it here, you're editing the
form, not filling it out.

Inheritance is server-side, so this file exists on disk **only in this repo**.
Searching another org repo's checkout for `PULL_REQUEST_TEMPLATE.md` correctly
finds nothing — that is not a missing template. Nor does GitHub apply it to a
PR created through the API; only a human opening a PR in the browser gets the
prefill. To follow the template from anywhere else, fetch it:

```
curl -s https://raw.githubusercontent.com/amarnaorg/.github/main/PULL_REQUEST_TEMPLATE.md
```

## Editing the org profile

`profile/README.md` is public-facing marketing copy with a deliberate voice —
declarative, concrete, numbers over adjectives, em-dash asides, no corporate
hedging. Match it rather than neutralizing it. It contains real founder names,
emails, links and claimed metrics: never invent, round or "improve" a metric,
a credential or a bio detail. If a claim needs updating, ask rather than guess.

The file still carries GitHub's original scaffold comment at the top; that's
intentional-looking clutter, not content to expand on.

## Verification

There is nothing to build or run. Verify by reading the rendered Markdown —
tables, anchors and the `<div align="center">` blocks are the parts that
actually break. GitHub's org profile page renders a restricted subset of HTML,
so prefer plain Markdown plus the alignment divs already in use over new raw
HTML.

## Git

Work on the assigned feature branch and push with `git push -u origin <branch>`.
Open a PR only when explicitly asked.
