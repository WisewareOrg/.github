# WisewareOrg process

These requirements apply to every repository in WisewareOrg. Each project's `CONTRIBUTING.md` links
here and states only its own parameters — its set of ticket types. Each requirement names the gate
that enforces it.

## Branches, tickets and pull requests

### PROC-001 — Branch name

The head branch of a pull request shall be named `<type>_<number>-<name>`: `<type>` one of the
project's ticket types; `<number>` its issue's number, a positive integer with no leading zero;
`<name>` one or more words of lowercase letters and digits joined by single underscores.

Enforced by: [check-branch](https://github.com/WisewareOrg/wise-ci/tree/main/check-branch)

### PROC-002 — Exemptions

The default branch and branches whose names begin with `renovate/` are exempt from PROC-001 and
PROC-003–PROC-007.

Enforced by: [check-branch](https://github.com/WisewareOrg/wise-ci/tree/main/check-branch)

### PROC-003 — Open issue

A branch's number shall name an open issue — not a pull request — in the same repository.

Enforced by: [check-branch](https://github.com/WisewareOrg/wise-ci/tree/main/check-branch)

### PROC-004 — Type label

That issue shall carry exactly one label from the project's type set, the one named by the branch's
type. Labels outside the type set are permitted.

Enforced by: [check-branch](https://github.com/WisewareOrg/wise-ci/tree/main/check-branch)

### PROC-005 — Milestone

That issue shall carry an open milestone.

Enforced by: [check-branch](https://github.com/WisewareOrg/wise-ci/tree/main/check-branch)

### PROC-006 — Development link

A pull request from the branch shall have its issue among the issues recorded in its Development
field. Other linked issues are permitted; a mention in the pull-request body does not satisfy this.

Enforced by: [check-branch](https://github.com/WisewareOrg/wise-ci/tree/main/check-branch)

### PROC-007 — Parent issue

A pull request targeting the default branch shall come from an issue with no parent. A pull request
targeting any other branch shall target a branch named per PROC-001, and its issue shall be a
sub-issue of that branch's issue in the same repository.

Enforced by: [check-branch](https://github.com/WisewareOrg/wise-ci/tree/main/check-branch)

### PROC-008 — Pull-request title

A pull-request title shall be a Conventional Commits subject (`type(scope): subject`, per
`@commitlint/config-conventional`), and shall not be a `fixup!`, `squash!` or merge subject.

Enforced by: [commitlint](https://commitlint.js.org)
