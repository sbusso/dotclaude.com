# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview
Static website for ".claude" - a curated directory of Claude Code tools, configurations, and resources. Showcases CLAUDE.md templates, MCP integrations, and workflow configurations.

## Development Commands
No build process required. Serve locally with:
```bash
python -m http.server 8000
# or: npx serve .
```

## Architecture

### Pages
- `index.html` - Homepage with hero, features grid, and promotional sections
- `features.html` - Agentic coding features overview with category filtering
- `agents.html` - Comprehensive sub-agents documentation (configuration, built-in agents, examples)
- `plugins.html` - Plugin system documentation (structure, components, marketplaces)
- `hooks.html` - Lifecycle hooks documentation (events, configuration, examples)
- `commands.html` - Slash commands documentation (built-in, custom, frontmatter)
- `mcp.html` - Model Context Protocol documentation (installation, scopes, configuration)
- `skills.html` - Agent skills documentation (SKILL.md format, discovery, team sharing)
- `tools.html` - MCP server directory with category filtering
- `configs.html` - CLAUDE.md template gallery with category filtering

### Theming System
CSS variables in `:root` define light mode (default), `[data-theme="dark"]` defines dark mode. Key variables:
- `--bg-primary`, `--bg-secondary`, `--bg-surface` - backgrounds
- `--text-primary`, `--text-secondary`, `--text-muted` - text colors
- `--claude-primary` (#D97757) - brand accent color
- `--claude-dark` (#141413) - primary dark color

Theme toggle uses `localStorage.setItem('theme', ...)` and respects system preference on initial load.

### Card Components
- `features.html`: `.feature-card` with `data-category` attribute (core, agent, extension, workflow, integration, enterprise)
- `tools.html`: `.tool-card` with `data-category` attribute (development, database, web, productivity, ai, cloud, communication)
- `configs.html`: `.config-card` with `data-category` attribute (framework, language, workflow, template, command, project)
- Filtering via `filterFeatures(category)` / `filterTools(category)` / `filterConfigs(category)` JavaScript functions

### Tag System
Category tags use Tailwind's `@apply` directive:
- `.tag-core`, `.tag-agent`, `.tag-extension`, `.tag-workflow`, `.tag-integration`, `.tag-enterprise` (features.html)
- `.tag-development`, `.tag-database`, `.tag-web`, `.tag-productivity`, `.tag-ai`, `.tag-cloud`, `.tag-communication` (tools.html)
- `.tag-framework`, `.tag-language`, `.tag-workflow`, `.tag-template`, `.tag-command`, `.tag-project` (configs.html)

## Adding Content

### New Feature Card (features.html)
```html
<div class="feature-card bg-white/80 p-6 rounded-xl border border-claude-200 hover:shadow-lg transition-all duration-300" data-category="CATEGORY">
    <!-- w-12 h-12 icon, title, description, command/label, link -->
</div>
```
Categories: core, agent, extension, workflow, integration, enterprise

### New Tool Card (tools.html)
```html
<div class="tool-card bg-white/80 p-6 rounded-xl border border-claude-200 hover:shadow-lg transition-all duration-300" data-category="CATEGORY">
    <!-- w-10 h-10 icon, title, description, author, link -->
</div>
```
Categories: development, database, web, productivity, ai, cloud, communication

### New Config Card (configs.html)
```html
<div class="config-card bg-white/80 p-6 rounded-xl border border-claude-200 hover:shadow-lg transition-all duration-300" data-category="CATEGORY">
    <!-- w-10 h-10 icon, title, description, author, link -->
</div>
```
Categories: framework, language, workflow, template, command, project

## Guidelines
- Maintain Claude brand colors (use CSS variables, not hardcoded values)
- All pages must include dark mode support for new elements
- Category filters must match `data-category` attributes exactly