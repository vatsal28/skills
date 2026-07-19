# de-slopify — weak signals & human-writing calibration

This file exists to prevent false positives. Read it whenever a diagnosis
rests on thin evidence, or when a "human-written" draft is being reviewed for
slop. Its two jobs: list what NOT to flag, and describe what real human writing
looks like so the rewrite target stays honest.

Source basis: Wikipedia's "Signs of human writing" and "Ineffective
indicators" sections, plus the cross-source consensus that detection is
probabilistic (see `../LICENSE`).

---

## The core discipline

- **No single sign is proof.** Signs are probabilistic and co-occurring. Act on
  clusters and density, not lone hits.
- **Weak signals alone never warrant an edit.** If the only thing "wrong" with
  a passage is one item from the list below, leave it and say the text doesn't
  need de-slopping.
- **Human speech is drifting toward LLM patterns.** As people absorb these
  phrasings, aggressive pattern-hunting produces more false positives over
  time. Bias toward restraint.
- **Detection ability varies.** Casual readers do barely better than chance at
  spotting AI text; heavy LLM users reach roughly 90%. Neither figure makes any
  individual signal reliable in isolation.

---

## Ineffective indicators — never cite these as slop, never "fix" them for their own sake

- **Perfect grammar and spelling.** Cleanliness is not a tell. Do not inject
  errors (that's a hard safeguard).
- **Formal or academic vocabulary in general.** "Utilize" in a legal brief,
  "moreover" in a philosophy paper — genre-appropriate, not slop.
- **A "bland" feel alone.** Blandness without any concrete tell is not
  actionable. Boring human writing exists.
- **Isolated transition words.** A single "Additionally," or "Furthermore," is
  weak. Only rotation/density (B11) rises to MODERATE.
- **Oxford commas.** Millions of humans use them by house style. Not a signal.
- **American vs. British spelling.** A regional default, not evidence.
- **Correct or incorrect markup on its own.** Curly quotes, an em dash, a
  thematic break — none is proof in isolation.
- **Mixed casual/formal register.** Humans code-switch mid-piece; this is not a
  tell by itself.

If your entire case for "this is slop" is built from the list above, the
correct output is: minimal or no changes, with a one-line note that the text
reads fine.

---

## Weak patterns from the catalog (handle with restraint)

These carry a WEAK (or WEAK-leaning) rating in `patterns.md`. Note them only in
a cluster; do not remove on sight:

- **B10** complex prepositional phrases ("in the context of")
- **C7** curly quotes where straight are expected (fix only in code/plaintext)
- **C8** hyphenated-pair uniformity — vary only where the open form is equally
  correct; **never** de-hyphenate mechanically (that breaks grammar)
- **C11** Oxford comma, American spelling — documentation only, do not act
- A lone **B1** vocabulary token — "robust," "delve," "crucial" once is noise

---

## Signs of human writing (calibration targets for the rewrite)

Aim the rewrite at these, not at a scrubbed-clean ideal:

- **Simple constructions.** is / are / has, not "serves as / functions as."
- **Plain verbs.** wrote (not authored), used (not utilized), died (not passed
  away), showed (not showcased).
- **Confident superlatives and firsts.** "one of the best," "was the first to,"
  stated without hedging. AI tends to over-qualify; humans commit.
- **Mild, unstacked hedges and intensifiers.** "very," "perhaps," "tends to,"
  "I think" — used once, not piled up.
- **Some wordiness is human.** "as a result of," "in order to," "the fact
  that" appear in real writing. A rewrite polished to perfect efficiency reads
  as machine-made. Leave some natural slack.
- **Rhythm variation.** Real writing mixes long and short sentences, and
  sometimes fragments. Uniform sentence length is itself a slop signal.
- **Opinions, uncertainty, first person, mess.** Where the artifact is authored
  in first person and already gestures at a stance, real writers show a view,
  admit mixed feelings, and don't tie every thread into a bow.

**Important limit:** these are targets, not licenses to fabricate. Add a stance,
a superlative, or a first-person aside only when it reflects something the
author actually holds or the source actually supports. Never manufacture
personality to hit a calibration target — a fake opinion is worse than a bland
sentence.

---

## Soulless-but-clean is still slop

The subtle failure the ineffective-indicators list can mask: text with perfect
grammar, genre-appropriate words, and no obvious tic — that is still lifeless.
Signs: uniform sentence length, zero opinion, no uncertainty, no first person
where it would be natural, everything resolved.

The fix is **rhythm and (opt-in) real stance**, not decoration and not invented
color. If the artifact and author don't support a stance (a neutral reference
paragraph, a formal report), leave it clean and plain — that is the correct,
finished state, not a defect to be jazzed up.
