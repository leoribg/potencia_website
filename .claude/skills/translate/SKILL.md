---
description: Translate content between pt-BR and en-US, proofread Portuguese, or implement full i18n system
argument-hint: [text to translate or action: translate|proofread|i18n]
---

# Content Translation & i18n

Translate or internationalize content for the PotêncIA Tech website.

## Input
$ARGUMENTS

## Instructions

Based on the user's request, perform one of the following:

### Translate specific text
If the user provides specific text to translate:
1. Identify the text in `public/index.html`
2. Translate it between Portuguese (pt-BR) and English (en-US) while maintaining:
   - Professional consulting tone
   - Technical accuracy for IT/AI/governance terminology
   - Brand voice consistency (authoritative yet approachable)
   - Cultural nuances (don't just literal-translate idioms)
3. Apply the translation directly in the file

### Full page translation review
If the user asks for a translation review or wants to add English support:
1. Read `public/index.html` and extract all user-facing text strings
2. Organize them by section (Navigation, Hero, Services, Methodology, About, Insights, Contact, Footer)
3. Provide translations maintaining brand consistency
4. Key terminology mapping:
   - "Governanca de TI" = "IT Governance"
   - "Transformacao Digital" = "Digital Transformation"
   - "IA Responsavel" = "Responsible AI"
   - "Inovacao Estrategica" = "Strategic Innovation"
   - "Potencia" = "Power/Potential" (keep as brand name, don't translate)
   - "Crescendo com Inteligencia" = "Growing with Intelligence"

### Implement i18n system
If the user wants full internationalization:
1. Create a translation object/map with all strings keyed by section
2. Add a language toggle to the navigation (alongside the theme toggle)
3. Create a LanguageProvider context (similar to ThemeProvider)
4. Store language preference in localStorage (key: 'potencia-lang')
5. Support: pt-BR (default), en-US
6. Update all hardcoded strings to use the translation system
7. Ensure the `<html lang="">` attribute updates dynamically

### Proofread Portuguese content
If the user asks for proofreading:
1. Review all pt-BR text for:
   - Grammar and spelling errors
   - Consistency in formality level (voce vs. tu vs. formal)
   - Proper use of accents and special characters
   - Professional tone appropriate for a consulting firm
2. Suggest corrections with explanations
