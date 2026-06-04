# AGENTS.md

## Project

Hugo static site (resume/CV) deployed to GitHub Pages at `https://nqvinh00.github.io/myprofile/`.

## Setup

```bash
git submodule update --init --recursive
# then just run hugo (no npm/node needed unless you add JS deps)
```

## Commands

| Action | Command |
|--------|---------|
| Dev server | `hugo server` |
| Build | `hugo --gc --minify` |
| Build (prod baseURL) | `hugo --gc --minify --baseURL "https://nqvinh00.github.io/myprofile/"` |

## Key files

- `hugo.toml` — **all site content** (personal info, experience, projects, etc.). Edit this file to update the resume. Markdown content files are not used.
- `.github/workflows/hugo.yaml` — CI/CD. Hugo 0.140.2 (extended). Deploys to GitHub Pages on pushes to `main`.
- `themes/hugo-profile` — git submodule (https://github.com/gurusabarish/hugo-profile).
- `static/` — images and `resume.pdf`.
- `content/index.md` — empty stub used by the theme's index layout.

## Important

- Theme is a submodule — always recurse on clone: `git clone --recursive` or `git submodule update --init --recursive`.
- `public/` is gitignored (CI generates it).
- No tests, no linter, no formatter config.
- CI timezone set to `Asia/Ho_Chi_Minh` (only relevant if you add date-dependent content).
- `markup.goldmark.renderer.unsafe = true` allows raw HTML in `hugo.toml` content strings.
