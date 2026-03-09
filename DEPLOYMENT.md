# Deploying to GitHub Pages

This guide walks you through deploying your Hugo academic site to GitHub Pages using GitHub Actions.

## Prerequisites

- A GitHub account
- Git installed locally
- This repository cloned on your machine

## Step 1 — Create a GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Name it `academic-site` (or any name you prefer)
3. Set visibility to **Public** (required for free GitHub Pages)
4. **Do not** initialise with a README (you already have files locally)

## Step 2 — Update `baseURL`

Open `hugo.yaml` and update the `baseURL` to match your GitHub Pages URL:

```yaml
# If using a user/org site (yourusername.github.io):
baseURL: "https://yourusername.github.io/"

# If using a project site (yourusername.github.io/academic-site):
baseURL: "https://yourusername.github.io/academic-site/"
```

## Step 3 — Push to GitHub

```bash
cd academic-site
git add -A
git commit -m "Initial commit — Hugo academic site with PaperMod"
git branch -M main
git remote add origin https://github.com/yourusername/academic-site.git
git push -u origin main
```

## Step 4 — Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Under **Source**, select **GitHub Actions**
3. That's it — the included workflow (`.github/workflows/deploy.yml`) handles the rest

## Step 5 — Verify

After pushing, go to the **Actions** tab in your repository. You should see the "Deploy Hugo to GitHub Pages" workflow running. Once it completes:

- Visit `https://yourusername.github.io/academic-site/` (or your custom URL)
- Your site should be live! 🎉

## Custom Domain (Optional)

To use a custom domain like `yourname.com`:

1. In your repo → **Settings** → **Pages** → **Custom domain**, enter your domain
2. Add these DNS records at your domain registrar:

   | Type  | Name | Value                       |
   |-------|------|-----------------------------|
   | A     | @    | 185.199.108.153             |
   | A     | @    | 185.199.109.153             |
   | A     | @    | 185.199.110.153             |
   | A     | @    | 185.199.111.153             |
   | CNAME | www  | yourusername.github.io      |

3. Enable **Enforce HTTPS** in the Pages settings
4. Update `baseURL` in `hugo.yaml` to `https://yourname.com/`

## Local Development

To preview locally before pushing:

```bash
hugo server -D
# Open http://localhost:1313 in your browser
```

The `-D` flag includes draft posts. Remove it to see only published content.

## Adding New Content

```bash
# New blog post
hugo new content blog/my-new-post.md

# New project
hugo new content projects/my-new-project.md
```

Edit the generated file, set `draft: false` when ready, commit, and push.
