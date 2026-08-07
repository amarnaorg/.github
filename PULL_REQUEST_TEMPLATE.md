<!--
Amarna's shared pull request template.

It lives in amarnaorg/.github and is inherited by every repo in the org that
doesn't define its own. To override it for one repo, add a
PULL_REQUEST_TEMPLATE.md to that repo's root, .github/ or docs/ folder.

Delete any section that doesn't apply. A short, honest PR beats a padded one.
-->

## What and why

<!-- One or two sentences. What changes, and what problem it solves. Link the issue: Closes #123 -->

## How it works

<!--
The reviewer's shortcut into the diff. Worth writing when the change is more
than mechanical: the approach you took, anything you tried first and dropped,
and the files where the real decisions live. Skip it for a copy tweak.
-->

## How to verify

<!--
Steps a reviewer can actually follow — branch, command, URL, what to look for.
"CI is green" is not verification of behavior.
-->

1.

## Screenshots

<!-- UI changes only. Before and after, and every breakpoint or theme you touched. -->

## Risk and rollback

<!--
Anything that makes this more than a code change: migrations, env vars or
secrets to add, config or infra changes, a deploy that has to happen in a
certain order, data that can't be un-changed. Say how to back it out.
Write "None — safe to revert" when that's the truth.
-->

## Checklist

- [ ] Ran it myself and watched it work — not just the tests
- [ ] Build, types and lint pass locally
- [ ] Tests or docs updated where the change warrants it
- [ ] No secrets, keys, tokens or customer data in the diff
- [ ] Scoped to one thing; unrelated cleanup pulled out
