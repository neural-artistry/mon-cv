# CLAUDE.md — mon-cv

This file documents the project structure, conventions, and workflows for AI assistants (Claude Code and others) working in this repository.

## Project Overview

**mon-cv** is a personal CV/resume project for the GitHub user `neural-artistry`. The repository is currently in its initial state with no source files committed. This CLAUDE.md will be updated as the project evolves.

- **Repository**: `neural-artistry/mon-cv`
- **Purpose**: Personal curriculum vitae / resume

---

## Repository State

> **Updated:** As of 2026-03-12, the project is a single-file static HTML CV/SPA deployed via GitHub Pages.

---

## Development Workflow

### Branch Strategy

- The `main` (or `master`) branch should always be stable and deployable.
- Feature work and AI-assisted changes must be done on dedicated branches.
- Branch naming for Claude Code sessions: `claude/<task-slug>-<session-id>`
- Never push directly to `main` without a pull request.

### Git Practices

```bash
# Create and switch to a feature branch
git checkout -b feature/<description>

# Commit with a clear, imperative message
git commit -m "Add work experience section to resume"

# Push with upstream tracking
git push -u origin <branch-name>
```

- Write commit messages in the imperative mood: "Add", "Fix", "Update", not "Added" or "Fixing".
- Keep commits focused on a single logical change.
- Do not commit build artifacts, secrets, or editor configuration files.

---

## Project Structure

Single-file static HTML SPA, deployed via GitHub Pages from the `master` branch root.

```
mon-cv/
├── CLAUDE.md
└── index.html          # Single-page CV application (all HTML/CSS/JS inline)
```

### Stack

- **Layout**: Tailwind CSS (CDN) — responsive sidebar/bottom-nav layout
- **Chart**: Chart.js (CDN) — radar chart for skills visualization
- **JS**: Vanilla JavaScript — tab navigation + master-detail experience panel
- **Hosting**: GitHub Pages (`master` branch, root directory)

### Deployment

The site is served via GitHub Pages. To update the live site, merge changes into `master`.

---

## Key Conventions (to be confirmed)

These are sensible defaults — override them in this file once the actual stack is chosen.

### Code Style

- Prefer semantic HTML for accessibility.
- Use relative units (`em`, `rem`, `%`) over fixed pixels in CSS.
- Keep JavaScript minimal; avoid heavy frameworks unless there is clear justification.

### Content Updates

- Resume data (experience, education, skills) should live in a single source of truth (e.g., a JSON file or a dedicated data layer) rather than scattered across markup files.
- Dates should use ISO 8601 format (`YYYY-MM`) in data files, formatted for display in templates.

### Secrets and Privacy

- Never commit personal contact details (phone number, home address) in plaintext if the repository is public.
- Use environment variables or a `.env` file (gitignored) for any deployment-specific values.

---

## Common Commands

No build step required — the project is a static HTML file.

```bash
# Preview locally (Python)
python3 -m http.server 8080

# Or with Node
npx serve .
```

---

## Updating This File

Whenever a significant change is made to the project structure, tooling, or conventions:

1. Update the relevant section in this file.
2. Commit the change alongside the structural change it documents.

When AI assistants add new capabilities, frameworks, or notable patterns, they should reflect those changes here so future sessions start with accurate context.
