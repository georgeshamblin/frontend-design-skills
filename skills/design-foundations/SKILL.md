---
name: design-foundations
description: Use when starting any visual front end work — a new page, site, or component — before writing the first line of markup or CSS.
metadata:
  category: discipline
  triggers: design, UI, front end, landing page, redesign, visual design, make it pretty
---

# Design Foundations

## When to Use
- Before building any page or component
- When a page "works but looks off" and nobody can say why

## The premise

A generated page and a designed page contain the same ingredients. The difference is
that a designer made each decision on purpose and made them all agree. This skill is
the agreement layer: read it, pick the values, then hold every later decision to them.

## Decide these five things first, in writing

1. **One feeling.** Pick a single adjective the page should produce: calm, sharp,
   warm, serious, playful. Every following choice gets tested against it. A page
   aiming at two feelings lands on neither.
2. **One typeface pair.** A display face for headings and a text face for body, or a
   single family used at two weights. Never three families. (See
   typography-that-reads.)
3. **One accent color.** A palette is neutrals plus ONE color with a point of view,
   used sparingly enough to mean something. (See color-systems.)
4. **One spacing scale.** Pick the base unit and stick to its multiples everywhere.
   (See spacing-and-layout.)
5. **One corner radius and one shadow recipe.** Applied consistently to every
   surface. Mixed radii and ad hoc shadows are the fastest generated tell.

Write the five as CSS custom properties before any component exists. That file IS the
design system; nothing hardcodes a value it could take from a token.

## Hierarchy is the whole job

A visitor should know in one glance: what this page is, what matters most, and what
to do next. Achieve it with size, weight, and space, in that order, before reaching
for color or decoration. Test: squint at the page. Exactly one thing should dominate.
If everything is bold, nothing is.

## Restraint rules

- Every element earns its place by helping the one feeling or the one action. Default
  to removing.
- Decoration that could appear on any site belongs on no site. If a gradient, badge,
  or blob does not come FROM the brand, it is filler.
- When in doubt between two treatments, take the quieter one. Quiet reads as
  expensive; loud reads as template.
- Consistency beats novelty. The fourth card matching the first three is design; the
  fourth card "adding variety" is noise.

## Exit checklist

Before calling any page done, run avoiding-ai-slop as the final review pass, and
check the copy against copy-that-sounds-human. Visual polish over generated sounding
words is lipstick.
