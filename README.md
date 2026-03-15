# Blog Poster

A minimal, bilingual blog built with Next.js 15 and Tailwind CSS 4. Fork it, edit one config file, and start writing.

## Quick Start

```bash
# 1. Fork or clone this repo
git clone <your-fork-url> my-blog && cd my-blog

# 2. Install dependencies
npm install

# 3. Configure your site
cp site.config.example.ts site.config.ts
# Edit site.config.ts with your name, description, and tagline

# 4. Start writing
npm run dev     # dev server on :3000
npm run build   # production build to /out
```

## Configuration

All site-wide settings live in **`site.config.ts`**:

```typescript
{
  name: "My Blog",              // site title & header
  description: "...",           // meta description
  tagline: "...",               // footer text
  ogImage: "/og-image.png",    // Open Graph image (relative path)
  url: "https://example.com",  // optional — enables full OG URLs
  cloudflareAnalyticsToken: "...",  // optional — omit to disable
}
```

## Features

- **Bilingual posts** — EN/ZH with client-side language toggle
- **Dark mode** — with localStorage persistence
- **Static export** — deploy anywhere (GitHub Pages, Vercel, Cloudflare Pages)
- **Single config file** — one file to customize everything
- **Cloudflare Analytics** — optional, only loads when token is set

## Writing Posts

Posts live in `content/` as markdown files with YAML frontmatter:

```
content/
├── hello-world.md       # English (primary)
└── hello-world.zh.md    # Chinese translation (optional)
```

### Frontmatter format

```yaml
---
title: "Hello World"
date: "2025-01-01"
spoiler: "A short description shown in the post list."
---

Your markdown content here.
```

## Deployment

The included GitHub Actions workflow (`.github/workflows/deploy.yml`) auto-deploys to GitHub Pages on push to `main`. For other platforms, use `npm run build` and deploy the `out/` directory.

## Stack

- **Framework:** Next.js 15 (static export)
- **Styling:** Tailwind CSS 4 + Typography plugin
- **Content:** Markdown with gray-matter + remark
