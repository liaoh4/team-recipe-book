# Design: Team Recipe Book v1.0

- **Status:** Draft
- **Author:** @liaoh4
- **PRD:** [prd.md](prd.md)
- **Requirement:** #4

## Overview
Recipes live as Markdown files in the repo.
A Python script reads them and builds an index page.

## Directory structure
```
recipes/
  breakfast/
    fluffy-pancakes.md
  main/
  dessert/
  drinks/
scripts/
  build_index.py
RECIPES.md          # generated index page
```

## Recipe file format
Each recipe starts with a YAML front matter block.
The script reads the fields from it.

```markdown
---
name: Fluffy Pancakes
category: breakfast
---

## Ingredients
- 2 cups flour
- 2 eggs

## Steps
1. Mix the flour and eggs.
2. Cook on a hot pan.
```

## Rules
- File names use lowercase letters and hyphens, such as `fluffy-pancakes.md`.
- The `category` field must match the folder name.
- Each recipe belongs to exactly one category.

## Index page
`scripts/build_index.py` scans the `recipes/` folder and writes `RECIPES.md`.
The index groups recipes by category and links to each file.

## Validation
A GitHub Actions check runs on every PR.
It fails when a recipe misses a required field.

## Decisions
- [ADR 0001: Store recipes as Markdown files](adr/0001-store-recipes-as-markdown.md)
