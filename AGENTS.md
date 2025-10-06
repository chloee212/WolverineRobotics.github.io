# Repository Guidelines

## Project Structure & Module Organization

- `_pages/` holds top-level markdown pages with YAML front matter powering navigation; update `_config.yml` `header_pages` when adding new content.
- `_blogs/` is reserved for long-form posts; name files `YYYY-MM-DD-topic.md` and set `layout: post`.
- `_layouts/` keeps custom Liquid templates; leave the placeholder `.gitkeep` until you add an override.
- `_config.yml` centralizes site metadata and navigation; treat URLs and header lists there as the single source of truth.
- `_site/` contains generated output; do not hand-edit files—refresh it via the build commands when needed.
- `Gemfile` and `Gemfile.lock` pin the Ruby toolchain; coordinate before running `bundle update` to avoid drift.

## Build, Test, and Development Commands

- `bundle install` installs the locked Jekyll toolchain.
- `bundle exec jekyll serve --livereload` builds and serves at `http://127.0.0.1:4000`, watching `_pages/` and `_blogs/` for changes.
- `bundle exec jekyll build` produces the production-ready `_site/`, mirroring the GitHub Pages build step.
- `bundle exec jekyll doctor` surfaces configuration or front matter issues; run before shipping structural changes.

## Coding Style & Naming Conventions

- Begin every content file with YAML front matter ordered as `layout`, `title`, `permalink`, then custom keys.
- Use hyphenated, lowercase filenames (e.g., `_pages/sponsor-pack.md`) and keep permalinks trailing with `/`.
- Prefer 2-space indentation for Markdown, YAML, and Liquid; keep Liquid tags inline for short logic snippets.
- Add `{% comment %}` blocks only when Liquid behavior is non-obvious; keep prose concise and action-oriented.

## Testing Guidelines

- Finish each change with `bundle exec jekyll build`; resolve warnings before pushing.
- While serving locally, click through updated pages to confirm navigation, metadata, and links render correctly.
- Validate new external links with `bundle exec jekyll doctor` or an external checker if issues persist.

## Commit & Pull Request Guidelines

- Write imperative, concise commits; follow `<type>: <summary>` as in `chore: delete default.html`.
- Keep commits scoped to a single logical change and rerun build commands before committing.
- Pull requests should explain intent, list affected pages, link issues, and include before/after screenshots for visual tweaks.
- Document any manual verification steps in the PR so reviewers can reproduce quickly.

## Content Workflow Tips

- New navigation items require both a `_pages/*.md` file and a matching entry in `_config.yml` `header_pages`.
- For drafts, set `published: false` in front matter and keep the file local until it is ready to ship.
