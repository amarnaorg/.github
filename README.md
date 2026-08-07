# amarnaorg/.github

Org-wide defaults for every repository under [@amarnaorg](https://github.com/amarnaorg).

| Path | What it does |
| --- | --- |
| `profile/README.md` | The org profile page shown at github.com/amarnaorg |
| `PULL_REQUEST_TEMPLATE.md` | Default pull request template, inherited by every repo in the org |

## How inheritance works

GitHub falls back to this repository whenever a repo doesn't define a
[community health file](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file)
of its own. A repo overrides a default by adding its own copy of the file in
its root, `.github/` or `docs/` folder — nothing here needs to change for that.

This repository has to stay **public** for the defaults to apply; a private
`.github` repo is ignored, including by the org's private repos.

## Why the template isn't in your checkout

The inheritance is server-side. GitHub never copies these files into the other
repos, so nothing under `amarnaorg/amarna` — or any other org repo — will ever
have a `PULL_REQUEST_TEMPLATE.md` on disk. Looking for one there and finding
nothing is the expected result, not a broken setup.

Two consequences worth knowing:

- The template prefills the PR body only when a **human opens the PR in the
  browser**. A PR created through the API or `gh` gets whatever body the caller
  passes, and no template.
- Anything automated that wants to follow the template has to fetch it:

  ```
  curl -s https://raw.githubusercontent.com/amarnaorg/.github/main/PULL_REQUEST_TEMPLATE.md
  ```

  Fill in the sections and pass the result as the PR body. A repo that would
  rather have the file locally should add its own copy, which then overrides
  this one for that repo.

Other files GitHub will pick up from here if we add them: `CONTRIBUTING.md`,
`SECURITY.md`, `SUPPORT.md`, `CODE_OF_CONDUCT.md`, `GOVERNANCE.md`,
`FUNDING.yml`, and an `ISSUE_TEMPLATE/` folder.
