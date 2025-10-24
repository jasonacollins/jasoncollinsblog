# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Documentation Structure

This repository uses a split documentation approach:

- **[README.md](README.md)** - Human-readable guide for developers
- **[AGENTS.md](AGENTS.md)** - Technical details and architecture for AI agents

**Please read both files before making changes to this repository.**

## Quick Reference

This is a Quarto blog. Essential commands:

```bash
# Preview with live reload (use this for development)
quarto preview

# Render entire site
quarto render

# Render single post
quarto render posts/post-name.qmd
```

## Key Points

1. **Freeze is enabled**: R code results are cached in `_freeze/` - understand this before modifying posts with computations
2. **Post format**: `.qmd` files in `posts/` directory with YAML frontmatter
3. **Never edit `_site/` directly**: It's auto-generated
4. **Cached results are committed**: The `_freeze/` directory is tracked in git

For complete details, see [AGENTS.md](AGENTS.md).
