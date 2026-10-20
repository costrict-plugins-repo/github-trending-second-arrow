---
description: Configure the preferred reframe voice for the second-arrow skill (set, random, or reset)
argument-hint: "[name | random | reset]"
---

# /voice — Configure Reframe Voice

Sets or clears the preferred voice used when the second-arrow skill fires a reframe. If a voice is set, reframes skip the picker and rewrite directly in that voice.

The user invoked: `/voice $ARGUMENTS`

## How to handle the invocation

### No args (`$ARGUMENTS` is empty)

Read the stored voice preference from memory first (if any), then present an interactive picker using the **AskUserQuestion** tool so the user can click a voice instead of typing.

First, output one line stating the current state:

```text
Current voice: <name> | not configured
```

Then call `AskUserQuestion` with a single question:

- **question**: `"Which voice should reframes use?"`
- **header**: `"Voice"`
- **multiSelect**: `false`
- **options** (in this order):
  1. `Carnegie` — `"Friendly & practical. Lets the user save face."`
  2. `Stoic` — `"Cool & precise. Names what was asked vs. what was given."`
  3. `Daoist` — `"Soft & indirect. Yields rather than confronts."`
  4. `Confucian` — `"Names the reciprocity directly."`
  5. `Second Arrow` — `"Separates the real frustration from the added layer."`
  6. `Metta` — `"Warm & steady. Strong fit for self-hostile messages."`
  7. `Askell` — `"Names what this pattern does to the work."`
  8. `Random` — `"Claude picks contextually per trigger type."`
  9. `Reset (clear preference)` — `"Return to the unconfigured picker experience."`

When the user picks an option, treat it exactly as if they had run the corresponding `/voice <name>`, `/voice random`, or `/voice reset` form below — including saving (or removing) the memory entry and printing the matching confirmation line.

If they select the free-text "Other" option that AskUserQuestion provides, validate the input against the valid-name list and respond accordingly (set if valid, error if not).

### `/voice <name>`

Set the preferred voice. Voice names are case-insensitive.

Valid names: `carnegie`, `stoic`, `daoist`, `confucian`, `second-arrow`, `metta`, `askell`, `random`

Save the preference as a `feedback` memory:
> Preferred second-arrow reframe voice: [name]

Confirm to user:
> Voice set to **[Name]**. Reframes will use this voice going forward. Run `/voice reset` to return to the picker.

### `/voice random`

Sets contextual mode. Claude picks per trigger type using the Voice defaults table — no fixed preference.

Save to memory:
> Preferred second-arrow reframe voice: random

Confirm:
> Voice set to **random**. Claude will pick contextually for each reframe (self-hostile → Second Arrow, hostility → Carnegie, drift → Stoic).

### `/voice reset`

Clear the stored preference. Find and remove the existing voice memory entry. Return to the unconfigured picker experience.

Confirm:
> Voice preference cleared. The picker will appear on the next reframe.

## Error handling

Unrecognized name:
> "[name]" isn't a valid voice. Valid options: `carnegie`, `stoic`, `daoist`, `confucian`, `second-arrow`, `metta`, `askell`, `random`
