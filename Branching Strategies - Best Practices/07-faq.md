# 07 - FAQ

## Frequently Asked Questions about Branching Strategies

This section addresses common concerns and misunderstandings teams often have when choosing, implementing, or evolving their branching strategies.

---

### ❓ What branching strategy should we use?

**It depends.**
Choose a strategy that fits your team size, release cadence, and tooling. Here’s a quick guide:

| Use Case                | Recommended Strategy     |
| ----------------------- | ------------------------ |
| Fast deployment / CI/CD | GitHub Flow, Trunk-Based |
| Formal releases & QA    | Git Flow, GitLab Flow    |
| Multiple live versions  | Release Branching        |
| Feature experimentation | Trunk-Based with flags   |

---

### ❓ Can we mix strategies?

Yes — many teams adopt a **hybrid** approach. For example:

* Use GitHub Flow for daily work, but tag releases using Git Flow concepts.
* Use GitLab Flow with `main`, `staging`, and `production` plus hotfixes when needed.

Just be sure to **document and communicate** the rules clearly.

---

### ❓ How long should feature branches live?

**As short as possible.**
Long-lived branches are prone to merge conflicts and integration issues. Try to:

* Keep feature branches under a few days.
* Merge often from `develop` or `main` to stay in sync.
* Use feature flags if a feature isn’t complete but needs to be merged.

---
