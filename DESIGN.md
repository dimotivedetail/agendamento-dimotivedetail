# Design System Document: Precision & Tonal Depth

## 1. Overview & Creative North Star
### Creative North Star: "The Industrial Precisionist"
This design system is built to mirror the obsessive attention to detail found in high-end automotive care. We move beyond standard "car wash" aesthetics by adopting an editorial, high-contrast visual language. The system avoids the cluttered "template" look by utilizing intentional asymmetry, expansive negative space, and a shift from structural lines to tonal layering. 

The experience should feel like a premium garage at midnight: dark, sophisticated, and illuminated by precision lighting. We leverage the "Anton" typeface to provide a brutalist, industrial backbone against a hyper-clean "Manrope" body, creating a tension between raw power and refined service.

---

## 2. Colors: Tonal Architecture
The color palette is rooted in the deep obsidian of the `primary` (#2e3035) and the surgical precision of the `tertiary` electric cyan (#00ded0).

- **Primary & Neutrals:** Used to build the "environment." `surface` (#121416) acts as the dark studio floor, while `primary` and `secondary` provide the materiality of steel and carbon fiber.
- **The Tertiary Highlight:** `tertiary` (#00ded0) is our "laser light." Use it sparingly for interactive elements, progress indicators, and critical calls to action. It should cut through the dark grey tones like a high-intensity LED.

### The "No-Line" Rule
To maintain a high-end feel, **1px solid borders are prohibited for sectioning.** 
- Separate content blocks using background shifts only (e.g., a `surface-container-low` section transitioning into a `surface` section).
- Boundaries are felt, not seen.

### Surface Hierarchy & Nesting
Treat the UI as a physical space with depth. Use the Surface Tiers to "nest" importance:
1.  **Base:** `surface` (#121416)
2.  **Sectioning:** `surface-container-low` (#1a1c1e)
3.  **Components/Cards:** `surface-container-highest` (#333537)

### The "Glass & Gradient" Rule
Flatness is the enemy of premium. 
- **Glassmorphism:** For floating overlays (modals, dropdowns), use `surface-container` colors at 70% opacity with a `20px` backdrop-blur. 
- **Signature Textures:** Apply a subtle linear gradient to main CTAs transitioning from `primary` (#c5c6cc) to `primary-container` (#2e3035) at a 45-degree angle to mimic the sheen of polished chrome.

---

## 3. Typography: Industrial Editorial
Typography must convey authority. We use a high-contrast scale to ensure a clear hierarchy between the "Brutalist" headings and "Technical" body text.

- **Display & Headline (SpaceGrotesk/Anton):** These are our "Engine" fonts. Use `display-lg` for hero statements. The bold, condensed nature of the industrial look should feel like it's embossed into the interface.
- **Body & Labels (Manrope):** This is our "Technical Manual." It must be clean, highly legible, and spaced generously (`letter-spacing: 0.02em`).
- **Identity Integration:** The logo must always appear in a circular containment, mimicking a wheel hub or a wax applicator, providing a soft geometric counterpoint to the sharp industrial type.

---

## 4. Elevation & Depth
In this system, light and shadow mimic a professional detailing bay.

- **The Layering Principle:** Avoid shadows for static cards. Instead, place a `surface-container-lowest` card on top of a `surface-container-low` background. This "Tonal Lift" creates a more sophisticated separation than a drop shadow.
- **Ambient Shadows:** For interactive "floating" elements, use a shadow with a 32px blur, 0% spread, and 6% opacity using the `on-surface` color. It should feel like a soft glow of light being blocked, not a black smudge.
- **The "Ghost Border" Fallback:** If a container requires a border for accessibility, use the `outline-variant` token at **15% opacity**. This creates a "barely-there" structural hint.
- **Corner Radii:** Follow the **Roundedness Scale**. Use `md` (0.375rem) for most components to maintain a "sharp but machined" feel. Reserve `full` only for the circular logo container and selection chips.

---

## 5. Components: Machined Elements

### Buttons
- **Primary:** `tertiary` (#00ded0) background with `on-tertiary` (#003733) text. No border. High-gloss hover state using a slight brightness increase.
- **Secondary:** `surface-variant` background with `on-surface` text. 
- **Tertiary (Ghost):** No background. `outline-variant` Ghost Border (15% opacity).

### Cards & Lists
- **Rule:** Absolute prohibition of divider lines.
- **Execution:** Use vertical whitespace (32px - 48px) to separate list items. For cards, use background color shifts (`surface-container-high`).
- **Imagery:** All car wash imagery (ref: {{DATA:IMAGE:IMAGE_2}}) should be treated with a subtle dark overlay to ensure `on-surface` text remains legible and the "midnight" aesthetic is maintained.

### Input Fields
- **Style:** Underline-only or subtle "Ghost Border."
- **Focus State:** The border transitions to `tertiary` (#00ded0) with a subtle outer glow (4px blur).

### Specialized Component: The "Detailing Progress" Tracker
- Use a `tertiary` thin line with `tertiary-fixed-dim` glow to track the status of a car service, echoing the precision of a laser level.

---

## 6. Do’s and Don’ts

### Do:
- **Use Asymmetry:** Place headings off-center or overlap images with text blocks to create a custom, editorial feel.
- **Embrace the Dark:** Keep 90% of the UI in the `surface` to `surface-container-highest` range.
- **Letter Spacing:** Increase letter spacing on all `label-sm` and `label-md` elements to 0.05em for a premium, airy feel.

### Don’t:
- **No Pure Black:** Never use #000000. Use `surface` (#121416) to allow for depth and shadows to remain visible.
- **No Heavy Borders:** Never use a 100% opaque border. It breaks the "Machined" aesthetic.
- **No Generic Icons:** Avoid rounded, "bubbly" icons. Use sharp, stroke-based icons with a 1.5px or 2px weight that matches the industrial look of Anton.