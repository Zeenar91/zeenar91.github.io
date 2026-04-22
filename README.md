# Zeenar Salim — Portfolio

A Jekyll portfolio site designed for GitHub Pages. Modern-minimal aesthetic: warm cream background, deep ink type, terracotta accent. Fraunces (display serif) paired with Inter (body sans).

## What's inside

```
├── _config.yml            # site settings, nav, social links
├── Gemfile                # Ruby dependencies for local preview
├── index.html             # home page
├── 404.html               # custom not-found page
├── _layouts/              # page templates (default, page, post, project, publication)
├── _includes/             # header + footer partials
├── _posts/                # blog posts (YYYY-MM-DD-slug.md)
├── _projects/             # portfolio entries (collection)
├── _publications/         # publication entries (collection)
├── about/                 # About page (Markdown)
├── portfolio/             # Portfolio listing (HTML)
├── publications/          # Publications listing (HTML)
├── services/              # Services page (Markdown)
├── speaking/              # Speaking page (Markdown)
├── cv/                    # CV page (Markdown)
├── blog/                  # Blog index (HTML)
└── assets/
    ├── css/main.css       # all styles
    └── images/            # drop profile photo, project thumbnails here
```

## Deploy to GitHub Pages (the fast path)

1. **Create a new GitHub repo.** Name it `yourusername.github.io` (replace `yourusername` with your actual GitHub username) — this reserves your primary GitHub Pages URL and requires no extra config.
2. **Push this folder's contents to the repo.** From the unzipped folder:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/yourusername/yourusername.github.io.git
   git push -u origin main
   ```
3. **Enable Pages.** In the repo on GitHub: **Settings → Pages**. Under *Build and deployment*, set **Source** to *Deploy from a branch*, **Branch** to `main`, **Folder** to `/ (root)`. Save.
4. **Wait 1–2 minutes**, then visit `https://yourusername.github.io`. That's it.

If you'd rather use a different repo name (e.g. `portfolio`), GitHub will serve it at `https://yourusername.github.io/portfolio/` — in that case, uncomment and set `baseurl: "/portfolio"` in `_config.yml`.

## Custom domain (optional)

1. Buy a domain, point a CNAME record at `yourusername.github.io`.
2. In **Settings → Pages**, add the domain under *Custom domain*. GitHub creates a `CNAME` file in the repo automatically.
3. Enable *Enforce HTTPS* once the cert provisions (takes a few minutes).

## Running locally (optional but useful)

You don't need this to deploy — GitHub builds the site for you. But if you want to preview changes before pushing:

```bash
# one-time setup (requires Ruby 3.x)
bundle install

# live-reloading local server at http://localhost:4000
bundle exec jekyll serve --livereload
```

If Ruby is a pain, skip local preview entirely. Just push to GitHub and watch it build.

## Editing content

### Text and bio
- **Home hero copy:** `index.html` (top of the file — the `hero` section)
- **About page:** `about/index.md`
- **Services:** `services/index.md`
- **CV:** `cv/index.md` (or drop a PDF at `assets/cv.pdf` and link it)
- **Speaking:** `speaking/index.md`

### Site settings (name, tagline, social links)
- Everything lives in `_config.yml`. Edit the `title`, `email`, `url`, and `social:` block. Restart the local server after editing (or just commit and push).

### Adding a project
Create a new file in `_projects/`, e.g. `_projects/my-project.md`:

```yaml
---
title: Project title
year: 2026
category: Research  # or "Program", "Data infrastructure", etc.
summary: One-sentence description for the card.
role: Your role
tools: Tools, methods, frameworks used
featured: true      # set to true to show on home page
tags: [tag-one, tag-two]
---

Write the full project story here in Markdown.
```

### Adding a publication
Create a file in `_publications/`:

```yaml
---
title: "Paper title"
authors: Salim, Z., &amp; Collaborator, A.
venue: Journal name
year: 2026
status: Under review   # optional
links:
  - label: DOI
    url: https://doi.org/...
  - label: Preprint
    url: https://...
---

Short abstract or summary.
```

### Adding a blog post
Create a file in `_posts/` named `YYYY-MM-DD-slug.md`:

```yaml
---
title: "Post title"
date: 2026-05-15
subtitle: Optional subtitle
---

Post content in Markdown.
```

## Design notes

- Colors, fonts, and spacing are defined as CSS custom properties at the top of `assets/css/main.css`. Change the `--accent`, `--cream`, or font stack once there and the whole site follows.
- The header is sticky with a subtle backdrop blur. The mobile nav toggle is inline JS at the bottom of `_includes/header.html` — no build step.
- Typography pairs Fraunces (a variable serif with optical sizing) with Inter. Both are loaded from Google Fonts in `_layouts/default.html`.
- No JavaScript framework, no build tooling beyond Jekyll. This keeps GitHub Pages builds fast and the site durable.

## What to do first

1. Edit `_config.yml` — put your real email, LinkedIn, Scholar, GitHub URLs in.
2. Drop a profile photo in `assets/images/` and add an `<img>` to the hero or About page.
3. Replace the sample projects, publications, and the "hello, new site" post with your real content.
4. Push to GitHub and enable Pages.

That's the whole thing.
