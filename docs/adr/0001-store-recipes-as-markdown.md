# ADR 0001: Store recipes as Markdown files

- **Status:** Accepted
- **Date:** 2026-09-24
- **Deciders:** @liaoh4

## Context
We need a place to store team recipes.
The team is small, and most people know Markdown.
We want every new recipe to be reviewed before it goes live.

## Options considered
1. **Markdown files in the repo**
2. **A database with a web form**
3. **A shared Google Doc**

## Decision
We choose option 1. Each recipe is a Markdown file in the repo.

## Consequences
**Good**
- Every recipe goes through a PR, so someone reviews it.
- Git keeps the full history of each recipe.
- We need no server and no database.

**Bad**
- Search is harder. We'll revisit this in v2.
- Contributors need a GitHub account and basic Git skills.
