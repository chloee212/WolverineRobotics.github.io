# WolverineRobotics.github.io

This repository powers the Wolverine Robotics website built with Jekyll and the Minima theme.

## Prerequisites
- Ruby (matching the version in `Gemfile`)
- Bundler (`gem install bundler` if not already installed)

## Run the Site Locally
1. Install dependencies:
   ```sh
   bundle install
   ```
2. Start the development server with live reload:
   ```sh
   bundle exec jekyll serve --livereload
   ```
3. Visit the site at `http://127.0.0.1:4000`.

## Production Build
Generate the static site output (mirrors GitHub Pages build):
```sh
bundle exec jekyll build
```
The compiled files live in `_site/` after the build.

## Helpful Checks
Run the Jekyll doctor to surface configuration or front matter issues:
```sh
bundle exec jekyll doctor
```

Page content lives under `_pages/`, long-form posts go inside `_blogs/`, and each page declares its own stylesheet under `assets/css/` via the front matter.
