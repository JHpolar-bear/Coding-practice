**Branches let you work on new features or fixes without affecting your main code.**

---

**Create a branch**

```bash
git branch feature-login          # create a new branch
git checkout -b feature-login     # create AND switch to it immediately
git switch -c feature-login       # modern way to create and switch
```

---

**Switch between branches**

```bash
git checkout main                 # switch to main branch
git switch main                   # modern way to switch
git switch feature-login          # switch to another branch
```

---

**View branches**

```bash
git branch                        # list all local branches
git branch -r                     # list remote branches on GitHub
git branch -a                     # list all local and remote branches
```

---

**Merge a branch into main**

```bash
git switch main                   # go to main first
git merge feature-login           # merge feature branch into main
```

---

**Delete a branch**

```bash
git branch -d feature-login       # delete after merging
git branch -D feature-login       # force delete (not yet merged)
git push origin --delete feature-login  # delete branch on GitHub
```

---

**Push a branch to GitHub**

```bash
git push -u origin feature-login  # push branch to GitHub
```

---

**Typical branch workflow:**

```bash
git switch -c feature-login       # create and switch to new branch
# make changes, add, commit...
git add .
git commit -m "Add login feature"
git push -u origin feature-login  # push branch to GitHub
git switch main                   # go back to main
git merge feature-login           # merge into main
git branch -d feature-login       # delete branch, done
git push                          # push updated main to GitHub
```

---

**When to use which switch command:**

| Command           | Notes                               |
| ----------------- | ----------------------------------- |
| `git checkout -b` | Old way, still works everywhere     |
| `git switch -c`   | Modern way, cleaner and recommended |

---

**Golden rule:** Never work directly on `main` — always create a branch, do your work there, then merge back.
