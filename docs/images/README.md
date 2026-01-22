# ClaraVerse Branding & Assets

This directory contains branding assets and screenshots for the ClaraVerse README and documentation.

## Files

### Branding Assets
- `logo.png` - Official ClaraVerse logo (19KB)
- `logo-web.png` - Web-optimized logo from claraverse.space (19KB)
- `banner.png` - Clara mascot banner (134KB)
- `clara-mascot.png` - Clara welcome mascot character (2.6MB)

### Screenshots
- `screenshot-chat.webp` - Chat interface example
- `screenshot-agents.webp` - Multi-agent orchestration interface

## Usage

### In README.md
```markdown
![ClaraVerse Logo](docs/images/logo.png)
![Clara Banner](docs/images/banner.png)
```

### In Documentation
Reference images using relative paths:
```markdown
![Screenshot](../images/screenshot-chat.webp)
```

## Adding New Screenshots

To add new screenshots:

1. Take a screenshot of the feature at 1400px+ width
2. Optimize the image:
   ```bash
   # For PNG (use ImageMagick)
   convert screenshot.png -quality 85 -resize 1400x screenshot-optimized.png

   # For WebP (recommended)
   cwebp -q 80 screenshot.png -o screenshot.webp
   ```
3. Save to this directory with a descriptive name
4. Update this README with the new file

## Brand Colors

Based on claraverse.space:

- **Primary (Sakura)**: `#f43f5e` - Use for CTAs and highlights
- **Background**: `#fafaf9` (Stone-50)
- **Text Primary**: `#1c1917` (Stone-900)
- **Text Secondary**: `#78716c` (Stone-500)

## Logo Guidelines

- Minimum size: 32px height
- Recommended sizes:
  - Header: 120px width
  - Footer: 80px width
  - Social media: 512x512px square
- Maintain aspect ratio
- Use on light backgrounds for best visibility

## Official Branding

All assets are sourced from [claraverse.space](https://claraverse.space) and should match the official branding guidelines.
