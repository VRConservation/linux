# AGENTS.md

MyST Markdown documentation site (mystmd), deployed to GitHub Pages.

## Layout

- All content is in `linux.md`; it must be listed under `project.toc` in `myst.yml` or it won't appear on the site.
- Site config (template, logo, nav links) is in `myst.yml`.
- Deployment: `.github/workflows/deploy.yml` builds with `myst build --html` and publishes to GitHub Pages on every push to `main`. There is no test/lint setup.

## Commands

```bash
npm install -g mystmd   # once
myst start              # dev server with live reload
myst build --html       # one-off build to _build/html
```

## Git gotcha: tracked build artifacts

`.gitignore` lists `_build/`, but thousands of files under `_build/` were committed before that, and **gitignore does not affect already-tracked files** — so `_build/site/*.json` etc. keep showing as modified. Same for `.ipynb_checkpoints/`.

Fix (run once, then commit):

```bash
git rm -r --cached _build .ipynb_checkpoints
git commit -m "stop tracking build artifacts"
```

Never re-add `_build/` contents; CI regenerates everything from source.
