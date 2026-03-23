# Design System Document: Kinetic Noir

## 1. Overview & Creative North Star
**The Creative North Star: "Digital Brutalism Refined"**

This design system is engineered to break the monotony of the "SaaS-standard" layout. For an agency, the website is the ultimate portfolio piece; it must feel high-tech, intentional, and slightly provocative. We move away from safe, centered grids toward a "Kinetic Noir" aesthetic—characterized by aggressive typography scales, deep monochromatic layering, and high-energy accents of fire and ember. 

The goal is to convey "Devilish" precision: a firm that is dangerously good at what they do. We achieve this through asymmetrical compositions, overlapping elements that defy the box model, and a rejection of traditional UI crutches like borders and drop shadows.

---

## 2. Colors & Surface Architecture

### The Palette
The core of this system is the contrast between the void (`background: #0e0e0e`) and the spark (`primary: #ff8f73`). 

*   **Primary & Tertiary:** Use `primary` (#ff8f73) and `tertiary` (#ff9f4d) for high-impact moments. These are not just "brand colors"; they are heat signatures.
*   **Neutral Dynamics:** We use a spectrum of blacks and greys (`surface-container-lowest` to `surface-bright`) to build depth without color.

### The "No-Line" Rule
**Explicit Instruction:** 1px solid borders for sectioning are strictly prohibited. 
Structural boundaries must be defined solely through background color shifts. To separate a hero from a feature section, transition from `surface` (#0e0e0e) to `surface-container-low` (#131313). This creates an "editorial" flow rather than a "templated" grid.

### Surface Hierarchy & Nesting
Treat the UI as a physical stack of material. 
1.  **Base Layer:** `surface` (#0e0e0e).
2.  **Sectional Shifts:** `surface-container-low` (#131313) for secondary content blocks.
3.  **Floating Elements:** `surface-container-high` (#201f1f) or `surface-container-highest` (#262626) for cards.
4.  **Nesting:** An inner element (like a code snippet or a chip) inside a card should use `surface-container-lowest` (#000000) to create a "punched-out" effect, adding sophisticated dimensional depth.

### The "Glass & Gradient" Rule
To inject "soul," use subtle linear gradients for main CTAs: 
`linear-gradient(135deg, var(--primary) 0%, var(--primary-dim) 100%)`.
For floating navigation or overlays, use `surface-variant` (#262626) at 60% opacity with a `backdrop-blur` of 20px to create a frosted tech aesthetic.

---

## 3. Typography: The Editorial Voice

We utilize a high-contrast pairing: **Space Grotesk** for technical, sharp-edged authority and **Manrope** for modern, fluid readability.

*   **Display (Space Grotesk):** `display-lg` (3.5rem) should be used with tight letter-spacing (-0.04em) and often placed asymmetrically. It’s a statement, not just a header.
*   **Headlines (Space Grotesk):** Use `headline-lg` (2rem) for section intros. Do not be afraid to use `on-primary` text on a `primary` background for a "loud" section header.
*   **Body (Manrope):** `body-lg` (1rem) is your workhorse. Use `on-surface-variant` (#adaaaa) for secondary descriptions to maintain the hierarchy.
*   **Labels (Space Grotesk):** `label-md` (0.75rem) should always be Uppercase with +0.1em letter spacing to provide a "technical blueprint" feel.

---

## 4. Elevation & Depth: Tonal Layering

Traditional "Material" shadows are too soft for this brand. We use **Tonal Layering**.

*   **The Layering Principle:** Depth is achieved by "stacking." A `surface-container-lowest` card placed on a `surface-container-low` section creates a natural "recessed" look.
*   **Ambient Shadows:** If an element must float (e.g., a Modal), use a tinted shadow: `shadow: 0 20px 40px rgba(0, 0, 0, 0.4)`. Never use pure grey shadows; allow the background black to swallow the edges naturally.
*   **The "Ghost Border":** For essential accessibility in inputs or card boundaries, use `outline-variant` (#494847) at **15% opacity**. It should be felt, not seen.

---

## 5. Component Strategies

### Buttons
*   **Primary:** Background `primary-container` (#ff7856), text `on-primary-container` (#490b00). Shape: `md` (0.375rem). Use a subtle inner-glow on hover.
*   **Secondary:** Background `secondary-container` (#474746). No border. Hover state should shift background to `secondary-fixed-dim` (#d6d4d3) and text to `on-secondary-fixed` (#403f3f).
*   **Tertiary:** Ghost style. No background. `label-md` typography with a `primary` underline that expands on hover.

### Cards & Lists
*   **The "No-Divider" Rule:** Forbid 1px horizontal lines in lists. Use `spacing-6` (2rem) of vertical white space or a 2-tone background shift (Alternating `surface-container-low` and `surface-container-lowest`).
*   **Cards:** Use `surface-container-highest` (#262626) with `rounded-lg` (0.5rem). Elements inside the card should be aligned to a strict 8-column internal grid.

### Input Fields
*   **Style:** `surface-container-lowest` (#000000) background. 
*   **Active State:** `outline` (#777575) border at 40% opacity. 
*   **Error State:** Text and underline in `error` (#ff6e84). Avoid "red boxes"—use red accents.

### Specialized Component: The "Kinetic Cursor"
Because this is an agency system, include a custom cursor component: a `primary` dot that expands into a `primary-dim` ring when hovering over interactive elements, utilizing `mix-blend-mode: difference` for high-end polish.

---

## 6. Do’s and Don’ts

### Do:
*   **Embrace the Void:** Use `spacing-24` (8.5rem) between major sections to let the typography breathe.
*   **Asymmetry:** Offset your `display-lg` text to the left or right, leaving the opposite side for "floating" imagery or code snippets.
*   **Color as Signal:** Use `primary` (#ff8f73) only for things that are "hot" (CTAs, active states, critical alerts).

### Don't:
*   **No Grey Text on Black:** Avoid low-contrast greys for body text. Use `on-surface` (#ffffff) for readability or `on-surface-variant` (#adaaaa) for secondary info.
*   **No Rounded "Pills":** Avoid `full` (9999px) rounding for buttons unless it's a small floating action chip. Stick to `md` (0.375rem) or `lg` (0.5rem) to keep the "edgy" feel.
*   **No Center-Alignment Obsession:** Avoid centering every hero section. It feels like a template. Align to the edges of the grid for a more sophisticated, editorial look.