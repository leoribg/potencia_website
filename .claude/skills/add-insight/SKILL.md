---
description: Add a new insight or article card to the Insights section
argument-hint: [title, link, category, description]
---

# Add Insight Card

Add a new insight/article card to the Insights section of the PotêncIA Tech website.

## Input
$ARGUMENTS

## Instructions

1. Read `public/index.html` and locate the **Insights** section component.

2. Parse the user's input to extract:
   - **Title**: The article/insight title (in pt-BR)
   - **Category**: e.g., "Governanca & Operacoes", "Inteligencia Artificial", "Transformacao Digital"
   - **Description**: A short summary (1-2 sentences in pt-BR)
   - **Link**: URL to the full article (typically LinkedIn or mauroperiquito.com)
   - **Read time** (optional): Estimated reading time

3. If the user didn't provide all fields, infer reasonable defaults or ask for missing critical info (title and link are required).

4. Create a new insight card following the exact pattern of existing cards in the Insights component:
   - Glass card styling with hover effects
   - Category badge at the top
   - Title with proper font sizing
   - Description text
   - "Ler artigo completo" link at the bottom with arrow icon
   - Proper responsive grid behavior

5. Add the new card to the insights array/JSX in the Insights component.

6. If there are now more than 3 insights, consider whether the grid layout needs adjustment (e.g., `grid-cols-1 md:grid-cols-2 lg:grid-cols-3` may need to become `lg:grid-cols-4` or the section may need a "show more" pattern).

7. Confirm the addition with a summary showing the card details.
