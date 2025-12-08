---
theme: neversink
transition: fade
routerMode: hash
lineNumbers: true
record: true
---

# Branch protection + required checks

Guardrails that stop risky merges, keep history clean, and ensure automation runs before code ships.

---
layout: center
---

# Why protect branches

- Prevents accidental force-pushes or deletions of `main` branches
- Ensures code is reviewed, tested, and policy-compliant before merge
- Keeps history linear, making blame, bisects, and rollbacks faster

---
layout: full
---

# Core protection rules (GitHub)

| Rule | Impact |
| --- | --- |
| Require pull request | Blocks direct pushes; enforces review workflow |
| Required reviews | Min approvals + CODEOWNERS for sensitive areas |
| Required status checks | CI gates (test, lint, SAST, coverage) must succeed |
| Require up-to-date branches | Forces rebase/merge with latest `main` before merge |
| Block force pushes/deletes | Preserves history; prevents loss of audited commits |
| Signed/verified commits | Assures authorship (GPG/Sigstore) |

---
layout: center
---

# Required status checks 101

- GitHub treats each CI job/status context as a check; only **required** ones gate merges
- Name checks clearly (`ci/test`, `ci/lint`, `security/snyk`)
- Mark flaky/non-critical jobs optional; failing optional checks should not block merges
- Prefer a single composite workflow that fails fast and reports granular steps

---
layout: center
---

# Example policy for `main`

- Require PR; disallow bypass except admins (sparingly)
- Min 1–2 approvals; CODEOWNERS for critical paths (security, infra, payments)
- Required checks: `ci/build`, `ci/test`, `ci/lint`, `security/deps`, `security/secrets`
- Require up-to-date before merge; enable auto-merge to streamline
- Block force-push/delete; require signed commits
- Enforce linear history (squash or rebase), no merge commits on long-lived branches

---
layout: full
---

# Setting it up (classic rules)

1) Repo Settings → Branches → Add classic branch protection rule
2) Branch name pattern: `main`
2) Tick: Require pull request, require approvals, dismiss stale reviews on new commits
4) Tick: Do not allow bypassing the above settings
