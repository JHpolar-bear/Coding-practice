**Git tags mark a specific commit as important — usually used to mark release versions.**

---

**Why use tags**

Commits have long hashes like `a1b2c3d` — hard to remember. Tags give meaningful names to important moments:

```
v1.0.0 — first release
v1.1.0 — added new feature
v2.0.0 — major update
```

---

**Two types of tags**

**Lightweight** — just a name pointing to a commit:

```bash
git tag v1.0.0
```

**Annotated** — includes message, date, author (recommended):

```bash
git tag -a v1.0.0 -m "First stable release"
```

---

**Create a tag**

```bash
git tag v1.0.0                        # lightweight tag on current commit
git tag -a v1.0.0 -m "First release"  # annotated tag on current commit
git tag -a v1.0.0 a1b2c3d -m "msg"   # tag a specific past commit
```

---

**View tags**

```bash
git tag                               # list all tags
git tag -l "v1.*"                     # list tags matching pattern
git show v1.0.0                       # see details of a tag
```

---

**Push tags to GitHub**

```bash
git push origin v1.0.0                # push a specific tag
git push origin --tags                # push all tags at once
```

⚠️ Tags are **not pushed automatically** with `git push` — you have to push them separately.

---

**Delete a tag**

```bash
git tag -d v1.0.0                     # delete local tag
git push origin --delete v1.0.0       # delete tag on GitHub
```

---

**Checkout a tag**

```bash
git checkout v1.0.0                   # travel to that version (read only)
git switch main                       # come back to present
```

---

**Versioning convention everyone uses:**

```
v1.0.0
  │ │ └── patch — bug fixes
  │ └──── minor — new features, backward compatible
  └────── major — breaking changes
```

| Change          | Example               | Version bump    |
| --------------- | --------------------- | --------------- |
| Bug fix         | Fixed login crash     | v1.0.0 → v1.0.1 |
| New feature     | Added dark mode       | v1.0.1 → v1.1.0 |
| Breaking change | Redesigned entire API | v1.1.0 → v2.0.0 |
