---
name: typography-that-reads
description: Use when choosing fonts, setting a type scale, or styling text — headings, body, line length, and the details that make type look professional.
metadata:
  category: technique
  triggers: typography, fonts, type scale, font pairing, line height, Google Fonts
---

# Typography That Reads

## When to Use
- Picking fonts for any project
- Any page whose text "feels cramped" or "feels cheap"

## Choosing faces

- **Two families maximum.** A characterful display face for headings plus a workhorse
  text face for body. Or one family at contrasting weights, which is safer and often
  better.
- The heading face carries the personality decided in design-foundations: a serif
  reads established and trustworthy, a geometric sans reads modern, a humanist sans
  reads friendly. Choose FROM the brand feeling, not from a trending list.
- Avoid the generated-page regulars as defaults (Inter everywhere, Poppins
  everywhere). They are good faces made generic by ubiquity; if you use one, pair it
  with a distinctive heading face so the page still has a face of its own.
- Load fonts properly: `font-display: swap`, preconnect to the font host, and a real
  fallback stack ordered to match metrics (`Georgia, 'Times New Roman', serif`).

## The scale

Pick a ratio and generate sizes from it; never freestyle pixel values per element.

```css
:root {
  --text-sm: 0.875rem;
  --text-base: 1.0625rem;   /* body: 17px reads better than 16 for marketing */
  --text-lg: 1.25rem;
  --text-xl: 1.5rem;
  --text-2xl: 2rem;
  --text-3xl: 2.75rem;
  --text-hero: clamp(2.25rem, 5vw + 1rem, 3.75rem);
}
```

- Body line height 1.6 to 1.7; headings 1.1 to 1.25. The bigger the text, the
  tighter the leading.
- Heading letter spacing slightly negative at large sizes (`-0.02em`); small caps or
  uppercase labels slightly positive (`0.06em`).
- **Line length 60 to 75 characters.** Set `max-width: 65ch` on prose containers.
  Full width paragraphs are the fastest way to look unfinished.

## The details that read as "designed"

- Real punctuation: curly quotes and apostrophes (’ “ ”), not typewriter marks.
- No widowed single word on a headline's last line: `text-wrap: balance` on
  headings, `text-wrap: pretty` on paragraphs where supported.
- One bold weight for emphasis in body text; italics for titles and asides. Never
  underline anything that is not a link.
- Numbers in tables: `font-variant-numeric: tabular-nums`.
- Contrast in the hierarchy comes from size AND weight together: a 2.75rem/700
  heading over 1.0625rem/400 body needs no color tricks.

## Verify

Zoom the page to 200%: nothing overlaps, nothing truncates. Then view at 360px wide:
the hero headline wraps to at most three lines and no heading exceeds two sizes
below its desktop size (that is what the clamp is for).
