# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository status

This repository is currently **empty** — no commits, no source files, no configuration. The remote (`rueckerconsult/rueckerconsult.github.io`) has no default branch yet. The repository name follows GitHub's `<user>.github.io` convention, which means content pushed to the default branch will be published as a GitHub Pages site at `https://rueckerconsult.github.io/`.

Because there is no code to describe yet, the architecture, build, lint, and test sections of this document are intentionally blank. **Re-run `/init` once real content has been committed** so this file can be regenerated against the actual codebase (static HTML, Jekyll, Hugo, a JS framework, etc. — none of that is decided yet).

## Working on this branch

Per the harness instructions, all work in this session must be developed on the `claude/add-claude-documentation-gvddC` branch and pushed there. Do not push to other branches without explicit user permission. Do not open a pull request unless the user asks for one.

## When adding the first content

A few things worth knowing before the first real commit lands:

- **GitHub Pages publishing source.** For a `<user>.github.io` repo, Pages publishes from the default branch's root by default. If the user wants a different setup (e.g. publish from `/docs`, from `gh-pages`, or via a GitHub Actions workflow), confirm before restructuring — the choice constrains the directory layout.
- **Jekyll vs. plain static.** GitHub Pages auto-builds Jekyll sites unless a `.nojekyll` file is present at the root. If the user wants plain static HTML or a non-Jekyll generator (Hugo, Astro, Next export, etc.), add `.nojekyll` so underscore-prefixed paths aren't filtered out.
- **Custom domain.** A `CNAME` file at the repo root configures a custom domain. Don't add or remove one without confirmation.

## Commands

None yet — to be filled in once a build system exists.

## Architecture

None yet — to be filled in once source files exist.
