# Design System Specification: The Living Laboratory

## 1. Overview & Creative North Star
**Creative North Star: "The Curated Specimen"**

This design system rejects the cold, sterile "SaaS blue" of modern tech in favor of an aesthetic that feels like a high-end, digital laboratory notebook. It is designed to balance the rigorous authority of academic research with the organic complexity of systems biology. 

To break the "template" look, we move away from rigid, boxed-in layouts. Instead, we use **intentional asymmetry** and **tonal layering**. Elements should feel like specimens placed carefully on a high-quality paper surface. We utilize high-contrast typography scales—pairing a traditional, authoritative serif with a highly legible, modern sans-serif—to create a rhythmic hierarchy that guides the eye through complex data sets.

## 2. Color & Texture Strategy
Our palette is rooted in the natural world: deep chlorophyll greens, oxygenated teals, and earth-bound clay tones.

### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders for sectioning or layout containment. 
Boundaries must be defined solely through background color shifts. For example, a `surface-container-low` section should sit directly on a `surface` background. The change in tone is the boundary.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—stacked sheets of fine vellum or heavy cardstock.
*   **Base:** `surface` (#fbf9f4) – The primary canvas.
*   **Depth:** Use `surface-container-low` for large structural areas and `surface-container-highest` for small, high-priority interactive "islands."
*   **Nesting:** Place a `surface-container-lowest` (#ffffff) card on top of a `surface-container-low` (#f5f3ee) background to create a soft, natural lift without a single stroke of a pen.

### The "Glass & Gradient" Rule
To add "soul" to the academic rigor:
*   **Glassmorphism:** Use semi-transparent versions of `surface-variant` with a 12px-20px `backdrop-blur` for floating navigation bars or overlaying data panels.
*   **Organic Gradients:** For Hero backgrounds or primary CTAs, use a subtle linear gradient from `primary` (#173626) to `primary-container` (#2e4d3b). This mimics the depth found in dense foliage or microscopic imagery.

### Signature Textures
Introduce a subtle "Dot Grid" pattern (using `outline-variant` at 15% opacity) to the background of `surface-container-low` areas. This evokes the feel of a researcher’s field notes and provides a tactile quality to the digital space.

## 3. Typography
The typographic voice is an intentional dialogue between the tradition of the academy and the precision of modern science.

*   **Display & Headlines (Newsreader):** Use these for all `display-*` and `headline-*` roles. The serif terminals convey a sense of established authority and "published" quality. Use generous letter-spacing (-0.02em) for large displays to keep them tight and sophisticated.
*   **Body & UI (Manrope):** A clean, geometric sans-serif used for `title-*`, `body-*`, and `label-*`. Its high x-height ensures readability in dense research papers or complex data tables.
*   **Contrast as Hierarchy:** Pair a `display-lg` headline with a `label-md` uppercase sub-header in `tertiary` (#4a2806) to create a sophisticated, editorial contrast.

## 4. Elevation & Depth
In this system, light and shadow are environmental, not artificial.

*   **Tonal Layering:** Avoid shadows for standard cards. Rely on the shift from `surface` to `surface-container-high`.
*   **Ambient Shadows:** When an element must "float" (e.g., a modal or a floating action), use a multi-layered shadow: `0 10px 30px -5px rgba(27, 28, 25, 0.05)`. The shadow color must be a tint of `on-surface`, never pure black.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, use the `outline-variant` token at **20% opacity**. This creates a "suggestion" of a container rather than a hard cage.
*   **Corner Radii:** Use the `lg` (0.5rem) scale for cards and `full` for buttons. This slight roundness mimics organic cells and smooth stones, softening the academic "edge."

## 5. Components

### Buttons
*   **Primary:** Background: `primary` (#173626), Text: `on-primary` (#ffffff). Shape: `full`. Use a subtle inner-glow (top-down) for a tactile, "pressed" feel.
*   **Secondary:** Background: `secondary-container` (#c1e8d6), Text: `on-secondary-container` (#466a5b). No border.
*   **Tertiary:** Text only, using `primary` color with a `label-md` weight.

### Cards & Data Lists
*   **The Forbidden Line:** Never use horizontal rules (`<hr>`) to separate list items. Use 16px to 24px of vertical white space (from the Spacing Scale) or alternating background tints (`surface` vs `surface-container-low`).
*   **Cards:** Use `surface-container-lowest` (#ffffff) with an `xl` (0.75rem) corner radius.

### Input Fields
*   **Style:** Minimalist. No bottom line or full box. Use a subtle `surface-container-high` fill with an `outline-variant` ghost border (20% opacity).
*   **Focus:** Transition the background to `surface-container-lowest` and increase the border opacity to 100%.

### Additional Academic Components
*   **The "Abstract" Block:** A specialized callout component using `tertiary-container` (#653e1b) background with `Newsreader` italic text.
*   **Data Specimen Chips:** Small, `full` rounded chips using `secondary-fixed` for categorical data visualization.

## 6. Do’s and Don’ts

### Do
*   **Do** use asymmetrical margins. For example, give a main text column a larger left margin than right to create an editorial, "notebook" feel.
*   **Do** lean into the "Clay" tones (`tertiary` series) for highlights and callouts—it breaks the monotony of the greens.
*   **Do** use the `24` (6rem) spacing token for major section breaks to allow the research to "breathe."

### Don’t
*   **Don’t** use pure black (#000000) for text. Use `on-surface` (#1b1c19) to maintain the soft, organic feel.
*   **Don’t** use sharp 90-degree corners. Everything in nature has a radius.
*   **Don’t** use standard "Success" greens. Use our `primary` and `secondary` teals/forest greens to maintain the signature palette.