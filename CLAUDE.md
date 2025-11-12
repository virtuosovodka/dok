# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal documentation site built with **MkDocs Material** theme. The site is:
- Deployed automatically to GitHub Pages when changes are pushed to `main`
- Managed entirely through Claude Code
- Served locally during development via Python's mkdocs serve

## Setup & Development

### Initial Setup
Before first use, initialize the project environment:
```bash
python3 -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
pip install mkdocs mkdocs-material
```

### Common Commands

**Start local development server:**
```bash
source .venv/bin/activate
mkdocs serve
```
The server runs at `http://127.0.0.1:8000/` and auto-reloads on file changes.

**Build static site:**
```bash
source .venv/bin/activate
mkdocs build
```
Output is generated in the `site/` directory.

**View site structure:**
```bash
cat mkdocs.yml
ls -la docs/
```

## Project Structure

```
.
├── README.md           # Project overview and workflow
├── mkdocs.yml          # MkDocs configuration (theme, nav, plugins)
├── docs/               # Documentation source files (Markdown)
│   ├── index.md        # Homepage
│   └── [topic pages]
├── site/               # Generated static HTML (gitignored)
├── .venv/              # Python virtual environment (gitignored)
└── CLAUDE.md           # This file
```

## Key Workflows

### Creating/Editing Documentation

1. Create or edit `.md` files in the `docs/` directory
2. Update the `nav` section in `mkdocs.yml` if adding new pages or sections
3. Test locally with `mkdocs serve`
4. Commit changes with `git add` and `git commit`
5. Push to main with `git push origin main` (GitHub Actions handles deployment)

### GitHub Pages Deployment

- GitHub Actions automatically builds and deploys on every push to `main`
- The workflow file should be in `.github/workflows/` (create if missing)
- Site is available at: `https://virtuosovodka.github.io/dok/`

## MkDocs Configuration

The `mkdocs.yml` file controls:
- **site_name**: The site title
- **theme**: Set to `material` with customization options
- **nav**: Navigation structure (links to docs pages)
- **plugins**: Extensions like search, social cards, etc.
- **markdown_extensions**: Syntax support (tables, code highlighting, etc.)

Common Material theme options include:
- `palette`: Color scheme (light/dark mode)
- `features`: Enable navigation tabs, search, etc.
- `font`: Custom fonts

## Important Notes

- The `site/` and `.venv/` directories are gitignored and not committed
- All content edits are made in `.md` files in `docs/`
- Configuration is centralized in `mkdocs.yml`
- Material theme provides built-in search, syntax highlighting, and responsive design
