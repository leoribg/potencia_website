---
description: Audit and fix SEO issues including meta tags, Open Graph, structured data, and technical SEO
argument-hint: [focus area (optional)]
---

# SEO Audit

Perform a comprehensive SEO audit of the PotêncIA Tech website and implement fixes.

## Focus area (optional)
$ARGUMENTS

## Instructions

1. Read `public/index.html` thoroughly and audit the following SEO aspects:

### Meta Tags Audit
- `<title>` tag: Is it descriptive, 50-60 characters, includes brand name?
- `<meta name="description">`: Is it compelling, 150-160 characters, includes keywords?
- `<meta name="keywords">`: Relevant keywords for digital transformation, AI governance, IT consulting in Brazil?
- `<meta name="author">`: Present and correct?
- `<meta name="robots">`: Appropriate directives?
- Canonical URL: `<link rel="canonical">`?
- Language: `<html lang="pt-BR">`?

### Open Graph (Social Sharing)
- `og:title`, `og:description`, `og:image`, `og:url`, `og:type`, `og:locale`
- Twitter Card tags: `twitter:card`, `twitter:title`, `twitter:description`, `twitter:image`
- LinkedIn-specific optimizations

### Structured Data (JSON-LD)
- Organization schema
- LocalBusiness schema (if applicable)
- WebSite schema with search action
- Service schema for each service offered
- BreadcrumbList (if applicable)

### Technical SEO
- Semantic HTML structure (proper heading hierarchy h1 > h2 > h3)
- Only one `<h1>` per page
- Alt text on images
- Proper `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>` usage
- Internal linking structure
- Mobile-friendly viewport meta tag
- Page load performance considerations

### Content SEO
- Keyword density and placement
- Content quality and relevance
- Call-to-action clarity
- Internal/external link quality

2. If the user specified a focus area, prioritize that. Otherwise, audit everything.

3. Present findings as a prioritized list:
   - **Critical**: Missing essential meta tags, broken structure
   - **Important**: Missing social tags, no structured data
   - **Nice to have**: Minor optimizations

4. Implement the fixes directly in `public/index.html`, adding meta tags in `<head>` and structured data as `<script type="application/ld+json">`.

5. Summarize all changes made and any remaining recommendations.
