---
description: View, modify, or add theme color tokens for light and dark modes
argument-hint: [show | change color-name to value | add token-name]
---

# Theme Color Manager

Manage and adjust the theme color tokens for the PotêncIA Tech website.

## Input
$ARGUMENTS

## Instructions

1. Read `public/index.html` and locate all CSS custom properties (variables) defined in the `<style>` block, specifically:
   - `:root` (dark mode defaults)
   - `[data-theme="light"]` (light mode overrides)
   - Any other theme-related classes

2. Based on the user's request, perform one of the following actions:

### View current palette
If the user asks to "show", "list", or "view" colors:
- Extract all CSS variables and their values
- Present them in a structured table grouped by category (backgrounds, text, borders, effects)
- Show both light and dark mode values side by side
- Include the brand colors (Potencia Blue #252065, Gold #E4B345)

### Modify existing colors
If the user wants to change a color:
- Identify the correct CSS variable(s) to modify
- Update the value in BOTH light and dark mode variants (unless specified otherwise)
- Ensure proper contrast ratios (WCAG AA minimum: 4.5:1 for text, 3:1 for large text)
- Warn if a change would break accessibility contrast requirements

### Add new color tokens
If the user wants to add a new design token:
- Create the CSS variable in both `:root` (dark) and `[data-theme="light"]` (light)
- Follow the naming convention: `--category-variant` (e.g., `--bg-accent`, `--text-highlight`)
- Suggest both light and dark mode values that maintain visual harmony

### Generate a color scheme
If the user wants to explore new palettes:
- Propose complementary colors that work with the existing brand colors
- Show how they'd look in both themes
- Maintain the professional, tech-consulting aesthetic

3. After any modification, verify that:
   - All theme transitions still work (the 0.3s ease transition on `color`, `background-color`, `border-color`)
   - Glass morphism effects remain visually consistent
   - The gradient-text class still uses harmonious start/end colors

4. Summarize all changes made.
