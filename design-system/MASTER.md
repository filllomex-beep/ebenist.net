# MASTER — Michal Řičica · ebenist & restaurátor

Design system for ebenist.net. Source of truth for color, type, spacing, motion.
Product type: single-craftsman heritage portfolio (restoration / bespoke furniture, Prague, est. 1988).

## Tone
Museum archive, not luxury boutique. Quiet authority. The work is 40 years of hand
restoration for embassies, the National Museum and sacred interiors — the site should feel
like a well-set catalogue raisonné: parchment, ink, generous margins, photographs given room.

## Color

| Token | Hex | Use |
|---|---|---|
| `--paper` | `#F4EFE6` | page ground |
| `--paper-2` | `#EBE4D8` | alternating panels, image placeholders |
| `--paper-3` | `#E1D8C8` | hairline fills, chips |
| `--ink` | `#191411` | primary text, wordmark |
| `--ink-2` | `#3D342C` | secondary text |
| `--ink-3` | `#6F6357` | muted / captions (5.1:1 on paper) |
| `--walnut` | `#1E1713` | dark sections (hero, case study, contact) |
| `--walnut-2` | `#2A211A` | raised surface on dark |
| `--brass` | `#9A7B45` | rules, large display accents, accent on dark (4.5:1) |
| `--brass-deep` | `#7A6033` | accent *text* on paper (5.2:1) |

No gradients as decoration. The only "gradient" allowed is a photographic scrim over imagery.

## Type

- **Display:** Cormorant Garamond — 300 for hero, 400 for section heads, 300 italic for emphasis.
  Tracking tightens as size grows (`-0.02em` at display sizes).
- **Text / UI:** Inter — 300/400/500 only.
- **Labels:** Inter 500, `0.72rem`, `uppercase`, `letter-spacing: 0.18em`.
- Lead paragraphs set in Cormorant Garamond 400 at `clamp(1.15rem, 1.7vw, 1.5rem)`.
- Measure: 62–68ch for body, 34ch for hero display.

## Spacing & layout

- Container `1320px`, gutter `clamp(1.25rem, 5vw, 4rem)`.
- Section rhythm `clamp(6rem, 12vh, 11rem)` block padding.
- 12-column grid. Layouts are **asymmetric** — label column (2–3 cols) + content column (6–8 cols),
  offset, never centered boilerplate.
- Hairlines `1px solid var(--line)` — used as editorial rules, not as boxes. Avoid card borders on all four sides.

## Motion

- Easing: entrances `cubic-bezier(0.16, 1, 0.3, 1)`; UI `cubic-bezier(0.4, 0, 0.2, 1)`.
- Durations: UI/hover `0.2–0.3s`; section reveals `0.7s`; stagger `0.07s`.
- Reveals via `IntersectionObserver` (`once`, `-12%` margin): `opacity 0→1`, `translateY(22px)→0`.
- Images: `scale(1.03)` on hover, `0.7s` expo. Hero uses a 24s ken-burns on `transform` only.
- Animate **transform and opacity only**. `prefers-reduced-motion` disables all of it.

## Anti-patterns (do not ship)

- Purple/pink AI gradients, glassmorphism, neon glows.
- Emoji as icons — inline SVG only.
- Centered hero + three equal feature cards.
- Fake testimonials, fake stats, or a contact form with no backend.
- Drop shadows on everything; use one soft shadow reserved for the lightbox only.
