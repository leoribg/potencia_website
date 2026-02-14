---
description: Analyze performance - resource loading, bundle size, runtime, and apply quick optimizations
argument-hint: [focus area (optional)]
---

# Performance Audit

Analyze and optimize the performance of the PotêncIA Tech website.

## Focus area (optional)
$ARGUMENTS

## Instructions

1. Read `public/index.html` thoroughly and analyze the following performance aspects:

### Resource Loading
- **CDN dependencies**: List all external resources (React, Tailwind, Babel, Lucide, Google Fonts) with their sizes and loading strategy
- **Render-blocking resources**: Identify scripts/styles that block initial render
- **Font loading**: Are fonts loaded efficiently? Consider `font-display: swap`, preconnect hints
- **Script loading**: Are scripts using `defer`, `async`, or neither? Evaluate optimal strategy

### Bundle Analysis
- **Total page weight**: Estimate the total download size (HTML + CDN resources)
- **Babel overhead**: The in-browser Babel transpilation adds significant overhead - flag this as a production concern
- **Unused CSS**: Tailwind CDN includes the full framework - estimate unused CSS percentage
- **Icon loading**: Lucide loads the full icon library - evaluate if tree-shaking or selective imports would help

### Runtime Performance
- **CSS animations**: Are animations using GPU-accelerated properties (transform, opacity)?
- **Layout thrashing**: Any patterns that cause forced reflows?
- **Event handlers**: Scroll handlers properly throttled/debounced?
- **React re-renders**: Any unnecessary re-renders from context changes?
- **DOM size**: Estimate total DOM node count

### Optimization Recommendations
Prioritize recommendations by impact:

**Quick Wins (implement now):**
- Add `<link rel="preconnect">` for CDN domains
- Add `font-display: swap` to Google Fonts URL
- Add `loading="lazy"` to below-fold images (if any)
- Add `<meta name="theme-color">` for browser chrome
- Optimize CSS custom property usage

**Medium Effort:**
- Replace Babel Standalone with a build step (Vite, esbuild)
- Replace Tailwind CDN with a built/purged version
- Selective Lucide icon imports instead of full library
- Implement intersection observer for scroll animations

**Long Term:**
- Consider splitting into multiple files with a bundler
- Implement service worker for offline support
- Add image optimization pipeline
- Consider SSR/SSG for better FCP

2. If the user specified a focus area, deep-dive into that area.

3. Implement quick wins directly in `public/index.html`.

4. Present a performance scorecard with estimated impact for each recommendation.
