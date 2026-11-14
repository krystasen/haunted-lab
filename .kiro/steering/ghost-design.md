# Steering — Ghost design (haunted laboratory)

Apply to every UI change in this project. If a change conflicts with this
file, change the file first and say so — do not silently drift.

## Palette (fixed)

- Background: `#0b0b1a` (near-black violet), panels `#171730`
- Ink: `#e8e6ff`; dim text: `#9a97c7`
- Glow green: `#7dff9e`; ember orange: `#ff9d45`; ghost violet: `#b388ff`
- No new accent colours without updating this file.

## Type and mood

- Serif display type (Georgia / Times); no rounded "cute" sans for headings.
- The ghost (👻, floating animation) is the mascot: present on the main
  screen, never more than one per view, never animated faster than 3 s.
- Fog: soft radial gradients, never a full-screen image that hurts text
  contrast. Text contrast must stay readable on the dark background.

## Interaction rules

- Every reaction shows its glow colour in the result — never plain text.
- Buttons give immediate feedback (hover glow); the Mix button is disabled
  when the cauldron is empty, never clickable-to-error.
- No login walls, no modals on first load, no sound without a user action.
