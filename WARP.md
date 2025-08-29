# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

This is an Astro-based static website for a XV Años (quinceañera) invitation. The project creates a single-page invitation with RSVP functionality using Google Forms integration and includes background music.

## Essential Commands

### Development
```bash
npm run dev           # Start development server (typically on port 4321)
npm run build         # Build for production
npm run preview       # Preview production build locally
```

### Package Management
```bash
npm install           # Install dependencies
npm update            # Update dependencies
```

## Architecture

### Project Structure
- `src/pages/index.astro` - Main invitation page (single page application)
- `src/styles/` - CSS styling with both Tailwind and custom CSS
  - `global.css` - Tailwind imports and global styles
  - `main.css` - Custom component styles and animations
- `public/vals.mp3` - Background audio file
- Configuration files for Astro, Tailwind CSS, and PostCSS

### Tech Stack
- **Astro 5.x** - Static site generator and main framework
- **Tailwind CSS 4.x** - Utility-first CSS framework
- **PostCSS** - CSS processing with autoprefixer
- **Google Forms** - RSVP form submission handling

### Key Architectural Decisions
1. **Single Page Design**: The entire invitation is contained in `index.astro` with embedded HTML, styles, and form
2. **Hybrid Styling**: Combines Tailwind utilities with custom CSS for specific design elements
3. **External Form Processing**: Uses Google Apps Script for RSVP form submissions
4. **Auto-playing Audio**: Background music starts automatically when page loads

### CSS Configuration Notes
- There are two Tailwind config files (`tailwind.config.cjs` and `tailwind.config.js`) - the `.cjs` file appears to be the main configuration
- PostCSS is configured to use the new `@tailwindcss/postcss` package for Tailwind 4.x compatibility
- Custom animations and styling are handled in `main.css` with a blue color scheme (`#002b5b`, `#004aad`)

### Form Integration
The RSVP form submits to a Google Apps Script endpoint. Form fields:
- `entry.nombre` - Family name
- `entry.personas` - Number of people attending  
- `entry.mensaje` - Optional message

### Development Notes
- The project uses ES modules (`"type": "module"` in package.json)
- Site configuration points to `https://tu-dominio.com` (placeholder domain)
- Audio file should be placed in the `public` directory to be served statically
