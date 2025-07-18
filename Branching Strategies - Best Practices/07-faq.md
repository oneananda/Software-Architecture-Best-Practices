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

### ❓ Should we use merge or rebase?

* Use **merge** for team collaboration (PRs/MRs), as it preserves context and review history.
* Use **rebase** for local cleanup (before opening a PR) to keep a tidy commit history.

**Tip:** Never rebase shared branches unless you know what you’re doing.

---

### ❓ How do we manage hotfixes?

Depends on your model:

* **Git Flow**: Use `hotfix/*` branches off `main`.
* **GitHub Flow**: Patch on `main` and deploy immediately.
* **GitLab Flow / Release Branching**: Patch on `release/x.y` or `production`.

Always merge hotfixes back into both the active development branch and the release/production branch.

---

### ❓ What’s the difference between `main` and `master`?

Nothing functionally.
The Git community is moving toward using `main` as the default branch name to replace the legacy `master`. You can configure Git or hosting platforms to use either.

---

### ❓ How do we onboard new developers to our branching model?

* Document your branching strategy in the project’s README or a `CONTRIBUTING.md`.
* Use automation (CI, linters, branch protection) to reinforce rules.
* Pair new devs with experienced team members during their first few PRs.

---

### ❓ When should we tag a release?

* When deploying to production.
* When finalizing a release in `main` or `release/x.y` branches.
* Tags help track history and support rollbacks or patches.

Use semantic versioning (`v1.2.3`) for clarity.

---

### ❓ How do we manage branching in monorepos?

Same principles apply:

* Use consistent naming and short-lived branches.
* CI tools like Nx, Turborepo, or Lerna can scope builds/tests per package.
* Consider a trunk-based model with feature flags to avoid large, diverging branches.

---

### ❓ When should we change our branching strategy?

When your **current one is holding you back**. Signs include:

* Frequent merge conflicts
* Slow release cycles
* Inconsistent deployment processes
* Poor test coverage or QA visibility

Branching strategies should evolve with your **team maturity**, **tooling**, and **product lifecycle**.

---

## Final Word

> A branching strategy is a tool, not a rule. The best one is the one your team understands, follows, and can automate.

Keep it simple. Keep it documented. And keep it flexible.

---
