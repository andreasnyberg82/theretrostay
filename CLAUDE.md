# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static single-page website for "Pod Reglami" - a mountain apartment rental in Ostrowsko, Poland (near Zakopane and the Tatras). The entire application is contained in a single `index.html` file with embedded CSS and JavaScript.

## Development

**No build process required** - this is a pure static HTML/CSS/JS website.

To develop locally, open `index.html` in a browser or serve with any static server:
```bash
python -m http.server 8000
# or
npx serve .
```

## Architecture

### Single-File Structure
All code lives in `index.html`:
- CSS styles in `<style>` block (uses CSS custom properties for theming)
- JavaScript in `<script>` block at end of body
- External dependencies loaded via CDN (Leaflet.js for maps, Google Fonts)

### Key Features

**Bilingual System (Polish/English)**
- Uses `data-lang-pl` and `data-lang-en` attributes on elements
- Language toggle persists preference to localStorage
- All user-facing text has both language versions inline

**Gallery Lightbox**
- Custom implementation with keyboard navigation (arrows, Escape)
- Images referenced: `01-cosy-room.jpeg` through `12-*.jpeg`

**Interactive Map**
- Leaflet.js with OpenStreetMap tiles
- Shows apartment location and nearby attractions (ski slopes, thermal baths)
- Coordinates: 49.4833°N, 20.0167°E (Ostrowsko)

**Form Handling**
- Booking form with date validation enforcing 2-night minimum stay
- No backend - form would need integration with actual booking service

### CSS Architecture
- Mobile-first responsive design with breakpoints at 768px and 1024px
- Color scheme via CSS variables: forest green, terracotta accents, cream backgrounds
- Scroll-triggered animations using Intersection Observer

## Business Details (for content updates)
- Pricing: 500 PLN/night, 2-night minimum
- Capacity: 4 adults + 2 children
- Key nearby attractions: Zakopane (25 min), Białka Tatrzańska ski (15 min), Chochołów thermal baths (20 min)
