Git is a tool that saves snapshots of your code over time. Think of it like a detailed undo history for your entire project — except you control when each snapshot is taken, you can write a note explaining what changed, and you can go back to any snapshot at any time.

Without Git, the alternative is folders named `project-final`, `project-final-v2`, `project-ACTUALLY-final`. Every developer has done this. Git solves it permanently.First, let's build the mental model — what Git is actually doing when you run those commands.Click any box to explore it further. The key insight: Git has three places files can live on your computer — your working directory (raw edits), the staging area (what you've chosen to include in the next snapshot), and the repository (the permanent history). GitHub is just a copy of that history stored online.

Now, every command you'll ever use maps to one of those three transitions. Here's an interactive reference covering everything you need for the first few weeks:Click any command to expand the real example and explanation. Start with "Daily workflow" — that tab has the four-command loop you'll repeat every single session.

**Your exercise right now** — do this in order and you'll have Git working on a real project:

```powershell
# 1. Install Git for Windows (if you haven't)
winget install Git.Git

# 2. Restart your terminal, then configure your identity
git config --global user.name "Your Name"
git config --global user.email "you@email.com"

# 3. Go into your project folder and initialise Git
cd Desktop\my-first-project
git init

# 4. Create a file, stage it, and make your first commit
New-Item README.md
git add .
git commit -m "initial commit"
```

After that, create a free account on github.com, make a new repository, and follow the instructions it gives you to push — it's literally two commands that GitHub shows you on screen.

One thing that trips up almost everyone at the start: Git and GitHub are separate things. Git is the tool that runs on your computer. GitHub is the website that stores a copy online. You can use Git with no internet connection — GitHub is just the backup and sharing layer on top.

# Git commands

## Up to Github

1. git add: adding item to cart
   This tells Git "include this in my next save", but doesn't save anything permanently.
   This command only records files that have changed.

```bash
git add filename.txt # stage one specific file
git add folder/ # stage everything in a folder
git add . # stage ALL changed files in the project
```

2. git commit: checking out
   This permanently snapshots everything that has been staged.

```bash
git commit -m "Add login page"
# -m lets you write the message inline so always use it when starting out
```

Workflow be like:

```bash
# You edit login.py and signup.py

git add login.py             # stage just login.py
git commit -m "Fix login bug"

git add signup.py            # stage signup.py
git commit -m "Add email validation to signup"

```

3. git status: inspect what has changed
   Output classifies files into three categories: (1) changes not staged for commit; (2) changes to be committed; (3) untracked files that git doesn't know yet.

4. git diff: shows the details of change

5. git log: check the versions of the project

   # show one line only

   git log --oneline

   # show difference of changing

   git long -p <file name>

   # show limited numbers of commits

   git long -n <number of commits>

6. git rm: remove file from project, and record it
   # delete file or directory
   git rm <file name>
   git rm -r <directory name>
   # cache file
   git rm --cached

# Rabbit rabbit bear bear seal seal
