---
name: avoiding-ai-slop
description: Use when reviewing or building any page that must not look AI generated — the tell checklist and the fix for each tell.
metadata:
  category: discipline
  triggers: AI slop, looks generated, generic design, template look, ChatGPT design, purple gradient
---

# Avoiding AI Slop

## When to Use
- Final review pass on every page before it ships
- A client or teammate says a page "looks AI generated"
- Auditing an existing site for a redesign

## The tells, and the fix for each

Work the table top to bottom. Each row is a pattern that instantly reads as
generated because millions of generated pages share it.

| Tell | Fix |
|---|---|
| Purple/indigo gradient on white, or gradient text | Build the palette from the brand (see color-systems). If no brand color exists, derive one from the industry and locale, not from the model's favorite hue |
| Emoji as bullets, icons, or section markers (🚀 ✨ 💡) | Delete them. Use one real icon family or nothing (see imagery-and-icons) |
| Three identical cards in a row, each with icon, title, two lines | Vary the structure: one featured item with detail, others compact; or a list; or alternating rows. Equal thirds is the template's rhythm, not the content's |
| Dash-heavy copy, "it's not just X, it's Y", "seamless", "elevate", "unlock" | Rewrite per copy-that-sounds-human. The words are the loudest tell of all |
| Every section: centered heading, centered subline, centered grid | Break symmetry somewhere deliberate: left align the hero, offset an image, let one section run wide (see spacing-and-layout) |
| Uniform border radius + soft shadow on every single element | One radius token, one shadow recipe, applied only to true surfaces. Flat sections are allowed to be flat |
| Feature grid of six near-synonyms ("Fast. Reliable. Secure…") | Cut to the three that are true and provable, with a concrete sentence each |
| Placeholder energy: "Lorem", stock handshake photos, "John Doe" testimonials | Real content or no section. An empty testimonial slot beats a fabricated one, which is also a legal problem |
| Hero headline that names the category instead of the value ("Modern Solutions for Your Business") | Say the specific thing the specific customer gets (see beautiful-heroes) |
| Every animation is fade-up-on-scroll, staggered 100ms | Either remove them or make motion mean something (see motion-and-microinteractions) |
| Footer with four columns of links the site doesn't have | Footer contains only what exists: contact, hours, the real pages, legal |

## The deeper rule

Slop is not any single element; it is **unexamined defaults agreeing with each
other**. The checklist removes the surface tells, but the cure is upstream: make the
five decisions in design-foundations from the brand's actual identity, and the
defaults never enter.

## Review protocol

1. Open the page cold, squint test: could this be any company? If yes, it fails.
2. Read every visible sentence aloud (copy-that-sounds-human rules apply).
3. Walk the table above; log each hit as a finding with its fix.
4. Fix, then re-run once. Done means zero rows hit.
