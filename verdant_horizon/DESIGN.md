# Design System Strategy: The Verdant Sanctuary

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Verdant Sanctuary."** 

We are moving beyond the transactional nature of booking platforms to create a high-end editorial experience that feels like a digital concierge. The goal is to evoke the lush, organic landscapes of Vietnam through a "Soft Minimalist" lens. We reject the rigid, boxy constraints of traditional travel sites in favor of an airy, breathable layout characterized by intentional asymmetry, overlapping photography, and a sophisticated tonal depth. 

This is not a database of rooms; it is a curated collection of experiences. Every interaction should feel fluid and intentional, moving away from "template" aesthetics toward a signature, premium identity.

---

## 2. Colors: Tonal Atmosphere
The palette is rooted in the vitality of nature. We utilize Material Design naming conventions to manage a sophisticated hierarchy of greens and neutrals.

### The "No-Line" Rule
**Borders are prohibited for sectioning.** To achieve a high-end editorial feel, boundaries must be defined solely through background color shifts. For example, a `surface-container-low` section should sit directly against a `surface` background. This creates a "seamless" interface that feels more like a physical environment and less like a digital form.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of fine, semi-translucent paper.
- **Base Layer:** `surface` (#fbf9f8) for the main page background.
- **Level 1 (Subtle Inset):** `surface-container-low` (#f5f3f3) for secondary content zones.
- **Level 2 (Active Cards):** `surface-container-lowest` (#ffffff) for primary interactive elements like property cards.
- **Level 3 (Interactive Depth):** Use `surface-container-high` (#eae8e7) for hover states or nested metadata.

### The "Glass & Gradient" Rule
To inject "visual soul," use **Glassmorphism** for floating elements (e.g., sticky headers or search bars). Use `surface_container_lowest` at 80% opacity with a `24px` backdrop blur. 
**Signature Texture:** For primary CTAs and hero backgrounds, use a subtle linear gradient (135°) transitioning from `primary` (#006d43) to `primary_container` (#00a86b). This provides a professional polish that flat color cannot replicate.

---

## 3. Typography: Editorial Rhythm
We use **Be Vietnam Pro** as our exclusive typeface. It is a modern sans-serif designed specifically to handle the complexities of Vietnamese diacritics with elegance and clarity.

- **The Display Scale (`display-lg` to `display-sm`):** Reserved for hero headlines. Use tight letter-spacing (-0.02em) to create an authoritative, editorial feel.
- **The Narrative Scale (`headline-md` to `title-lg`):** Used for property names and section headers. High-contrast sizing between headlines and body text is essential to guide the eye.
- **The Utility Scale (`body-md` to `label-sm`):** Designed for legibility. For Vietnamese text, ensure line-height is increased by 10-15% compared to English standards to accommodate accent marks without crowding.

Typography is the primary driver of our hierarchy. Use `on_surface_variant` (#3d4a41) for secondary descriptions to create a soft, sophisticated contrast against the deep `on_surface` (#1b1c1c) titles.

---

## 4. Elevation & Depth
Depth in this system is achieved through **Tonal Layering**, not structural lines.

- **The Layering Principle:** Place a `surface-container-lowest` card on a `surface-container-low` section to create a soft, natural lift. This mimics the way light interacts with matte surfaces.
- **Ambient Shadows:** When a floating effect is required (e.g., a "Book Now" mobile bar), use an extra-diffused shadow: `box-shadow: 0 12px 40px rgba(0, 109, 67, 0.06);`. The shadow must be tinted with the `primary` hue to feel organic.
- **The "Ghost Border" Fallback:** If a border is required for accessibility, use the `outline-variant` token at **15% opacity**. Never use 100% opaque borders.
- **Interaction Depth:** On hover, rather than moving a card "up" with a shadow, shift its background from `surface-container-lowest` to `surface_bright` or slightly increase the scale (1.02x) for a more modern, fluid response.

---

## 5. Components

### Buttons
- **Primary:** Gradient fill (`primary` to `primary_container`), `on_primary` text, `md` (8px) corner radius. Use for "Search" and "Confirm Booking."
- **Secondary:** `secondary_container` fill with `on_secondary_container` text. No border.
- **Tertiary:** No fill, `primary` text. Use for "View More" or "Cancel."

### Editorial Cards
- **Property Cards:** Use `xl` (24px) or `lg` (16px) corner radius. **Strictly no dividers.** Use 24px of internal padding (`spacing-6`) to separate images from text.
- **Image Treatment:** Images should have a subtle `inner-shadow` or a `2%` black overlay to ensure white "Save" icons remain visible.

### Input Fields
- **Search Bar:** A large, floating `surface-container-lowest` element with `full` (9999px) roundedness. Use `label-md` for floating labels.
- **Text Inputs:** Use `surface-container-low` as the background. On focus, transition the background to `surface-container-lowest` and add a 1px "Ghost Border" using `primary`.

### Navigation
- **Navbar:** Use a Glassmorphic `surface_container_lowest` with a blur. No bottom border; instead, use a subtle `surface-dim` shadow (4% opacity) to separate it from the content.

---

## 6. Do’s and Don’ts

### Do
- **Do** use asymmetrical image grids (e.g., one large image next to two smaller stacked images) to feel like a high-end magazine.
- **Do** prioritize white space. If a section feels crowded, double the padding rather than adding a divider.
- **Do** ensure all Vietnamese diacritics have ample vertical "breathing room" in the line-height.

### Don’t
- **Don’t** use a 1px solid border to separate list items. Use a `surface-container-low` background or a 32px vertical gap.
- **Don’t** use pure black (#000000) for text. Always use `on_surface` (#1b1c1c) for a softer, more premium read.
- **Don’t** use "standard" drop shadows. If it looks like a default Photoshop shadow, it is too heavy.
- **Don’t** use the `primary` green for everything. Reserve it for meaningful actions (CTAs) and use the `secondary` and `surface` tiers for the layout.