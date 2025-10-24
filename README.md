# Jason Collins Blog

A Quarto-based blog covering behavioural economics, data science, and artificial intelligence.

## Quick Start

### Prerequisites

- [Quarto](https://quarto.org/docs/get-started/) (version 1.8+)
- R (for posts with computational content)

### Development

```bash
# Preview the site locally (with live reload)
quarto preview

# Render the entire site
quarto render

# Render a single post
quarto render posts/post-name.qmd
```

## Project Structure

```
.
├── posts/              # Blog posts (.qmd files)
├── _site/              # Generated site (auto-generated)
├── _freeze/            # Cached computational results
├── _quarto.yml         # Site configuration
├── pdfs/               # PDF files
├── about.qmd           # About page
├── research.qmd        # Research page
└── subscribe.qmd       # Subscribe page
```

## Writing Posts

Create a new `.qmd` file in the `posts/` directory:

```yaml
---
title: "Your Post Title"
author: "Jason Collins"
date: 2025-01-24 09:00:00+10:00
draft: false
bibliography: references.bib  # Optional
toc: true                      # Optional
---

Your content here...
```

### Including R Code

Posts can include R code chunks:

````markdown
```{r chunk-name, message=FALSE, warning=FALSE}
library(tidyverse)
# Your analysis code
```
````

### Citations

Reference a bibliography file in the frontmatter and use pandoc citation syntax:

- In-text: `@author2024`
- Parenthetical: `[@author2024]`

## Configuration

Key settings in `_quarto.yml`:

- **Freeze execution**: Computational results are cached (only re-run when source changes)
- **Theme**: Cosmo with custom SCSS
- **Body width**: 600px
- **Citation style**: Custom APA without ampersands

## Publishing

The rendered site is in `_site/`. Deploy this directory to your web host.

Note: The `_freeze/` directory contains cached results and should be committed to version control.
