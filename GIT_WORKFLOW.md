# Git Workflow — Pushing New Code to GitHub

A quick reference for committing and pushing changes to your repository.

## Day-to-Day Workflow

Every time you make changes (new blog posts, updated content, config tweaks, etc.), follow these steps:

### 1. Check What Changed

```bash
git status
```

This shows which files have been added, modified, or deleted.

### 2. Stage Your Changes

```bash
# Stage everything
git add -A

# Or stage specific files
git add content/blog/my-new-post.md
git add hugo.yaml
```

### 3. Commit

Write a short, descriptive message about what you changed:

```bash
git commit -m "Add new blog post on reinforcement learning"
```

### 4. Push to GitHub

```bash
git push
```

That's it! GitHub Actions will automatically rebuild and redeploy your site.

---

## Common Scenarios

### Adding a New Blog Post

```bash
hugo new content blog/my-new-post.md
# Edit the file, set draft: false when ready
git add -A
git commit -m "Add blog post: My New Post"
git push
```

### Updating Site Configuration

```bash
# Edit hugo.yaml
git add hugo.yaml
git commit -m "Update site title and menu links"
git push
```

### Adding a New Project

```bash
hugo new content projects/my-project.md
# Edit the file
git add -A
git commit -m "Add project: My Project"
git push
```

### Deleting Content

```bash
rm content/blog/old-post.md
git add -A
git commit -m "Remove old blog post"
git push
```

---

## Useful Commands

| Command                  | Description                                  |
|--------------------------|----------------------------------------------|
| `git status`             | See what files have changed                  |
| `git diff`               | See exact line-by-line changes               |
| `git log --oneline -5`   | View last 5 commits                          |
| `git pull`               | Pull latest changes from GitHub              |
| `git stash`              | Temporarily save uncommitted changes         |
| `git stash pop`          | Restore stashed changes                      |

## Undoing Mistakes

### Undo the Last Commit (Keep Changes)

```bash
git reset --soft HEAD~1
```

### Discard All Uncommitted Changes

```bash
git checkout -- .
```

### Amend the Last Commit Message

```bash
git commit --amend -m "Corrected commit message"
```

---

## Tips

- **Commit often** — small, focused commits are easier to understand and revert if needed.
- **Pull before you push** — run `git pull` first if you edit files directly on GitHub to avoid conflicts.
- **Preview locally** — run `hugo server` and check `http://localhost:1313` before pushing to make sure everything looks right.
