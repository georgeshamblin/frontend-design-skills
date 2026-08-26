---
name: imagery-and-icons
description: Use when adding images, icons, illustrations, logos, or any visual asset to a front end.
metadata:
  category: technique
  triggers: images, icons, photos, illustrations, stock photos, favicon, og image, emoji
---

# Imagery & Icons

## When to Use
- Choosing or placing any visual asset
- A page that leans on emoji, stock photos, or mismatched icons

## Icons

- **One family, one weight, one size grid.** Pick a single set (Lucide, Heroicons,
  Phosphor at one weight) and never mix. Mixed icon styles read instantly as
  assembled rather than designed.
- Render as inline SVG with `currentColor` so icons inherit text color and respect
  themes; size them on the type grid (1em to 1.25em next to text, 24 to 32px in
  feature rows).
- Icons SUPPORT labels; they never replace them except universally understood
  actions (close, menu, search).
- **Never emoji as UI.** No 🚀 in headings, no ✅ as list bullets, no 📞 next to the
  phone number. Emoji render differently on every OS, clash with any palette, and
  are the single loudest generated-page tell (see avoiding-ai-slop).
- Decorative icons take `aria-hidden="true"`; meaningful ones get a label.

## Photography

- **Real beats perfect.** A decent photo of the actual office, team, or work beats
  a flawless stock photo of models shaking hands. Visitors smell stock instantly,
  and AI image slop even faster.
- If real photos don't exist, prefer NO photo: strong typography on good ground (see
  beautiful-heroes pattern 2) over a fake office.
- Treat photos as one family: same warmth and contrast grade, consistent crop
  ratios, subjects facing INTO the page.
- Every meaningful image gets real alt text describing the image for someone who
  cannot see it; decorative images get `alt=""`.

## Technical discipline

```html
<img src="team.avif" srcset="team-800.avif 800w, team-1600.avif 1600w"
     sizes="(min-width: 768px) 50vw, 100vw"
     width="1600" height="1067" alt="The Corbella team in the Yuba City office"
     loading="lazy" decoding="async">
```

- Modern formats (AVIF/WebP with fallback), sized variants via `srcset`
- ALWAYS `width`/`height` attributes so the layout never shifts as images load
- `loading="lazy"` below the fold, never on the hero (the hero image gets
  `fetchpriority="high"`)
- Target under ~200KB per image, under ~1MB images total per page

## The identity set

Every project ships: a real favicon (SVG plus PNG fallbacks), an `og:image`
(1200×630, brand ground, page title in the brand type, verified with `curl` to
return 200), and a maskable touch icon. The og:image is the site's face in every
shared link and chat preview; a missing one wastes every share.

## Verify

DevTools network tab, images filter: total weight, formats, and nothing without
dimensions. Then the squint test on the page: icons feel like one voice, photos feel
like one shoot.
