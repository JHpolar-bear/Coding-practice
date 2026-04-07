**Git rebase moves your commits on top of another branch — keeping history clean and linear.**

---

**The problem it solves**

When you branch off main and main gets new commits, your branch falls behind:

```
main:    A --- B --- C

feature:      A --- B --- X --- Y
```

Merging creates a messy "merge commit":

```
main:    A --- B --- C --- M (merge commit)
                      \   /
feature:          X --- Y
```

Rebasing replays your commits on top of the latest main — no merge commit:

```
main:    A --- B --- C --- X --- Y
```

Clean, linear history.

---

**Basic rebase workflow**

```bash
git switch feature-login          # go to your feature branch
git rebase main                   # replay your commits on top of main
git switch main                   # go back to main
git merge feature-login           # fast forward merge (clean)
```

---

**Interactive rebase — rewrite history**

Lets you edit, squash, reorder, or delete commits before merging.

```bash
git rebase -i HEAD~3              # edit last 3 commits
```

Opens an editor showing your commits:

```
pick a1b2c3 Add login page
pick b2c3d4 Fix typo
pick c3d4e5 Add validation
```

Change `pick` to:

```
pick a1b2c3 Add login page
squash b2c3d4 Fix typo        # squash combines this into commit above
pick c3d4e5 Add validation
```

This squashes the typo fix into the login commit — cleaner history.

---

**Rebase vs Merge:**

|            | Merge                                    | Rebase                          |
| ---------- | ---------------------------------------- | ------------------------------- |
| History    | Shows all commits including merge commit | Clean linear history            |
| Safety     | Always safe                              | ⚠️ Never rebase shared branches |
| Use case   | Merging finished features                | Keeping branch up to date       |
| Complexity | Simple                                   | More advanced                   |

---

**⚠️ The golden rule of rebase**

**Never rebase a branch that others are working on.** Rebase rewrites commit history — if someone else has your branch, their history breaks.

```bash
# SAFE — only you use this branch
git rebase main

# DANGEROUS — others are using this branch
git rebase main    # ⚠️ never do this on shared branches
```

---

**When to use rebase:**

```bash
# Keep your feature branch up to date with main
git switch feature-login
git rebase main

# Clean up messy commits before opening a PR
git rebase -i HEAD~3

# Never rebase main itself
```
