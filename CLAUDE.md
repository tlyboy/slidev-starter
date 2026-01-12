# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Slidev presentation project - a developer-focused presentation framework built on Vue 3 and Vite. Slides are written in Markdown with embedded Vue components, code highlighting, diagrams, and animations.

## Commands

```bash
# Install dependencies (uses pnpm)
pnpm install

# Start dev server at localhost:3030
pnpm dev

# Build for production (outputs to dist/)
pnpm build

# Export slides to PDF/PNG
pnpm export
```

## Architecture

- **slides.md** - Main presentation file with YAML frontmatter for configuration (theme, title, duration)
- **components/** - Vue 3 components usable directly in slides via `<ComponentName />`
- **pages/** - Additional markdown files that can be imported into slides using `src:` attribute
- **snippets/** - TypeScript code files for external code examples in slides

## Key Concepts

**Slide Separation**: Use `---` to separate slides in markdown files

**Frontmatter**: Each slide can have YAML frontmatter for per-slide configuration:

```md
---
layout: center
class: text-center
---
```

**Vue in Markdown**: Vue components and reactive code work directly in slides:

```md
<Counter :count="10" />

<script setup>
import { ref } from 'vue'
const count = ref(0)
</script>
```

**Styling**: Uses UnoCSS atomic classes (e.g., `flex="~"`, `m="auto"`, `border="~ main rounded-md"`)

**Code Blocks**: Support Shiki highlighting, line highlighting (`{2,3}`), TwoSlash, and Monaco editor integration

## Themes

Current theme is `seriph`. Theme is set in slides.md frontmatter. Available themes: `default`, `seriph`, and many community themes.
