# 02 - Common Branching Strategies

Modern software teams have adopted several branching strategies to help manage their development workflows. Each model suits different team sizes, release cadences, and operational requirements. Below are the most widely used strategies.

---

## 1. **Git Flow**

**Overview:**
A structured strategy designed for teams with a formal release process. It separates long-lived branches for `main`, `develop`, and temporary branches for features, releases, and hotfixes.

**Key Branches:**

* `main`: Production-ready code (stable releases).
* `develop`: Integration branch for completed features.
* `feature/*`: Individual feature branches off `develop`.
* `release/*`: Pre-release stabilization branches.
* `hotfix/*`: Urgent patches off `main`.

**Best For:**

* Teams with regular versioned releases
* Projects requiring staging environments

**Drawbacks:**

* Can be heavyweight and slow for fast-moving teams
* High merge overhead if feature branches live too long

---

## 2. **GitHub Flow**

**Overview:**
A lightweight, continuous delivery-friendly model used by GitHub and many agile teams.

**Key Concepts:**

* Only `main` is long-lived and always deployable.
* Features are developed in short-lived branches.
* Pull Requests (PRs) are opened for every change and reviewed before merging to `main`.
* CI/CD deploys from `main` after successful merges.

**Best For:**

* Continuous deployment pipelines
* Small, fast-paced teams or startups

**Drawbacks:**

* No built-in release or hotfix branches
* Less suited for managing multiple versions or long QA cycles

---

## 3. **GitLab Flow**

**Overview:**
A hybrid approach combining ideas from Git Flow and GitHub Flow. It provides flexibility by integrating environment-based branches (like `staging`, `production`) and optionally tags or release branches.

**Variants:**

* Environment-based branches (`main`, `staging`, `production`)
* Issue tracking and Merge Requests integrated with GitLab tools
* Optionally supports version tags or release branches

**Best For:**

* Teams using GitLab with integrated CI/CD
* Projects needing both continuous delivery and controlled releases

**Drawbacks:**

* Can be confusing due to multiple possible variants
* Requires clear internal policies to avoid ambiguity

---

## 4. **Trunk-Based Development**

**Overview:**
A minimalistic model where all developers work directly off a single branch, typically `main` or `trunk`. Changes are small, frequent, and integrated continuously.

**Key Practices:**

* Short-lived feature branches (often merged daily or within hours)
* Feature flags used to hide incomplete code
* Heavy reliance on automated testing and CI

**Best For:**

* High-performance DevOps teams
* Organizations deploying multiple times per day

**Drawbacks:**

* Requires mature CI/CD pipelines
* Demands discipline to avoid breaking main

---

## 5. **Release Branching (Standalone)**

**Overview:**
Used in long-term support or enterprise environments. Releases are tracked with dedicated long-lived branches, e.g., `release/1.0`, `release/2.0`.

**Best For:**

* Products with multiple maintained versions
* Enterprise software with extended support cycles

**Drawbacks:**

* High overhead of backporting fixes
* Slower to integrate changes across versions

---

## Choosing the Right Strategy

| Strategy          | Best For                         | Complexity | Supports CI/CD | Supports Versioning |
| ----------------- | -------------------------------- | ---------- | -------------- | ------------------- |
| Git Flow          | Formal release cycles            | High       | Moderate       | Yes                 |
| GitHub Flow       | Continuous delivery              | Low        | Yes            | No (requires tags)  |
| GitLab Flow       | Balanced, environment-based flow | Medium     | Yes            | Optional            |
| Trunk-Based       | High-speed deployments           | Low        | Yes            | No (feature flags)  |
| Release Branching | Multiple maintained versions     | Medium     | Moderate       | Yes                 |

---
