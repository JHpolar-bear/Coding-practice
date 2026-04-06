# Git Remote Commands

## Overview

These three commands manage the flow of code between your **local machine** and **GitHub**.

```
Your Computer                     GitHub
─────────────                     ──────
local repo    ──git push──►   remote (origin)
              ◄──git pull──
              ◄──git fetch──
```

---

## git push

Uploads your local commits to GitHub.

```bash
git push                    # push to default remote
git push -u origin main     # first push, sets default
git push origin main        # push to specific branch explicitly
```

> ⚠️ Always commit before pushing — push only sends commits, not unsaved changes.

---

## git pull

Downloads the latest changes from GitHub and **immediately applies** them to your local files.

```bash
git pull                          # download and apply changes
git pull origin main              # pull from specific branch
git pull --rebase origin main     # pull with cleaner history
```

`git pull` is actually two commands in one:

```bash
git fetch + git merge
```

> ✅ Always pull before starting work each day to get the latest changes.

---

## git fetch

Downloads the latest changes from GitHub but **does not apply** them — lets you inspect first.

```bash
git fetch origin                  # download changes
git status                        # see if you are behind
git log origin/main --oneline     # inspect what changed
git merge origin/main             # apply when ready
```

> 💡 Think of fetch as looking at your mail without opening it.

---

## Comparison

| Command     | Downloads | Applies to local files | Safe              |
| ----------- | --------- | ---------------------- | ----------------- |
| `git fetch` | ✅        | ❌                     | ✅ Very safe      |
| `git pull`  | ✅        | ✅                     | ✅ Safe           |
| `git push`  | ❌        | ❌                     | ⚠️ Affects GitHub |

---

## Daily Workflow

```bash
# Start of day — get latest changes
git pull

# End of day — send your changes to GitHub
git add .
git commit -m "Your message"
git push
```
