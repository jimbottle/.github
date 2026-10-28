# Contributing

Thanks for looking. These defaults apply to every repository under this account that does not carry its own CONTRIBUTING.md; they summarise sections 5 and 9 of the Raylytics Version Control Standard (`STANDARD.md` in the `raylytics` repo).

## Branch

- Branch from `main`, named `type/short-kebab` with one of the commit types below (`feat/webview-lift`, `fix/sso-button-creds-gate`).
- One logical change per branch. A branch unmerged after 30 days is finished, turned into an issue, or deleted.
- Never force-push `main`.

## Commits

- [Conventional Commits 1.0](https://www.conventionalcommits.org/en/v1.0.0/): `type(scope): subject`, a blank line, then a body that says why. Types: `feat`, `fix`, `perf`, `refactor`, `style`, `docs`, `test`, `build`, `ci`, `chore`, `revert`. `!` or a `BREAKING CHANGE:` footer marks an incompatible change.
- Subject at most 72 characters, imperative, no trailing period; body wrapped at 72; footers `Closes #12`, `Refs #34`.
- No AI bylines: no `Co-Authored-By: Claude`, no `Generated with` line. The commit-msg hook refuses them.
- Install the hooks once per clone: `pre-commit install --hook-type pre-commit --hook-type commit-msg`. Never use `--no-verify`.

## Pull requests

- Every change lands through a PR, squash-merged, with CI green. The PR title becomes the squash commit subject and must itself be a Conventional Commit subject.
- CI is the gate: the `pre-commit` and `test` checks must pass. There are no required reviewers.
- Fill in the PR template: what changed and why, how it was tested, and anything the reviewer should decide.

## Secrets

- Secrets never enter the tree: no `.env`, keystores, service-account JSON, private keys, or tokens in URLs. `.env.example` lists every variable with a placeholder.
- gitleaks runs in the pre-commit hook and in CI. If you find a secret in the history, report it privately (see SECURITY.md) rather than opening an issue.

## Reporting problems

Open an issue with the bug-report template, or a feature request with its template. Security problems go through SECURITY.md.
