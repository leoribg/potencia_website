---
description: Audit and harden client-side security - hide sensitive data from DevTools (F12), add CSP, SRI, and obfuscation
argument-hint: [focus area (optional)]
---

# Security Audit — Client-Side Data Exposure

Audit the PotêncIA Tech website for sensitive information visible via browser DevTools (F12) and implement hardening measures.

## Focus area (optional)
$ARGUMENTS

## Context

Since this is a single-file SPA (`public/index.html`) with no build step, ALL code is visible in the browser source. This skill identifies what's exposed and applies mitigations where possible.

## Instructions

1. Read `public/index.html` and scan for every instance of sensitive or exploitable data, including:

### Category 1: API Keys & Credentials
- Firebase configuration object (`apiKey`, `authDomain`, `projectId`, `storageBucket`, `messagingSenderId`, `appId`, `measurementId`)
- Any other API keys, tokens, or secrets
- **Assessment**: Firebase client-side keys are designed to be public (they identify the project, not authenticate). However, the project MUST have Firebase Security Rules properly configured to prevent unauthorized data access. Verify and warn the user.

### Category 2: Service Endpoints
- **Formspree endpoint URL** (`https://formspree.io/f/...`): Can be abused to send spam through the form
- **Firebase project URLs**: Reveal the Firebase project name
- Any other third-party service endpoints

### Category 3: Personal & Business Information
- **Email addresses**: Direct emails visible in source (e.g., `mauroperiquito@potenciatech.ai`)
- **LinkedIn profile/company URLs**: Reveal organizational structure
- **External article URLs**: Reveal content strategy
- **Phone numbers, addresses** if present

### Category 4: Development Artifacts
- **React development builds**: Check if `react.development.js` / `react-dom.development.js` are used instead of production minified versions (`react.production.min.js`)
- **Console logs, TODO comments, debug code**: Anything left from development
- **Babel Standalone**: Exposes raw JSX source code in browser, making the entire app logic readable
- **Inline comments** revealing internal architecture decisions

### Category 5: Missing Security Headers & Protections
- **Content Security Policy (CSP)**: Is a `<meta http-equiv="Content-Security-Policy">` present?
- **Subresource Integrity (SRI)**: Do CDN `<script>` tags have `integrity` attributes?
- **X-Frame-Options / frame-ancestors**: Protection against clickjacking
- **Referrer Policy**: `<meta name="referrer">`
- **Permissions Policy**: Restricting browser feature access

2. For each finding, classify severity:
   - **CRITICAL**: Real credentials, secrets, or tokens that grant access
   - **HIGH**: Exploitable endpoints (form spam), development builds in production
   - **MEDIUM**: Business information exposure, missing security headers
   - **LOW**: Informational exposure (project names, public URLs)

3. Implement fixes directly in `public/index.html`:

### Fixes to apply:

**Switch to production React builds:**
Replace development CDN URLs with production minified versions:
- `react.development.js` → `react.production.min.js`
- `react-dom.development.js` → `react-dom.production.min.js`

**Add Content Security Policy meta tag:**
```html
<meta http-equiv="Content-Security-Policy" content="
  default-src 'self';
  script-src 'self' 'unsafe-inline' 'unsafe-eval' https://unpkg.com https://cdn.tailwindcss.com https://www.gstatic.com;
  style-src 'self' 'unsafe-inline' https://fonts.googleapis.com https://cdn.tailwindcss.com;
  font-src https://fonts.gstatic.com;
  img-src 'self' data: https:;
  connect-src 'self' https://formspree.io https://www.google-analytics.com https://*.firebaseio.com;
  frame-ancestors 'none';
">
```
Adapt the policy to match actual resource origins used in the page.

**Add Subresource Integrity (SRI) hashes:**
For each CDN `<script>` and `<link>` tag, generate and add `integrity` attributes with `crossorigin="anonymous"`. Use `sha384` algorithm.
Run `curl -s <CDN_URL> | openssl dgst -sha384 -binary | openssl base64 -A` to generate hashes for each resource.

**Add security meta tags:**
```html
<meta name="referrer" content="strict-origin-when-cross-origin">
<meta http-equiv="X-Content-Type-Options" content="nosniff">
```

**Obfuscate email addresses:**
Replace plain-text email in `mailto:` links and visible text with a JavaScript-decoded version to prevent scraping by bots:
- Encode the email with a simple character shift or base64
- Decode it at render time in the React component
- This stops automated scrapers but doesn't affect users

**Add honeypot field to the contact form:**
Add a hidden input field that bots will fill but humans won't. If filled, the form submission is silently discarded. This protects the Formspree endpoint from spam:
```html
<input type="text" name="_gotcha" style="display:none" tabIndex="-1" autoComplete="off">
```

**Remove TODO comments and debug artifacts:**
Scan for and remove any `// TODO`, `console.log`, `console.debug`, or development-only comments.

**Add rel="noopener noreferrer" to all external links:**
Verify every `<a target="_blank">` has `rel="noopener noreferrer"` to prevent tab-nabbing attacks.

4. Present a security report with:
   - Summary of all findings with severity ratings
   - List of all fixes applied
   - Remaining risks that cannot be mitigated client-side (with recommendations)
   - A recommendation about Firebase Security Rules (the user should verify these in the Firebase Console)
   - A note about considering a build step (Vite/esbuild) to avoid exposing raw JSX source code via Babel Standalone
