# PotencIA Tech Website

## Project Overview
Single-page application website for **PotêncIA Tech**, a Brazilian digital transformation consulting firm. The site focuses on governance, IT strategy, responsible AI, and digital transformation.

## Architecture
- **Single-file SPA**: All code lives in `public/index.html` (React + JSX + CSS)
- **No build step**: Babel Standalone handles JSX transpilation in-browser
- **CDN dependencies**: React 18, TailwindCSS 3, Lucide Icons, Google Fonts (Montserrat + Inter)
- **Hosting**: Firebase Hosting (project: `potencia-74784`)
- **Contact form**: Formspree integration
- **Analytics**: Firebase Analytics / GA4

## Key Conventions

### Design System
- **Glass morphism** pattern: `backdrop-blur`, semi-transparent backgrounds, subtle borders
- **Brand colors**: Potência Blue `#252065`, Potência Gold `#E4B345`
- **Dual theme**: Light mode (blue text on white) / Dark mode (white text on black)
- **CSS Variables**: All theme tokens defined as custom properties on `:root` and `[data-theme="light"]`
- **Fonts**: Montserrat for headings, Inter for body text

### React Patterns
- Functional components with hooks
- ThemeProvider context for theme state management
- PascalCase component names
- All components defined inside `<script type="text/babel">` in index.html

### Styling
- TailwindCSS utility classes as primary styling approach
- CSS custom properties for theme-aware colors
- Glass card pattern: `glass-card` class with hover effects
- Gradient text: `gradient-text` class for brand gradient

### Responsive Design
- Mobile-first approach
- Tailwind breakpoints: `sm`, `md`, `lg`
- Grid layouts: 1 col (mobile) → 2-4 cols (desktop)

## File Structure
```
public/
  index.html                          # Main SPA (all code)
  favicon.svg                         # Brand favicon
firebase.json                         # Firebase hosting config
.firebaserc                           # Firebase project config
.claude/
  agents/
    security-scanner.md               # Scans for exposed secrets, keys, endpoints (F12 risk)
    code-reviewer.md                  # Reviews code quality, React patterns, a11y, bugs
    design-system.md                  # Analyzes colors, typography, spacing, components
    content-writer.md                 # Writes/edits pt-BR content in brand voice
    qa-tester.md                      # Pre-deploy QA: links, theme, form, responsive
  skills/
    security-audit/SKILL.md           # /security-audit - harden client-side security
    seo-audit/SKILL.md                # /seo-audit - meta tags, Open Graph, JSON-LD
    a11y-check/SKILL.md               # /a11y-check - WCAG 2.1 AA accessibility audit
    perf-audit/SKILL.md               # /perf-audit - performance analysis & quick wins
    new-section/SKILL.md              # /new-section - generate new React sections
    add-insight/SKILL.md              # /add-insight - add insight/article cards
    add-service/SKILL.md              # /add-service - add service cards
    theme-colors/SKILL.md             # /theme-colors - manage theme color tokens
    deploy/SKILL.md                   # /deploy - Firebase deploy with pre-flight checks
    translate/SKILL.md                # /translate - pt-BR/en-US translation & i18n
```

## Skills (invoke with `/skill-name`)
| Skill | Description |
|---|---|
| `/security-audit` | Audit and harden client-side security — exposed keys, CSP, SRI, email obfuscation |
| `/seo-audit` | Audit meta tags, Open Graph, structured data (JSON-LD), heading hierarchy |
| `/a11y-check` | WCAG 2.1 AA accessibility audit — contrast, ARIA, keyboard nav, landmarks |
| `/perf-audit` | Performance analysis — resource loading, bundle size, runtime optimizations |
| `/new-section` | Generate a new React section following glass morphism and dual theme patterns |
| `/add-insight` | Add a new insight/article card to the Insights section |
| `/add-service` | Add a new service card to the Services section |
| `/theme-colors` | View, modify, or add theme color tokens (light + dark mode) |
| `/deploy` | Deploy to Firebase Hosting with pre-flight validation checks |
| `/translate` | Translate content (pt-BR / en-US), proofread, or implement full i18n |

## Agents (invoke with `/agents`)
| Agent | Description |
|---|---|
| `security-scanner` | Scans for secrets, API keys, emails, endpoints visible via F12 DevTools |
| `code-reviewer` | Reviews React patterns, a11y, CSS, code quality, and potential bugs |
| `design-system` | Documents the full design system — colors, typography, spacing, components |
| `content-writer` | Writes pt-BR content matching the brand voice for C-level audience |
| `qa-tester` | Pre-deploy QA: links, theme system, forms, responsive layout, assets |

## Commands
- Local dev: `firebase serve --port 5000`
- Deploy: `firebase deploy --only hosting`

## Language
- All user-facing content is in **Brazilian Portuguese (pt-BR)**
- Code comments and variables in English
