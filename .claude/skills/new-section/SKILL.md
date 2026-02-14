---
description: Generate a new React section component following the project's glass morphism design, dual theme, and responsive patterns
argument-hint: [section description]
---

# New Section Generator

Create a new React section component for the PotêncIA Tech website based on this description: $ARGUMENTS

## Instructions

1. Read `public/index.html` to understand the existing component patterns, theme system, and design conventions.

2. Generate a new React functional component that:
   - Follows the existing naming convention (PascalCase)
   - Uses the project's glass morphism design (`glass-card` class, `backdrop-blur`, semi-transparent backgrounds)
   - Respects the dual theme system using CSS custom properties (`var(--text-primary)`, `var(--bg-secondary)`, etc.)
   - Uses TailwindCSS utility classes for layout and spacing
   - Is fully responsive (mobile-first: single column on mobile, multi-column on `md`/`lg`)
   - Uses Lucide icons where appropriate (via `data-lucide` attributes)
   - Uses Montserrat for headings and Inter for body text
   - Includes the `gradient-text` class for accent headings where fitting
   - Has proper semantic HTML (`<section>`, `<article>`, etc.)
   - Includes `aria-label` and accessibility attributes
   - All user-facing text must be in Brazilian Portuguese (pt-BR)

3. Insert the new component definition in the `<script type="text/babel">` block, before the `App` component.

4. Add the new component to the `App` component's render tree in the appropriate position.

5. If the section needs new CSS variables or custom styles, add them to the existing `<style>` block following the theme pattern (both light and dark variants).

6. After insertion, call `lucide.createIcons()` if new Lucide icons were used (this is already handled by the existing useEffect).

7. Show the user a summary of what was added and where it was placed in the page flow.
