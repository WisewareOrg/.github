# WisewareOrg process

These requirements apply to every repository in WisewareOrg. Each repository's `CONTRIBUTING.md`
links here alongside its own contribution rules. Each requirement names the gate that enforces it.

## Branches, tickets and pull requests

### PROC-001 — Branch name

The head branch of a pull request shall be named `<type>_<number>-<name>`: `<type>` one of the
ticket types (PROC-010); `<number>` its issue's number, a positive integer with no leading zero;
`<name>` one or more words, each made up of lowercase letters and digits, joined by single
underscores.

Enforced by: [check-branch](https://github.com/WisewareOrg/wise-ci/tree/main/check-branch)

### PROC-002 — Exemptions

The default branch and branches whose names begin with `renovate/` are exempt from PROC-001 and
PROC-003–PROC-008.

Enforced by: [check-branch](https://github.com/WisewareOrg/wise-ci/tree/main/check-branch)

### PROC-003 — Open issue

A branch's number shall name an open issue — not a pull request — in the same repository.

Enforced by: [check-branch](https://github.com/WisewareOrg/wise-ci/tree/main/check-branch)

### PROC-004 — Type label

The branch's issue shall carry exactly one label from the ticket types (PROC-010), the one named by
the branch's type. Labels outside the ticket types are permitted.

Enforced by: [check-branch](https://github.com/WisewareOrg/wise-ci/tree/main/check-branch)

### PROC-005 — Milestone

The branch's issue shall carry an open milestone.

Enforced by: [check-branch](https://github.com/WisewareOrg/wise-ci/tree/main/check-branch)

### PROC-006 — Development link

A pull request shall have its head branch's issue among the issues recorded in its Development
field. Other linked issues are permitted.

Enforced by: [check-branch](https://github.com/WisewareOrg/wise-ci/tree/main/check-branch)

### PROC-007 — Default-branch parent

A pull request targeting the default branch shall come from a head branch whose issue has no parent
issue.

Enforced by: [check-branch](https://github.com/WisewareOrg/wise-ci/tree/main/check-branch)

### PROC-008 — Integration-branch parent

A pull request targeting a branch other than the default branch shall target a branch named per
PROC-001, and its head branch's issue shall be a sub-issue, in the same repository, of the target
branch's issue.

Enforced by: [check-branch](https://github.com/WisewareOrg/wise-ci/tree/main/check-branch)

### PROC-009 — Pull-request title

A pull-request title shall be a Conventional Commits subject (`type: subject` or `type(scope):
subject`, per `@commitlint/config-conventional`), and shall not be a `fixup!`, `squash!` or merge
subject.

Enforced by: [pr-title](https://github.com/WisewareOrg/wise-ci/tree/main/pr-title)

### PROC-010 — Ticket types

The ticket types are `task`, `bug`, `design` and `process`.

Enforced by: [check-branch](https://github.com/WisewareOrg/wise-ci/tree/main/check-branch)

## Repository settings

### PROC-011 — Repository floor

Each repository's settings shall meet at least those stated in
[`repository-floor.yml`](repository-floor.yml).

Enforced by: [repo-floor](https://github.com/WisewareOrg/wise-ci/tree/main/repo-floor)

### PROC-012 — Default-branch pull requests

Changes shall reach the default branch only by pull request.

Enforced by: [repo-floor](https://github.com/WisewareOrg/wise-ci/tree/main/repo-floor)

### PROC-013 — Default-branch deletion

The default branch shall not be deleted.

Enforced by: [repo-floor](https://github.com/WisewareOrg/wise-ci/tree/main/repo-floor)

### PROC-014 — Default-branch force-push

The default branch shall not be force-pushed.

Enforced by: [repo-floor](https://github.com/WisewareOrg/wise-ci/tree/main/repo-floor)
