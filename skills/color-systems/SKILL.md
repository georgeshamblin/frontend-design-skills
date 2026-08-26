---
name: color-systems
description: Use when choosing colors, building a palette, defining CSS color tokens, or adding dark mode to any front end.
metadata:
  category: technique
  triggers: colors, palette, color scheme, dark mode, brand colors, CSS variables, contrast
---

# Color Systems

## When to Use
- Starting the palette for any project
- A page that feels flat, garish, or "template purple"
- Adding dark mode

## Building the palette

A professional palette is **neutrals doing the work and one accent making the
point**:

1. **Neutrals with temperature.** Pure gray (#888) looks dead. Tint the neutral ramp
   toward the accent's temperature: warm accent, warm grays; cool accent, cool
   grays. Build 8 to 10 steps from near white to near black.
2. **One accent with a reason.** Derived from the logo, the industry, the locale,
   the feeling chosen in design-foundations. Never the model's reflexive
   indigo/violet unless the brand actually owns it.
3. **A support tone,** used rarely: a darker or lighter relative of the accent for
   hovers and secondary emphasis. Not a second personality.
4. **Semantic colors** (success, warning, error) that harmonize with the ramp
   instead of stock traffic light values.

Distribution: roughly 60% background neutrals, 30% text and structural neutrals,
10% accent. When the accent exceeds ten percent, it stops meaning anything.

## Tokens, not hex soup

```css
:root {
  --bg: #faf9f7;
  --surface: #ffffff;
  --text: #1c1a17;
  --text-muted: #5c574f;
  --border: #e6e2db;
  --accent: #1f5f43;
  --accent-strong: #17452f;
  --accent-contrast: #ffffff;
}
```

Every color in every component references a token. Nothing hardcodes a hex value;
that is what makes dark mode and rebrands one file edits.

## Dark mode (only if the project wants it)

- Redefine the SAME tokens under `@media (prefers-color-scheme: dark)`; components
  never know which mode they are in
- Dark surfaces are dark warm/cool neutrals (#16181d territory), never pure black;
  text is near white, never pure white
- Desaturate and lighten the accent slightly in dark mode; saturated colors vibrate
  on dark grounds
- Shadows barely work on dark; separate surfaces with subtle borders and lighter
  surface steps instead
- Give `body` an explicit token background in both modes

## Contrast is not optional

- Body text on background: 4.5:1 minimum (aim 7:1)
- Large headings: 3:1 minimum
- Accent as button background with its contrast color: 4.5:1
- Muted text still passes 4.5:1; "muted" means smaller role, not illegible

Check with a contrast tool per pairing, both modes. A beautiful palette that fails
contrast is a defect, not a style (see accessible-and-still-pretty).

## Tells to avoid

Gradient text on headlines. Purple to blue hero washes. A different accent per
section. Colored section backgrounds alternating like a beach ball. Restraint: most
sections sit on `--bg`; ONE section may use a tinted or dark ground for contrast,
and that section earns it by content, not rotation.
