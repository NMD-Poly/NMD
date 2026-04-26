***

# Repository Contribution Guidelines

Welcome to the team! To maintain a clean, professional, and conflict-free codebase, all developers must strictly adhere to the following branching and commit conventions.

## 1. Branching Strategy

We follow a strict Trunk-Based Development model. The `main` branch is **sacrosanct** (regarded as too important or valuable to be interfered with); it represents the production-ready state. **Never push directly to `main`.**

All development happens on short-lived, ephemeral branches. Once your work is tested and approved via a Pull Request (PR), it is squash-merged into `main`, and your branch is deleted.

### Branch Naming Convention
Branches must follow this format: `<type>/<issue-number>-<short-description>`

**Allowed Types:**
* `feat/` - for new features or significant logical additions.
* `fix/` - for bug fixes.
* `refactor/` - for code restructuring without changing behavior.
* `docs/` - for documentation updates.

**Examples:**
* ✅ `feat/12-jwt-auth-filter`
* ✅ `fix/45-db-connection-pool`
* ❌ `my-new-feature` *(Rejects: no type, no issue number)*
* ❌ `test-branch` *(Rejects: too vague)*

---

## 2. Commit Message Convention

We strictly enforce the [Conventional Commits 1.0.0](https://www.conventionalcommits.org/en/v1.0.0/) specification. This ensures our Git history is readable and easily parsed by automated release tools. Keep your commit descriptions **terse** (sparing in the use of words; concise and to the point).

### Commit Format
```
<type>(<scope>): <description>
```
[optional body]

### Allowed Types
* **feat:** A new feature for the user or application.
* **fix:** A bug fix.
* **docs:** Documentation only changes (e.g., updating README).
* **style:** Formatting, missing semi-colons, etc; no production code change.
* **refactor:** Refactoring production code (e.g., renaming a variable in a Java class).
* **test:** Adding missing tests, refactoring tests (e.g., JUnit/Mockito updates).
* **chore:** Updating build tasks, package manager configs (e.g., updating `pom.xml` dependencies).

### The Scope (Optional but Recommended)
The scope provides context for where the change happened in our Spring architecture.
* **Examples:** `controller`, `service`, `security`, `db`, `config`.

### The Description
* Must be in English.
* Use the imperative, present tense: "add" not "added" nor "adds".
* Do not capitalize the first letter.
* No dot (`.`) at the end.

### Real-World Java/Spring Examples
* **Adding a new endpoint:** `feat(controller): add registration endpoint for new users`
* **Fixing a database bug:** `fix(db): resolve lazy initialization exception in user entity`
* **Updating dependencies:** `chore(maven): update spring boot starter parent to 3.2.0`
* **Writing automated tests:** `test(service): add mockito tests for password validation logic`

---

## 3. The Development Workflow

**1. Sync your local repository:**
```bash
git checkout main
git pull origin main

**2. Create your feature branch:**
```bash
git checkout -b feat/88-user-profile-dto
```

**3. Write code and commit frequently:**
```bash
git add .
git commit -m "feat(dto): create UserProfile record"
```

**4. Push and open a Pull Request:**
```bash
git push -u origin feat/88-user-profile-dto
```

**5. Review & Merge:**
* Wait for GitHub Actions (CI) to pass successfully.
* Receive approval from at least one team member.
* Squash and Merge into `main`.
* Delete your feature branch.
