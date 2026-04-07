# Concept

**A remote is simply a copy of repo stored somewhere else: in this case, GitHub.**

---

## Remotes in Git

Git works offline first, and everything (add, commit, branch) is done locally.

Actions when remote is required:

Backing up work `git push`

Sharing with others `git push`

Getting changes from others
`git pull`

Working from another computer `git clone`

# Commands about Remote

## Add a Remote

```bash
git remote add origin <url>
```

Giving this GitHub URL a nickname 'origin'.

## View remotes

```bash
git remote -v                               # see all remotes and their URLs
```

Output:
origin https://github.com/yourname/your-repo.git (fetch)
origin https://github.com/yourname/your-repo.git (push)

## Fix a wrong URL

```bash
git remote set-url origin <new-url>         # update existing remote URL
```

## Rename a remote

```bash
git remote rename origin newname            # rename origin to something else
```

## Delete a remote

```bash
git remote remove origin                    # disconnect from GitHub completely
```
