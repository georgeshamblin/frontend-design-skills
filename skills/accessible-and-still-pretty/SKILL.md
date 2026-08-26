---
name: accessible-and-still-pretty
description: Use when handling contrast, focus states, semantics, or any accessibility concern — proving a11y and beauty are the same discipline, not a tradeoff.
metadata:
  category: discipline
  triggers: accessibility, a11y, contrast, focus states, WCAG, screen reader, semantic HTML
---

# Accessible & Still Pretty

## When to Use
- Every project, as a standing gate before ship
- Someone proposes hiding focus rings or shipping gray-on-gray text "for the look"

## The reframe

Accessibility failures are design failures wearing an excuse. Illegible muted text,
invisible focus, hover-only menus: these read as broken to EVERYONE, not just users
with disabilities. The most beautiful sites pass because clarity is what beauty is
made of.

## Contrast (hard numbers)

- Body text 4.5:1 against its ground, minimum; aim 7:1
- Large text (24px+, or 19px bold) 3:1 minimum
- UI parts (input borders, icons that carry meaning) 3:1
- These bind the "muted" text tokens too — muted means secondary, not faint. If the
  palette can't produce a passing muted tone, fix the palette (color-systems), don't
  ship the failure.

## Focus states as a design feature

Never `outline: none` without a better replacement. Design ONE focus treatment from
the brand and apply it everywhere:

```css
:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 3px;
  border-radius: var(--radius-sm);
}
```

`:focus-visible` keeps mouse clicks clean while keyboard users get a ring worth
looking at. Tab through the whole page: every interactive element shows the ring,
in a logical order, and nothing keyboard-unreachable exists.

## Semantics are free polish

- One `<h1>`, heading levels without skips (the outline a screen reader hears is
  the same hierarchy the squint test sees — see design-foundations)
- Landmarks: `<header>`, `<nav>`, `<main>`, `<footer>`; a skip link as the first
  focusable element
- Buttons do actions, links go places; never a clickable `<div>`
- Form inputs get real `<label for>` (see component-polish); errors are announced
  (`aria-describedby` + `role="alert"`), not just turned red — color is never the
  only signal for anything
- Images: descriptive alt or explicit `alt=""` (imagery-and-icons)
- `lang` on `<html>`, real `<title>`, and text that zooms to 200% without breaking

## Motion and preference respect

`prefers-reduced-motion` handling ships in every project (the block lives in
motion-and-microinteractions). If dark mode exists, it follows
`prefers-color-scheme` with tokens, both modes passing contrast independently.

## The gate

Before ship: axe DevTools (or Lighthouse a11y) returns zero serious violations, a
full keyboard pass works, contrast spot checks pass in both modes, reduced motion
respected. These four checks take ten minutes and are not skippable — a page is not
done, and not beautiful, while any of them fails.
