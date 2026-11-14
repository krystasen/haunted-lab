# Design — Haunted Laboratory

## Overview

One static page (`index.html`, no build step, no framework). All state lives
in the browser: the current cauldron contents in memory, the recipe book and
reaction log in `localStorage`. Any static host can serve it (GitHub Pages,
Vercel, Netlify).

## Components

- **Reagent shelf** — 8 reagents, each `{ id, name, color, note }`.
  Rendered as buttons; click adds to the cauldron (max 3, no duplicates).
- **Cauldron** — the chosen set, shown as removable chips; Mix button
  (disabled when empty); result area showing the reaction name, glow colour,
  and description.
- **Recipe book** — discovered recipes, persisted under
  `haunted-lab-recipes` in localStorage.
- **Reaction log** — newest first, max 50 entries, persisted under
  `haunted-lab-log` in localStorage.

## Mixing rules

- A recipe is an exact, order-free set of 1–3 reagent ids. Lookup key is the
  sorted ids joined with `+`.
- 6 known recipes are defined in `RECIPES` in `index.html` (see README for
  the list). The starter defines 6 of a planned 6–8; add more by adding
  entries, not by changing the lookup.
- Unknown sets use a deterministic fallback: a small hash of the sorted key
  picks one of 3 fallback reactions. This guarantees the property
  "same set → same reaction" for every input, including unknown ones.

## Styling

Dark background (`#0b0b1a`), violet glow, green/ember accents. See
`.kiro/steering/ghost-design.md` — the steering file is the single source of
truth for palette, glow, and type; do not invent new accent colours in code
without updating it.

## Testing strategy

- **Property-based tests (planned, Week 2):** for every reagent set of size
  1–3, mixing twice gives the same reaction; no set produces an error or an
  empty result; the recipe book never contains duplicates.
- **Manual checks (Week 1):** each of the 6 known recipes mixes to its named
  result; an unknown set (e.g. Moonpetal + Bat Wing Dust) gives a fallback;
  reload keeps the recipe book and log.

## Decisions not yet made

- Exact deployment host (GitHub Pages is the default; decide in Week 3).
- Sound effects: optional, off by default, not in Week 1 scope.
- Sharing a reaction: copy-to-clipboard for a log entry, Week 3 if time.
