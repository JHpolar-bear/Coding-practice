Here's every Git command you've learned so far, organized by category:

---

**Setup**

```bash
git init                          # start Git in a folder
git clone <url>                   # download a repo from GitHub
git remote add origin <url>       # link local repo to GitHub
git remote -v                     # check GitHub link
git remote set-url origin <url>   # fix wrong GitHub link
```

---

**Daily workflow**

```bash
git add .                         # stage all changes
git add filename.txt              # stage a specific file
git commit -m "message"           # save a snapshot
git push                          # upload commits to GitHub
git pull                          # download latest from GitHub
git push -u origin main           # first push, sets default
```

---

**Inspection**

```bash
git status                        # see what files changed
git diff                          # see exact line changes (unstaged)
git diff --staged                 # see exact line changes (staged)
git log                           # full commit history
git log --oneline                 # compact commit history
```

---

**Undo**

```bash
git restore filename.txt          # discard changes to a file
git restore --staged .            # unstage everything
git restore --staged filename.txt # unstage a specific file
```

---

**File operations**

```bash
git rm filename.txt               # delete file and stage deletion
git rm --cached filename.txt      # stop tracking file, keep it locally
git mv oldname.txt newname.txt    # rename a file
git mv filename.txt subfolder/    # move a file
```

---

**Configuration**

```bash
git config --global alias.st status          # create an alias
git config --global --list                   # see all config and aliases
git config --global --unset alias.st         # remove an alias
git config --global core.editor "code --wait" # set VS Code as default editor
```

---

**The 3 commands you use every single day:**

```bash
git add .
git commit -m "message"
git push
```
