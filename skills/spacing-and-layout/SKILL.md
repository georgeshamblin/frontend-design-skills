---
name: spacing-and-layout
description: Use when laying out pages or components — spacing scale, grids, section rhythm, whitespace, and breaking template symmetry.
metadata:
  category: technique
  triggers: layout, spacing, whitespace, grid, padding, margins, sections, cramped
---

# Spacing & Layout

## When to Use
- Structuring any page
- A page that feels cramped, or so evenly spaced it feels like a template

## The scale

One base unit, multiples only:

```css
:root {
  --space-1: 0.25rem;  --space-2: 0.5rem;  --space-3: 0.75rem;
  --space-4: 1rem;     --space-6: 1.5rem;  --space-8: 2rem;
  --space-12: 3rem;    --space-16: 4rem;   --space-24: 6rem;
  --space-32: 8rem;
}
```

Every margin, padding, and gap is a token. An eyeballed `margin: 37px` is how
inconsistency creeps in.

## Proximity is meaning

Space communicates relationships before any words do:

- Space WITHIN a group is always smaller than space BETWEEN groups. A heading sits
  close to its paragraph (`--space-3`) and far from the previous section
  (`--space-24`). When this inverts, the page reads as scrambled.
- Section padding is generous: `--space-24` vertical on desktop minimum for
  marketing pages. Cramped sections read as cheap; air reads as confident.
- But equal air everywhere is its own tell. Vary section rhythm deliberately: a
  dense proof section between two airy ones creates tempo.

## Structure

- **Container:** one max width for content (~72rem), one for prose (`65ch`),
  centered, with `--space-6` side padding on mobile.
- **Grid with hierarchy.** Equal thirds all the way down is the template look. Let
  content dictate: a 2:1 split with a featured item, a 5:7 text and image pair, a
  full width statement between grids.
- **Break the symmetry once per screen.** Left aligned hero instead of centered. An
  image that bleeds to the viewport edge. A pull quote hanging into the margin.
  Asymmetry placed on purpose is what separates layout from stacking.
- Alignment is sacred: everything snaps to the container edges or the grid. Broken
  symmetry means an intentional exception, never a sloppy near miss.

## Vertical rhythm rules

- No two adjacent sections styled identically (same ground, same alignment, same
  grid) or they blur into one long scroll
- Every section starts with a clear heading level and one job; a section doing two
  jobs is two sections
- The page ends with ONE call to action section, not a stack of three competing
  closers

## Verify

Screenshot the page and draw the grid lines mentally: could you reconstruct the
layout from a handful of tokens and rules? Then check mobile (see
responsive-beauty): the rhythm must survive the collapse to one column, with section
padding stepped down (`--space-16`) rather than deleted.
