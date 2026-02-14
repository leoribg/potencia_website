---
description: Accessibility audit following WCAG 2.1 AA - contrast, keyboard nav, ARIA, landmarks
argument-hint: [focus area (optional)]
---

# Accessibility Audit

Perform an accessibility (a11y) audit of the PotêncIA Tech website following WCAG 2.1 AA guidelines.

## Focus area (optional)
$ARGUMENTS

## Instructions

1. Read `public/index.html` thoroughly and audit the following accessibility aspects:

### Perceivable
- **Text alternatives**: All non-text content has text alternatives (alt, aria-label, aria-labelledby)
- **Color contrast**: Text meets WCAG AA contrast ratios (4.5:1 normal, 3:1 large text) in BOTH light and dark modes
- **Color independence**: Information is not conveyed by color alone
- **Text resizing**: Content is readable at 200% zoom
- **Content structure**: Proper use of headings, lists, and landmarks

### Operable
- **Keyboard navigation**: All interactive elements are keyboard accessible (tab order, focus indicators)
- **Focus management**: Visible focus indicators on all interactive elements
- **Skip navigation**: "Skip to main content" link present?
- **Touch targets**: Minimum 44x44px touch target size for mobile
- **Motion**: Respect `prefers-reduced-motion` media query for animations

### Understandable
- **Language**: `lang="pt-BR"` attribute on `<html>`
- **Labels**: All form inputs have associated `<label>` elements
- **Error identification**: Form validation provides clear error messages
- **Consistent navigation**: Navigation is consistent across the page

### Robust
- **Valid HTML**: Proper nesting, no duplicate IDs
- **ARIA usage**: ARIA attributes used correctly (roles, states, properties)
- **Landmark regions**: Proper use of `<main>`, `<nav>`, `<aside>`, `<footer>`
- **Component roles**: Interactive components have proper ARIA roles

### Theme-Specific Checks
- Verify contrast ratios for BOTH light and dark mode color schemes
- Ensure theme toggle is keyboard accessible and announces state changes
- Check that glass morphism effects don't reduce text readability
- Verify gradient text is readable (has fallback solid color)

2. For each issue found, categorize by severity:
   - **A (Critical)**: Blocks access for users with disabilities
   - **AA (Important)**: Significant barrier to accessibility
   - **AAA (Enhancement)**: Best practice improvement

3. Implement fixes directly in `public/index.html`:
   - Add missing ARIA attributes
   - Add skip navigation link
   - Fix heading hierarchy
   - Add `prefers-reduced-motion` media query
   - Add focus-visible styles
   - Fix form label associations
   - Add proper landmark roles

4. Present a summary of findings and fixes, organized by WCAG principle.
