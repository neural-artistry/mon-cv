# CLAUDE.md — mon-cv

This file documents the project structure, conventions, and workflows for AI assistants (Claude Code and others) working in this repository.

## Project Overview

**mon-cv** is a personal CV/resume project for the GitHub user `neural-artistry`. The repository is currently in its initial state with no source files committed. This CLAUDE.md will be updated as the project evolves.

- **Repository**: `neural-artistry/mon-cv`
- **Purpose**: Personal curriculum vitae / resume

---

## Repository State

> **Note:** As of 2026-03-12, this repository contains no source code. The sections below describe conventions and expected structure to be applied once development begins.

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

## Expected Project Structure

Since this is a CV/resume project, the structure will depend on the chosen technology. Common patterns:

### Static HTML/CSS

```
mon-cv/
├── CLAUDE.md
├── index.html          # Main resume page
├── css/
│   └── style.css
├── assets/
│   ├── images/
│   └── fonts/
└── README.md
```

### Framework-based (e.g., Next.js, Astro, Nuxt)

```
mon-cv/
├── CLAUDE.md
├── package.json
├── src/
│   ├── components/
│   ├── pages/ (or app/)
│   └── styles/
├── public/
└── README.md
```

### JSON/Markdown data-driven

```
mon-cv/
├── CLAUDE.md
├── data/
│   └── resume.json     # Structured resume data (e.g., JSON Resume schema)
├── templates/
└── output/
```

Update this section once the actual structure is established.

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

Update this section with real commands once the stack is chosen.

```bash
# Install dependencies (if applicable)
npm install

# Start development server
npm run dev

# Build for production
npm run build

# Run linter
npm run lint
```

---

## Updating This File

Whenever a significant change is made to the project structure, tooling, or conventions:

1. Update the relevant section in this file.
2. Commit the change alongside the structural change it documents.

When AI assistants add new capabilities, frameworks, or notable patterns, they should reflect those changes here so future sessions start with accurate context.
