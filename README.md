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

Other files GitHub will pick up from here if we add them: `CONTRIBUTING.md`,
`SECURITY.md`, `SUPPORT.md`, `CODE_OF_CONDUCT.md`, `GOVERNANCE.md`,
`FUNDING.yml`, and an `ISSUE_TEMPLATE/` folder.
