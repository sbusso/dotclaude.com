# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview
This is a static website for ".claude" - a curated directory of Claude Code tools, configurations, and resources. The site showcases CLAUDE.md templates, MCP integrations, and workflow configurations for the Claude Code community.

## Architecture
- **Static HTML site** with 3 main pages: index.html (homepage), configs.html (CLAUDE.md templates), tools.html (MCP servers)
- **CSS framework**: Tailwind CSS via CDN
- **Custom styling**: CSS variables for Claude brand colors and animations
- **Interactive filtering**: JavaScript for category-based content filtering
- **Responsive design**: Mobile-first approach with responsive grid layouts

## Development Commands
This is a static site with no build process. Serve locally with:
```bash
# Python
python -m http.server 8000

# Node.js
npx serve .

# PHP  
php -S localhost:8000
```

## File Structure
- `index.html` - Homepage with hero section and feature overview
- `configs.html` - CLAUDE.md template gallery with filtering
- `tools.html` - MCP server directory with categorization
- Custom CSS variables define the Claude brand color palette
- JavaScript handles interactive filtering functionality

## Content Guidelines
- Maintain Claude brand consistency using the defined color variables
- Keep external links functional and up-to-date
- Ensure responsive design works across all screen sizes
- Use semantic HTML structure for accessibility