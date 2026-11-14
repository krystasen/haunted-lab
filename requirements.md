# Requirements — Haunted Laboratory (Costume Contest)

## Introduction

A single-page haunted virtual laboratory. Users pick reagents, mix them in a
cauldron, discover recipes, and keep a reaction log. No login, no backend,
static hosting only. The ghostly UI is itself the Costume Contest entry.

## Requirements

### Requirement 1 — Reagent shelf

**User Story:** As a player, I want to pick reagents from a shelf, so I can
decide what goes into the cauldron.

#### Acceptance Criteria

1. WHEN the app loads THEN the system SHALL show exactly 8 reagents, each
   with a name and a visual glow colour.
2. WHEN a player clicks a reagent THEN the system SHALL add it to the
   cauldron, up to a maximum of 3 reagents.
3. WHEN a reagent already in the cauldron is clicked again THEN the system
   SHALL NOT add a duplicate.
4. WHEN a player clicks a reagent already in the cauldron's list THEN the
   system SHALL remove it from the cauldron.

### Requirement 2 — Cauldron mixing

**User Story:** As a player, I want to mix the reagents in the cauldron,
so I can see what potion they make.

#### Acceptance Criteria

1. WHEN the cauldron is empty THEN the system SHALL disable the Mix button.
2. WHEN the player mixes a set of reagents that matches a known recipe THEN
   the system SHALL show that recipe's name, glow colour, and description.
3. WHEN the player mixes a set with no known recipe THEN the system SHALL
   show a deterministic fallback reaction (same set → same reaction, every
   time) and SHALL NOT show an error or an empty state.
4. WHEN a mix completes THEN the system SHALL clear the cauldron.

### Requirement 3 — Recipe book

**User Story:** As a player, I want discovered recipes to be recorded, so I
can collect them and try to find them all.

#### Acceptance Criteria

1. WHEN a known recipe is mixed for the first time THEN the system SHALL add
   it to the recipe book and update the discovered count.
2. WHEN a known recipe is mixed again THEN the system SHALL NOT duplicate it
   in the book.
3. WHEN the page reloads THEN the system SHALL keep the discovered recipes
   (local storage is acceptable; no account is required).

### Requirement 4 — Reaction log

**User Story:** As a player, I want a log of my reactions, so I can look
back at what I mixed.

#### Acceptance Criteria

1. WHEN a mix completes THEN the system SHALL prepend one log entry with the
   reagents mixed, the reaction name, and the time.
2. WHEN the player clears the log THEN the system SHALL remove all entries.

### Requirement 5 — Ghost UI

**User Story:** As a player, I want the whole lab to look haunted, so the
Costume Contest theme is visible in every screen, not just in one banner.

#### Acceptance Criteria

1. WHEN the app loads THEN the system SHALL render a dark theme with ghost
   glow, fog-like gradients, and a floating ghost element.
2. WHEN a reaction occurs THEN the system SHALL show its glow colour in the
   result (no reaction SHALL render as plain unstyled text).
