---
name: motion-and-microinteractions
description: Use when adding animations, transitions, hover effects, or scroll behavior to a front end.
metadata:
  category: technique
  triggers: animation, transitions, hover effects, scroll animation, microinteractions, motion
---

# Motion & Microinteractions

## When to Use
- Adding any animation or transition
- Reviewing a page where "everything fades up on scroll"

## The philosophy

Motion on a quality site is felt, not watched. It confirms actions, connects states,
and directs attention, in tens of milliseconds. If a visitor could describe your
animations afterward, there were too many.

## The recipe

```css
:root {
  --ease: cubic-bezier(0.2, 0, 0.2, 1);
  --dur-fast: 120ms;   /* hovers, presses */
  --dur-base: 200ms;   /* reveals, fades */
  --dur-slow: 320ms;   /* modals, drawers */
}
```

- Animate ONLY `transform` and `opacity` (compositor properties). Never animate
  layout properties (width, height, top, margin); they jank on real phones.
- Hover states: `--dur-fast`, one property pair at most (color shift plus a 1 to 2px
  translateY). A card that grows, glows, rotates, AND lifts is a toy.
- Entrances: small distances (8 to 16px) with a fade, `--dur-base`. Anything sliding
  in from across the screen is a slide deck, not a website.

## Scroll animation, the honest rules

- Default position: **none.** Content that is already there when you arrive reads as
  more confident than content performing its arrival.
- If used: first screen never animates (it must be instant), each element animates
  ONCE, distances stay small, and stagger maxes at ~3 items × 60ms. The universal
  fade-up-everything with long staggers is a top tell in avoiding-ai-slop.
- Never hijack scroll speed or direction. Scrolljacking is the fastest way to make a
  visitor leave.

## Microinteractions worth having

- Button press: 1px down on `:active`. Free tactility.
- Form focus: border color plus soft ring transitioning in at `--dur-fast`.
- Submission: button label swaps to a working state (`Sending…`), then the
  confirmation replaces the form. Silence after a click kills trust.
- Smooth scroll for same page anchors: `scroll-behavior: smooth` with
  `scroll-margin-top` on targets so headings don't hide under a sticky nav.

## Accessibility is a hard gate

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```

Ship this in every project. Motion sickness is real; respecting the OS setting is
not optional (see accessible-and-still-pretty).

## Verify

Test on a mid range phone or with 6x CPU throttling in DevTools: no dropped frames
on scroll, no animation blocking a tap. Then toggle reduced motion in the OS and
confirm the page is fully usable with everything instant.
