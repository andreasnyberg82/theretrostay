# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static single-page website for "Pod Reglami" (meaning "Under the Foothills" in Polish) - a mountain apartment rental in Ostrowsko, Poland (near Zakopane and the Tatras). The entire application is contained in a single `index.html` file with embedded CSS and JavaScript.

## Deployment

- **Repository:** https://github.com/andreasnyberg82/theretrostay
- **Live site:** https://andreasnyberg82.github.io/theretrostay/
- **Hosting:** GitHub Pages (auto-deploys on push to main)

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
- 15 images in `images/` folder with descriptive names (01-cosy-room.jpeg through 15-living-beds.jpeg)

**Interactive Map**
- Leaflet.js with OpenStreetMap tiles
- Shows apartment location and nearby attractions (ski slopes, thermal baths)
- Coordinates: 49.4833°N, 20.0167°E (Ostrowsko)

**Booking Form**
- Submits via AJAX to Formspree (endpoint: `https://formspree.io/f/xgozerdw`)
- Shows thank you message without page refresh
- Date validation enforcing 2-night minimum stay

### CSS Architecture
- Mobile-first responsive design with breakpoints at 768px and 1024px
- Color scheme via CSS variables: forest green (#1a3a2f), terracotta (#c17f59), cream (#faf8f5)
- Scroll-triggered animations using Intersection Observer

### Images
Located in `images/` folder:
- 01-cosy-room.jpeg through 15-living-beds.jpeg
- Original WhatsApp uploads also kept as backups

## Business Details (for content updates)
- Pricing: 500 PLN/night, 2-night minimum
- Capacity: 4 adults + 2 children
- Key nearby attractions: Zakopane (25 min), Białka Tatrzańska ski (15 min), Chochołów thermal baths (20 min)

## SEO & Social
- Favicon: SVG star logo (inline data URI)
- Open Graph image: `images/12-dining-xmas.jpeg`
- Meta description in Polish
