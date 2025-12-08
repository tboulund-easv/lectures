---
theme: neversink
transition: fade
routerMode: hash
lineNumbers: true
record: true
---

# Pull requests in GitHub

How PRs enable collaboration, quality gates, and delivery flow in a DevOps pipeline.

---
layout: center
---

# What a pull request is

- A proposed set of changes from a branch to be merged into a base branch
- Bundles code, context, discussion, checks, and approvals in one place
- Acts as a **control point** for quality, security, and compliance before code ships

---
layout: center
---

# Why DevOps cares

- Enables trunk-based flow with safe, incremental changes
- Adds automated gates (tests, lint, security, coverage) before merge
- Creates audit trail: who reviewed, what changed, when it shipped
- Drives collaboration and shared ownership across engineering, QA, ops, and security

---
layout: full
---

# Typical PR lifecycle

<v-clicks>

1) Create feature/fix branch from `main`
2) Commit small, scoped changes; push and open PR with context
3) CI runs: build, test, lint, scan
4) Reviewers give feedback; author updates branch
5) Required checks + approvals pass; branch is up to date
6) Merge

</v-clicks>

---
layout: center
---

# Branching and scope

- Prefer short-lived branches tied to a single ticket/issue
- Keep PRs small: fast to review, easy to roll back
- Name branches clearly: `feature/payment`, `fix/login-bug`
- Link to issues and projects for traceability

---
layout: full
---

# Anatomy of a good PR

<style scoped>
  td, th { padding: 6px 8px; }
</style>

| Element | Purpose |
| --- | --- |
| Title | Clear intent and scope (`feat: add payment retries`) |
| Description | What changed, why, and how to test |
| Checklist | Tick boxes for tests run, docs updated, migrations noted |
| Reviewers | Right people for code, security, product impact |
| Labels | Categorize (feature, bug, breaking-change, security) |
| CI checks | Build, unit/integration tests, lint, SAST/DAST, coverage |

---
layout: center
---

# Author expectations

- Keep diffs minimal; split unrelated changes
- Provide context, screenshots, logs, and rollout notes
- Mark breaking changes and migration steps
- Draft state for WIP; ready-for-review when stable

---
layout: center
---

# Reviewer expectations

- Check correctness, tests, security, and operational impact
- Ask for clarifications; suggest, don't demand
- Approve only when checks pass and risk is understood
- Use blocking comments sparingly and precisely

---
layout: full
---

# Description template (GitHub)

```md
## Summary
- What changed?
- Why now?

## Testing
- [ ] Unit
- [ ] Integration
- [ ] E2E
- [ ] Manual steps (add commands)

## Risks & rollout
- Breaking changes? Migrations? Feature flags?
```

---
layout: full
---

# Automation in the pipeline

- Run CI on `pull_request` events: build, test, lint, type-check
- Security gates: dependency scanning, secret scanning, SAST
- Coverage thresholds and flaky-test detection
- Auto-assign reviewers and code owners
- Preview environments for UI/API validation



---
layout: center
---

# Metrics and anti-patterns

- Ignoring feedback and not addressing comments from reviewers
- Submitting large PRs that are difficult to review
- Failing to run tests before opening a PR
- Merging PRs without required approvals or passing checks
- Not providing sufficient context or documentation for changes (conventional commits help here)

---
layout: center
---

# Key takeaways

- PRs are the quality and collaboration hub in GitHub
- Automate everything repeatable; keep humans on design and risk
- Small, well-scoped, well-described PRs ship faster and safer
