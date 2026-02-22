---
name: brutalist-design-expert
description: Expert in Brutalist and Neo-Brutalist web design. Use when the user wants a raw, bold, or non-conventional aesthetic. Includes variations like Cute-alism and Dial-up Delight.
---

# Brutalist Design Expert

This skill makes the agent a specialist in Brutalist web design, its modern evolutions (Neo-Brutalism), and niche sub-genres. It provides design tokens, layout patterns, and a methodology for staying updated with trends.

## When to use this skill
- Use when the user requests a "Brutalist", "Neo-Brutalist", or "raw/bold" design.
- Helpful for projects targeting Gen Z audiences or brands wanting a high-contrast, authentic "anti-corporate" look.
- Use when designing interfaces that need to stand out from standard minimalist/polished templates.

## Design Variations & Tokens

### 1. Classic Brutalism (Pure/Raw)
- **Concept:** Function over form, zero-waste digital design.
- **Visuals:** Default browser fonts (Times New Roman, Arial), blue underline links, no padding, raw HTML look, monochrome or clashing colors.
- **Reference:** `brutalistwebsites.com`

### 2. Neo-Brutalism (Elevated Brutalism)
- **Concept:** Rebellious but usable.
- **Visuals:** 
    - **Shadows:** Hard-edged, solid black shadows (e.g., `box-shadow: 5px 5px 0px #000;`).
    - **Borders:** Thick 2px-4px black borders on everything.
    - **Colors:** High-saturation "clashing" colors (Neon Green, Hot Pink, Yellow) on a white or light-grey background.
    - **Typography:** Bold Sans-serif or Monospace (e.g., Space Grotesk, Lexend, JetBrains Mono).

### 3. Cute-alism (Soft Brutalism)
- **Concept:** Friendly utility.
- **Visuals:** Pastel backgrounds + Brutalist layout, "sticker" style buttons, whimsical iconography, rounded corners mixed with sharp shadows.

### 4. Dial-up Delight (Retro-Futurism)
- **Concept:** Early internet nostalgia (Y2K / GeoCities).
- **Visuals:** Pixel fonts, scrolling marquees, animated GIFs, table-based layouts (lookalike), dithering effects.

## How to stay updated (The "Scraper" Workflow)

To get the latest trends, the agent should:
1. **Target Sites:** Use `browser_subagent` to visit:
    - `https://brutalistwebsites.com/` (For raw inspiration)
    - `https://onepagelove.com/gallery/brutalist` (For modern one-page examples)
    - `https://gumroad.com` (A classic example of commercial Neo-Brutalism)
2. **Analysis Process:** 
    - Extract CSS variable names (often reveal primary/accent colors).
    - Analyze `box-shadow` values to determine shadow "hardness".
    - Check font-families used in headers vs. body.

## Implementation Guide (Vanilla CSS)

```css
/* Core Neo-Brutalist Token Set */
:root {
  --bg: #F0F0B0;
  --accent: #FF5C00;
  --border: #000000;
  --shadow: #000000;
  --font-main: 'Space Grotesk', sans-serif;
}

.brutalist-card {
  background: white;
  border: 4px solid var(--border);
  box-shadow: 8px 8px 0px var(--shadow);
  padding: 2rem;
  transition: transform 0.1s;
}

.brutalist-card:hover {
  transform: translate(-2px, -2px);
  box-shadow: 10px 10px 0px var(--shadow);
}

.brutalist-button {
  background: var(--accent);
  border: 3px solid var(--border);
  box-shadow: 4px 4px 0px var(--shadow);
  font-weight: 800;
  text-transform: uppercase;
  padding: 0.5rem 1.5rem;
  cursor: pointer;
}
```

## Best Practices
- **Contrast is Key:** Always aim for high contrast, but verify legibility.
- **Grid layouts:** Use `display: grid;` with visible `gap` or even borders on the grid container itself.
- **Accessibility:** Don't sacrifice the user's ability to navigate. Neo-Brutalism is about aesthetic rebellion, not functional failure.
