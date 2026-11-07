# haba713.github.io

GitHub Pages **user site** for `https://haba713.github.io/`: a small home page listing haba713's
open source projects, plus root-level files that only work at the domain root (`robots.txt`,
search engine verification files).

## How it is built and deployed

- GitHub Pages "Deploy from a branch": branch `master`, folder `/ (root)`. GitHub's built-in Jekyll
  builds the site; there is no workflow in `.github/workflows/` and none is needed.
- Default theme (Primer); site title, description and URL in `_config.yml`.
- Plugins GitHub Pages enables by default: `jekyll-optional-front-matter` publishes every `.md`
  file, so repo-only Markdown files (`README.md`, `AGENTS.md`, `CLAUDE.md`) must stay in `exclude`.
- Project sites are separate repos served under `/<repo>/`, e.g. paku's mdBook docs at
  `https://haba713.github.io/paku/`, built and deployed from the `haba713/paku` repo.

## Files

| File                    | Purpose                                                             |
|-------------------------|---------------------------------------------------------------------|
| `index.md`              | home page: project list, one bullet per project                     |
| `_config.yml`           | Jekyll config: title, description, url, excluded files              |
| `robots.txt`            | allows all crawlers; one `Sitemap:` line per project sitemap        |
| `google*.html`          | Google Search Console verification for the root URL-prefix property |
| `README.md`             | repo description, not published                                     |

## Conventions

- Keep it small: plain Markdown pages, no custom layouts or extra gems unless needed.
- Adding a project: one bullet in `index.md` (docs link, one-line description, source link) and,
  if it has a sitemap, a `Sitemap:` line in `robots.txt`.
- Never delete or rename verification files (`google*.html`, `BingSiteAuth.xml`); search consoles
  re-check them.
- Branch `master`. Commits: conventional commits, single lowercase line, noun-first subject
  (`feat: robots.txt with paku sitemap`). Author `haba713 <haba713@gmail.com>` (set in the repo's
  local git config).
- Markdown files only, with `.md` extension; no extensionless `README`.
