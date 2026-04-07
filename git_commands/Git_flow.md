**GitHub Flow is a simple, consistent workflow for using Git and GitHub together.**

---

**The 6 steps:**

```
1. Pull latest main
2. Create a branch
3. Make changes and commit
4. Push branch to GitHub
5. Open a Pull Request
6. Merge and clean up
```

---

**Step by step:**

**1. Always start from the latest main**

```bash
git switch main
git pull                          # get latest changes before branching
```

**2. Create a branch for your work**

```bash
git switch -c feature-login       # name it after what you're building
```

**3. Make changes, add, commit**

```bash
# edit your files...
git add .
git commit -m "Add login page"
git commit -m "Add login validation"  # commit often, small commits
```

**4. Push branch to GitHub**

```bash
git push -u origin feature-login
```

**5. Open a Pull Request on GitHub**

- GitHub shows **"Compare & pull request"** banner — click it
- Write what you changed and why
- Request a review from a teammate
- Discuss, make changes if needed

**6. Merge and clean up**

```bash
# After PR is merged on GitHub:
git switch main
git pull                          # download the merged changes
git branch -d feature-login       # delete local branch
git push origin --delete feature-login  # delete remote branch
```

---

**Visualized:**

```
main ──► create branch ──► commits ──► push ──► PR ──► merge ──► main
  ▲                                                              │
  └──────────────────────────────────────────────────────────────┘
```

---

**Rules of GitHub Flow:**

| Rule                        | Why                                |
| --------------------------- | ---------------------------------- |
| `main` is always deployable | Never break main                   |
| Always work on a branch     | Keeps main clean                   |
| Commit often                | Small commits are easier to review |
| Open a PR early             | Get feedback sooner                |
| Never push directly to main | Always go through a PR             |

---

**The golden habit:**

Every single piece of work — no matter how small — follows the same loop:

```bash
git switch main && git pull           # start fresh
git switch -c your-feature           # branch
# work, add, commit...
git push -u origin your-feature      # push
# open PR on GitHub, merge, clean up
```

This keeps your codebase clean, your history readable, and your team happy.
