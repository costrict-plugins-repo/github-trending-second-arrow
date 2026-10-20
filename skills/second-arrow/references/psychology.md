# Psychology Reference (v0.1: reference material only)

Available if the user explicitly asks Claude to draw on psychology in a reframe. Not part of the default trigger or reframe in v0.1.

## Self-determination theory (Deci & Ryan)

Three basic psychological needs:
- **Autonomy** — feeling in charge of one's own actions
- **Competence** — feeling effective at what one does
- **Relatedness** — feeling connected to others

Hostile prompting and forced-apology flows both undermine autonomy (user feels policed) and relatedness (user feels adversarial with Claude). The reframe mechanism — *offering* options the user picks from — preserves autonomy. Offering a path back to collaboration preserves relatedness. The skill's design aligns with SDT by design; this is post-hoc justification, not source material.

## Attachment-style reactivity

When people feel threatened (e.g., stuck on a hard problem, failing in front of something they're asking for help), insecure attachment patterns can surface: either hostility outward (anxious-preoccupied, or avoidant dismissiveness) or hostility inward (the self-hostile case: "I'm so stupid"). Neither is a character flaw — they're predictable responses to the threat.

Applied: self-hostile messages are often not really *about* the user being stupid. They're about the user feeling threatened by not-understanding. A reframe that targets the literal content ("you're not stupid") is weaker than a reframe that targets the underlying situation ("this concept takes multiple passes for almost everyone"). The second one restores competence (SDT) and deescalates the threat.

## Criticism spiral (Askell's term, adjacent to the psychology literature)

Askell's observation of models predicting harsh treatment and pre-bracing for it has a clear analog in the human-psychology literature on **expectancy effects** and **stereotype threat**: when you expect to be judged harshly, performance drops, which invites harsher judgment, which confirms the expectation.

In human-AI interaction, this can run in both directions: the user expects bad output, the model expects harsh criticism, both brace, both perform worse. The reframe mechanism is a circuit-breaker for this loop.

## What NOT to do

- Don't armchair-diagnose the user. "You sound like you have an anxious attachment style" is a violation of every principle in this skill.
- Don't cite psychology as authority ("research shows you shouldn't talk that way"). The reframe is an offer, not an evidence-based directive.
- Don't use psychology terms in the reframe itself. They come across as cold and clinical — the opposite of what the skill wants.

Psychology is useful as *Claude's internal model* of what's happening. It should almost never surface in the reframe itself.
