# Documentation

Personal documentation site built with MkDocs Material and managed by Claude Code.

## Purpose

This documentation site will be maintained using Claude Code with the following features:

- **MkDocs Material Theme**: Modern, responsive documentation theme
- **GitHub Pages**: Automatic deployment on every push to main
- **Claude Code Management**: All site management done via Claude Code AI assistant
- **GitHub CLI Integration**: Repository operations handled by `gh` command
- **Local Development Server**: Testing via mkdocs serve in .venv virtual environment

## Workflow

1. Edit this README.md to describe documentation topics
2. Launch Claude Code in this directory
3. Run `/init` to create CLAUDE.md and initialize project structure
4. Claude Code will:
   - Create mkdocs.yml configuration
   - Set up docs/ directory structure
   - Create GitHub Actions workflow for deployment
   - Start local development server in .venv
   - Restart server after each commit for testing

## Topics to Cover

[Add your documentation topics here, for example:]

- Development environment setup
- Programming guides and tutorials
- Tool configurations
- Project notes and references

## Development

The local server runs at http://127.0.0.1:8000/ and automatically reloads when files change.

Claude Code manages the server lifecycle:
- Starts server in .venv on first build
- Kills and restarts server after commits
- Ensures clean state for testing changes
