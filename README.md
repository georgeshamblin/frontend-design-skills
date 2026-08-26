# Front End Design & Beauty Skills

A Claude Code skills library for building front ends that look designed, not
generated. Every skill pushes against the default AI aesthetic: the purple
gradients, the emoji bullet lists, the dash-riddled copy, the three identical cards
in a row. The goal is pages a human designer would sign.

Two house rules run through the whole kit:

1. **Copy sounds human.** No dash used as punctuation unless it is quite literally
   necessary. Full sentences, concrete words, a voice that belongs to the brand.
2. **Restraint reads as quality.** Fewer fonts, fewer colors, fewer effects, more
   whitespace, and every decision made on purpose.

## Install

**Per-project** (recommended):

```bash
mkdir -p .claude/skills
cp -R skills/* .claude/skills/
```

**Global:**

```bash
cp -R skills/* ~/.claude/skills/
```

## The skills

| Skill | Use it for |
|---|---|
| [design-foundations](skills/design-foundations/SKILL.md) | The taste baseline: hierarchy, restraint, intention. Load before any visual work |
| [avoiding-ai-slop](skills/avoiding-ai-slop/SKILL.md) | The tell checklist. What makes a page scream "generated" and how to remove each tell |
| [typography-that-reads](skills/typography-that-reads/SKILL.md) | Type scale, font pairing, real quotes, line length, rhythm |
| [color-systems](skills/color-systems/SKILL.md) | Building a palette with a point of view, tokens, dark mode, contrast |
| [spacing-and-layout](skills/spacing-and-layout/SKILL.md) | Spacing scale, grids, asymmetry, whitespace as a feature |
| [beautiful-heroes](skills/beautiful-heroes/SKILL.md) | Openings that feel like the brand instead of a template |
| [component-polish](skills/component-polish/SKILL.md) | Buttons, cards, forms, shadows, radii: the details that separate finished from generated |
| [motion-and-microinteractions](skills/motion-and-microinteractions/SKILL.md) | Transitions that feel expensive and respect reduced motion |
| [copy-that-sounds-human](skills/copy-that-sounds-human/SKILL.md) | The wording skill: the no dash rule, banned AI phrases, voice |
| [imagery-and-icons](skills/imagery-and-icons/SKILL.md) | One icon family, image treatment, never emoji as UI |
| [responsive-beauty](skills/responsive-beauty/SKILL.md) | Pages that stay beautiful at every width, not merely functional |
| [accessible-and-still-pretty](skills/accessible-and-still-pretty/SKILL.md) | Contrast, focus states, and semantics done with taste |

## How to use the kit

For a new page or site, load `design-foundations` and `avoiding-ai-slop` first, then
pull specific skills as the work touches their territory. For a redesign or review,
start with `avoiding-ai-slop` as the audit checklist.
