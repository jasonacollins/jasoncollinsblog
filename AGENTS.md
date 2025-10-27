# AGENTS.md

Technical guidance for AI agents working with this Quarto blog repository.

## Commands Reference

### Development Workflow

```bash
# Preview site with live reload (primary development command)
quarto preview

# Render entire site
quarto render

# Render single post
quarto render posts/post-name.qmd

# Check Quarto version
quarto --version
```

## Architecture

### Quarto Configuration (_quarto.yml)

Critical settings that affect how the site works:

- `execute.freeze: true` - Computational results are cached in `_freeze/` directory
- `execute.error: true` - Errors in R code are displayed but don't halt rendering
- `format.html.code-fold: true` - R code chunks are foldable by default
- `csl: apa-no-ampersand.csl` - Custom citation style (APA without ampersands)
- `format.html.grid.body-width: 600px` - Main content width

### Freeze Mechanism

This is critical to understand:

1. When `freeze: true`, R code execution results are cached in `_freeze/posts/post-name/`
2. Cached results are committed to git (not gitignored)
3. Code only re-executes when the source `.qmd` changes
4. To force re-execution: delete the corresponding `_freeze/` subdirectory
5. The `_freeze/` structure mirrors the post structure

### Post Structure

Posts are in the `posts/` directory. Use `.md` files by default, only use `.qmd` if the post requires R computations.

Typical structure:

```yaml
---
title: "Post Title"
author: "Jason Collins"
date: 2025-01-24 09:00:00+10:00
draft: false           # Set true to exclude from build
bibliography: references.bib
toc: true
---
```

**Date format**: Important to use `YYYY-MM-DD HH:MM:SS+10:00` format with timezone.

### R Code Execution

Posts can contain R code chunks with standard knitr syntax:

````markdown
```{r chunk-name, message=FALSE, warning=FALSE}
library(tidyverse)
# Code here
```
````

Common chunk options used in this blog:
- `message=FALSE` - Suppress package loading messages
- `warning=FALSE` - Suppress warnings
- Named chunks help with caching

### File Paths and References

- **Images**: Typically `img/post-slug/image-name.png` or stored in post directory
- **PDFs**: Stored in `pdfs/` directory
- **Citations**: Bibliography files referenced in frontmatter, use `@key` syntax
- **Internal links**: Use relative paths from site root

## Common Operations

### Creating a New Post

1. Create `posts/your-post-name.md` with frontmatter (use `.qmd` only if R computations needed)
2. Write content (with optional R chunks if using `.qmd`)
3. Run `quarto preview` to see live updates
4. When ready, `quarto render` to finalize

### Renaming a Post

When renaming a post file:

1. Rename the `.qmd` file in `posts/`
2. Check for corresponding `_freeze/posts/old-name/` directory
3. Rename freeze directory to match new post name
4. Update any internal links to the post
5. Re-render the site

### Modifying Post with Cached Results

If a post has frozen results in `_freeze/`:

- Editing the `.qmd` will trigger re-execution on next render
- To prevent re-execution, don't edit the file (edit related non-cached files instead)
- To force full re-execution, delete `_freeze/posts/post-name/`

## Output Directories

- `_site/`: Complete rendered site (regenerated on each build, don't edit directly)
- `_freeze/`: Cached computational outputs (committed to git)
- `.quarto/`: Quarto build cache (gitignored)

## Git Workflow

The repository tracks:
- Source `.qmd` files
- `_freeze/` cached results
- Configuration files
- Static assets (images, PDFs)

The repository ignores:
- `_site/` (build output)
- `.quarto/` (build cache)
- R session files (`.RData`, `.Rhistory`, etc.)

## Troubleshooting

### Post not updating after code changes

- Delete `_freeze/posts/post-name/` to force re-execution
- Check that R environment has required packages installed

### Images not displaying

- Verify image path is relative to the post or use absolute path from site root
- Check image file exists and extension matches

### Citations not rendering

- Ensure `bibliography: references.bib` in frontmatter
- Verify `.bib` file exists and has correct entries
- Check citation keys match between text and bibliography
