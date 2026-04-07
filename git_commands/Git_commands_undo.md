These are all **undo/fix** commands — each for a different situation.

---

**git commit --amend — fix your last commit**

Use when you just committed but made a mistake — wrong message, or forgot to include a file.

```bash
# Fix the commit message
git commit --amend -m "Correct message here"

# Forgot to include a file
git add forgotten_file.txt
git commit --amend --no-edit      # --no-edit keeps the same message
```

⚠️ Only use this **before** `git push`. Amending after pushing causes problems on shared repos.

---

**git revert — undo a past commit safely**

Creates a **new commit** that undoes a previous one. Safe to use even after pushing.

```bash
git log --oneline                 # find the commit hash you want to undo
git revert a1b2c3d                # replace with your actual commit hash
```

This doesn't delete history — it adds a new "undo" commit on top. This is the **safe** way to undo on shared/team projects.

---

**git checkout — navigate to a past commit or branch**

```bash
git log --oneline                 # find the commit hash
git checkout a1b2c3d              # travel to that commit (read only)
git checkout main                 # come back to present
```

Think of it as a **time machine** — you can look at old code but you shouldn't edit anything while there. It puts you in "detached HEAD" state which just means you're not on any branch.

---

**When to use which:**

| Situation                                  | Command                                         |
| ------------------------------------------ | ----------------------------------------------- |
| Fix last commit message                    | `git commit --amend`                            |
| Forgot to add a file to last commit        | `git add file` + `git commit --amend --no-edit` |
| Undo a past commit (already pushed)        | `git revert <hash>`                             |
| Look at old code without changing anything | `git checkout <hash>`                           |
