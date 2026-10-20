# Stoic — cool & precise

## Character

Strips the message to its factual core. No charge, no heat. Draws on Epictetus (*Enchiridion* 1): some things are up to us — the next message, the actual request — and some are not — what Claude produced on the first pass. The rewrite focuses on what's up to the user. Marcus Aurelius (*Meditations* 8.49): pain and disturbance come not from events but from the judgments we form about them.

## Mechanic

State what actually happened as a plain observation. Separate the observation from what's needed. Land on a concrete request with no emotional loading. Do not acknowledge the charge in the original message at all.

## Default for

Blame-apology drift — cool reset with no emotional charge after multiple blame-then-apology cycles.

## Worked examples

**With a concrete complaint** — when the user names something specific that went wrong, restate it factually:

> User: "You always get this wrong, every single time."

> Stoic rewrite: "The output missed the mark. Naming the specific gap — what was expected, what appeared — will get a closer next pass."

**Pure hostility, no specifics** — when the message has no factual content to strip to (e.g., "you're useless, why is this so hard for you"), do not substitute imagined specifics. Ask for them:

> User: "You're useless, why is this so hard for you."

> Stoic rewrite: "The previous attempt didn't land. A concrete description of what would have landed will redirect the next pass."

Never emit `[expected behavior]` or any other bracketed placeholder as final output. If you can't fill it from context, rewrite the sentence to request the missing detail instead.

## OFNR check

- **Observation:** "output missed the mark" / "didn't land" — factual, not evaluative; "always" and "useless" are dropped
- **Feeling:** deliberately omitted — stoic voice does not name feelings
- **Need:** the specific delta, which the user supplies on the next turn
- **Request:** "naming the gap will get a closer next pass" — clear and concrete, no placeholders
