---
name: component-polish
description: Use when styling buttons, cards, forms, navigation, or footers — the component details that separate a finished page from a generated one.
metadata:
  category: technique
  triggers: buttons, cards, forms, inputs, navbar, footer, shadows, border radius, polish
---

# Component Polish

## When to Use
- Building or reviewing any interactive component
- A page whose pieces individually look fine but collectively look cheap

## System rules (from design-foundations)

One radius token. One shadow recipe. One border color. Every component draws from
them — polish is 80% consistency.

```css
:root {
  --radius: 10px;
  --radius-sm: 6px;
  --shadow-sm: 0 1px 2px rgb(0 0 0 / 0.05);
  --shadow-md: 0 4px 12px -2px rgb(0 0 0 / 0.08), 0 2px 4px -2px rgb(0 0 0 / 0.04);
}
```

Shadows are layered, low opacity, and reserved for elements that float (dropdowns,
modals, the ONE featured card). A shadow on everything means elevation on nothing.

## Buttons

- Primary: accent ground, `--accent-contrast` text, `--radius-sm`, padding
  `0.75rem 1.5rem`, weight 600. Secondary: quiet outline or ghost, SAME dimensions.
- States are not optional: hover (slight darken via `--accent-strong`, or a 1px
  lift), active (pressed, no lift), focus visible (see accessible-and-still-pretty),
  disabled (reduced opacity, no hover response).
- Transitions per motion-and-microinteractions: ~150ms, colors and transform only.
- No gradient pill buttons with glow. That is the costume of a generated page.

## Cards

- A card = surface token + border OR shadow (rarely both) + internal padding
  `--space-6` + the radius token.
- Contents follow one internal hierarchy: label/icon, title, body, action, each
  separated by scale spacing. All cards in a group share identical structure; the
  variety belongs to the content.
- If a card is clickable, the WHOLE card is the link, with a visible hover response.
- Not everything needs to be a card. Text on the page ground with good spacing often
  reads more confident than another bordered box.

## Forms

Forms are where trust is won or lost:

- Labels ABOVE inputs, always visible. Placeholder text is a hint, never the label.
- Inputs: comfortable height (~2.9rem), `--radius-sm`, border `--border` with accent
  on `:focus` plus a soft outer ring; padding matching the button scale.
- Ask for the minimum. Every extra field costs completions.
- Validate on submit (or on blur after first attempt), with the message next to the
  field, in words a person would say: `Please enter your phone number`, not `Invalid
  input`.
- The submit button follows copy-that-sounds-human: `Send message`, never `Submit`.

## Navigation & footer

- Nav: wordmark left, few real links, one primary action right. Current page
  indicated. Sticky only if the page is long enough to need it; solid ground when
  stuck, never a blur wall over content.
- Footer: what actually exists — NAP, hours, real page links, legal. A four column
  footer for a five page site is a tell (see avoiding-ai-slop).

## Verify

Build one screen with every component state visible (default, hover, focus, filled,
error, disabled). If two components disagree on radius, border, or spacing, the
tokens were bypassed; fix the component, not the token.
