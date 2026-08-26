---
name: responsive-beauty
description: Use when making a page work across screen sizes — mobile layout, breakpoints, touch targets — so it stays beautiful, not merely functional, at every width.
metadata:
  category: technique
  triggers: responsive, mobile, breakpoints, media queries, viewport, touch targets, mobile design
---

# Responsive Beauty

## When to Use
- Building any page (mobile is most of the traffic for local businesses)
- A site that is "responsive" but ugly at 375px

## The mindset

Mobile is not the desktop design squeezed; it is the SAME hierarchy re-expressed for
a narrow, touch driven, often slower context. Design the phone view as its own
composition: what dominates, what breathes, what gets cut.

## Layout rules

- Build with fluid primitives so most components never need a media query:
  `grid-template-columns: repeat(auto-fit, minmax(min(100%, 20rem), 1fr))`,
  flex wrap, `clamp()` for type and spacing.
- Breakpoints where the CONTENT breaks, not at device folklore. Usually two or
  three: ~640px, ~960px. Test between them, not just at them.
- Column collapse follows meaning: on mobile, the image that sat beside text now
  sits below the text it illustrates (headline first, always).
- Section padding steps down, never disappears: `--space-24` desktop → `--space-16`
  mobile. Type steps via the clamp scale in typography-that-reads.
- **No horizontal scroll, ever.** Wide content (tables, code) scrolls inside its own
  container; the page body never does. `overflow-x` on the body is a defect.

## Touch

- Interactive targets 44×44px minimum, 8px+ between adjacent targets
- Hover cannot be the only affordance: anything revealed on hover must be visible
  or tappable on touch
- The phone number is `tel:` linked, the address links to maps, the primary CTA sits
  within thumb reach near the top AND repeats at the bottom
- Sticky mobile nav earns its pixels: on a 667px screen, a 90px bar takes 13% of
  everything

## Mobile beauty specifically

- The hero headline wraps to at most 3 lines at 360px (that is what
  `--text-hero`'s clamp lower bound is for)
- One column does not mean one texture: keep the section rhythm variation
  (ground shifts, an edge to edge image) so mobile is not a monotone scroll
- Cut, don't cram: a 6 item desktop grid can be a 3 item mobile list plus a link.
  Deciding what mobile omits is design; shrinking everything is surrender.

## Performance is design on mobile

A beautiful page arriving in 6 seconds is an ugly page. Image discipline from
imagery-and-icons, compositor-only animation from motion-and-microinteractions,
fonts subsetted with `font-display: swap`. Test throttled (Fast 3G, 4x CPU): the
headline readable within ~2 seconds, no layout shift as assets land.

## Verify

DevTools at 360, 390, 768, 1024, 1440: squint test at each (one dominant element,
hierarchy intact), no horizontal scroll, targets tappable, hero headline ≤3 lines.
Then once on a REAL phone over cellular; the emulator lies about fonts, shadows,
and speed.
