---
description: Add a new service card to the Services section with icon and description
argument-hint: [service name and description]
---

# Add Service Card

Add a new service card to the Services section of the PotêncIA Tech website.

## Input
$ARGUMENTS

## Instructions

1. Read `public/index.html` and locate the **Services** section component.

2. Parse the user's input to extract:
   - **Title**: Service name (in pt-BR)
   - **Description**: Service description (1-3 sentences in pt-BR)
   - **Icon**: Lucide icon name (e.g., `shield-check`, `brain-circuit`, `cpu`, `rocket`)
   - **Accent color** (optional): A color for the top border on hover

3. If the user provided a general description, craft appropriate pt-BR title and description text that matches the professional consulting tone of the existing services (formal but approachable).

4. Create a new service card following the exact pattern of existing cards:
   - Glass card design with `glass-card` class
   - Lucide icon at the top with themed color
   - `h3` title with proper font styling
   - Description paragraph
   - Hover animation (lift effect + top border color)
   - Responsive grid behavior

5. Add the card to the services grid in the Services component.

6. Adjust the grid layout if needed:
   - 4 cards: `grid-cols-1 md:grid-cols-2 lg:grid-cols-4` (current)
   - 5-6 cards: consider `lg:grid-cols-3` with 2 rows
   - 7-8 cards: consider `lg:grid-cols-4` with 2 rows

7. Verify the new Lucide icon name is valid. If unsure, suggest alternatives from the existing icon set.

8. Confirm the addition with a summary.
