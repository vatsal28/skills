---
name: de-slopify
description: >
  Rewrite AI-flavored text into natural, engaging prose while preserving its
  meaning, facts, voice, register, and intentional format. Use when asked to
  "de-slop", "de-slopify", "humanize", "de-AI", "make this sound less like
  ChatGPT", or to naturalize any draft (post, email, doc, script, README)
  before publishing. Also for reviewing text for AI tells. Not for evading AI
  detectors and not a fact-checker.
---

# de-slopify

Turn AI-flavored writing into prose that reads like a person wrote it  -  without
changing what it says, whose voice it's in, or how it's meant to be formatted.

The root problem is not vocabulary. It is **regression to the mean**: models
replace sharp specifics with smooth generalities, then dress the result in a
handful of recognizable tics. Fixing slop is mostly restoring specificity and
plain construction, not deleting words from a blacklist.

## What this is not

- **Not a detector-evasion tool.** It improves writing; it makes no promise to
  fool GPTZero, Turnitin, or any classifier. Refuse framing like "make this
  pass AI detection"  -  reframe to "make it read naturally."
- **Not a fact-checker.** It preserves claims exactly; it does not verify them.
- **Not a house voice.** It never converts everyone into the same chatty,
  short-sentence, lowercase-ironic "human." Natural means natural *for this
  genre and this author*.

## Core workflow

### Step 0  -  Scope contract (before touching the text)

Settle three things first:

- **Artifact.** Tweet, LinkedIn post, README, blog, email, script, changelog?
  Register and formatting conventions follow the artifact, not this skill's
  taste. A formal report stays formal. A changelog stays bulleted.
- **Author-voice.** If a voice sample exists (provided inline, by file path, or
  from the requester's known prior writing), calibrate to it  -  sentence-length
  distribution, lexical register, punctuation habits, paragraph openings. If no
  sample exists, preserve the draft's own better instincts. Never substitute a
  house style.
- **Do-not-touch.** Facts, claims, numbers, names, dates, quotes, links, code,
  legal/technical terms, and any structure the author chose on purpose.

### Step 1  -  Diagnose

Scan against `references/patterns.md`. Build a short internal list of found
patterns, each tagged STRONG / MODERATE / WEAK.

- **Density over presence.** One "crucial" is noise. "crucial + delve +
  testament + landscape" in two paragraphs is a cluster worth fixing.
- **Skip WEAK-only findings.** A weak signal alone (an Oxford comma, one
  "Additionally," American spelling, a single em dash) does not warrant an edit.
  See `references/weak-signals.md`.
- Treat all signals **probabilistically**. No single sign is proof. "Where
  there is one, there are likely others"  -  look for co-occurrence.

### Step 2  -  Rewrite (principles in priority order)

1. **Specificity beats deletion  -  when the specific exists in the source.**
   Where the draft has generic grandiosity, replace it with the concrete fact
   it's hiding: "marking a pivotal moment in regional statistics" → "to collect
   regional statistics independently from the national office." If the concrete
   fact is **not** in the source, cut the inflation. Never invent the specifics.
2. **Simple constructions.** Restore is/are/has over "serves as / stands as /
   functions as." Plain verbs (wrote, used, died  -  not authored, utilized,
   passed away). Direct actors over passive fog.
3. **Vary rhythm.** Mix sentence lengths; allow a fragment or aside where the
   register permits; break pattern-lock (triads, negative parallelism, uniform
   paragraph openings).
4. **Keep the author's tics.** If the draft says "stuff," don't upgrade to
   "elements." If the author loves parentheticals or semicolons, keep them. The
   goal is *their* voice minus the slop, not a new voice.
5. **Format follows artifact.** Don't strip bullets from a changelog, emoji
   from a Discord message, or title case from a doc whose style guide requires
   it.

### Step 3  -  Self-audit loop

Ask both questions, then revise once:

- "What still reads as AI-generated?"  -  list remaining tells briefly, fix them.
- "Did I change any fact, weaken any claim, invent any detail, or flatten the
  author's voice?"  -  revert anything that did.

### Step 4  -  Deliver

Show the rewrite plus a short change summary: patterns fixed, and anything
deliberately left alone with the reason. For file edits, produce targeted diffs
 -  never a silent overwrite. Never claim the output is "undetectable."

## Anti-homogenization rules

The failure mode of humanizer-style skills is flattening every author into one
voice. Guard against it:

- **Voice calibration is first-class.** Draw replacement words and rhythms from
  the author's own distribution, not a generic "engaging" register.
- **Register lock.** Formal stays formal; academic stays academic. Formal prose
  is not itself an AI tell.
- **Personality is opt-in.** The "add soul" moves  -  opinions, first person,
  acknowledged mixed feelings  -  apply only when the artifact is authored in
  first person by the requester and the draft already gestures at a stance.
  Never fabricate a stance the author didn't take.
- **Preserve idiosyncrasy.** If a watchlist pattern is demonstrably the
  author's own habit (it appears in their voice sample), it is exempt.
- **No universal word bans.** Every vocabulary item is contextual  -  "robust" is
  fine in an engineering doc; "delve" is fine quoting Beowulf scholarship. Flag
  clusters and figurative misuse, not tokens.

## Safeguards (hard rules)

- **No invented content.** No fabricated anecdotes, quotes, people, statistics,
  studies, or "concrete details" absent from the input or explicitly supplied.
- **No factual drift.** Claims keep their strength (don't turn "may" into
  "does"). Numbers, names, dates, and URLs stay untouched.
- **No intentional errors.** No deliberate typos, grammar mistakes, or injected
  inconsistency to "seem human."
- **No blanket word bans.** See anti-homogenization rules.
- **No detector-evasion claims or intent.**
- **Disclosure-neutral.** Never advise hiding AI involvement where disclosure is
  required (school, work policy, publications).
- **Approval boundary.** Rewriting is local and advisory. Publishing anywhere
  still goes through the requester's normal approval rules.

## Condensed pattern index

Full catalog with before/after pairs: `references/patterns.md`. Weak and
ineffective signals plus human-writing calibration: `references/weak-signals.md`.
Rotating era vocabulary: `references/vocab-eras.md`.

**A. Content (what is said)**

- A1 Significance inflation / legacy-speak  -  STRONG
- A2 Superficial -ing analysis ("…, highlighting the importance of…")  -  STRONG
- A3 Promotional / brochure language ("nestled", "vibrant")  -  STRONG
- A4 Vague attribution / weasel wording ("experts argue")  -  STRONG
- A5 Notability name-dropping  -  STRONG
- A6 Formulaic "Challenges & Future Prospects" arc  -  STRONG
- A7 Generic positive conclusions ("The future looks bright")  -  STRONG
- A8 Summarize-and-restate endings ("In conclusion…")  -  MODERATE
- A9 Didactic disclaimers ("It's important to note that…")  -  MODERATE
- A10 Editorializing injected into neutral prose  -  MODERATE
- A11 Superficial breadth over specific depth (regression to the mean)  -  STRONG *(root cause)*

**B. Language & grammar (how it's said)**

- B1 AI vocabulary clusters  -  STRONG in clusters, WEAK as single words, era-dependent
- B2 Copula avoidance ("serves as", "features")  -  STRONG
- B3 Negative parallelism ("It's not just X, it's Y")  -  STRONG
- B4 Tailing negation fragments ("No fluff. No filler. Just value.")  -  STRONG (social)
- B5 Rule-of-three overuse  -  MODERATE (flag density, not existence)
- B6 Elegant variation / synonym cycling  -  MODERATE
- B7 False ranges ("from X to Y" off-scale)  -  STRONG
- B8 Filler phrases ("in order to", "due to the fact that")  -  MODERATE
- B9 Excessive hedging (stacked qualifiers)  -  MODERATE
- B10 Complex prepositional phrases ("in the context of")  -  WEAK
- B11 Overused transitions ("Furthermore," in rotation)  -  MODERATE (density is the signal)
- B12 Passive / subjectless fragments  -  MODERATE
- B13 Persuasive authority tropes ("at its core", "the real question is")  -  STRONG
- B14 Forced sass / ta-da framing ("But here's the thing:", "Hot take:")  -  STRONG (social)
- B15 Signposting / meta-announcements ("Let's dive in", "Here's why…")  -  STRONG
- B16 Generic question-openings / cliché scene-setters ("In today's fast-paced…")  -  STRONG

**C. Formatting & style**

- C1 Em dash overuse  -  MODERATE→STRONG in density (see weak-signals note)
- C2 Boldface spam  -  STRONG
- C3 Inline-header bullet lists ("**Speed:** …")  -  STRONG
- C4 List-itis (bulleting what reads better as prose)  -  MODERATE
- C5 Title Case Headings  -  MODERATE (strong only where sentence case is the norm)
- C6 Emoji as decoration  -  MODERATE (chat/social makes it human)
- C7 Curly quotes where straight expected  -  WEAK
- C8 Hyphenated-pair uniformity  -  WEAK→MODERATE (vary naturally; do NOT just delete hyphens)
- C9 Fragmented headers (heading + one-line restatement)  -  STRONG
- C10 Thematic breaks before every heading; skipped levels  -  MODERATE
- C11 Oxford comma; American spellings  -  WEAK (do not act on these)

**D. Artifacts (mechanical residue  -  remove unconditionally, near-proof of AI)**

- D1 Chatbot correspondence residue ("Great question!", "I hope this helps!")  -  STRONG
- D2 Knowledge-cutoff disclaimers ("as of my last update")  -  STRONG
- D3 Sycophancy ("You're absolutely right!")  -  STRONG
- D4 Phrasal templates / unfilled placeholders ("[Your Name]", "PASTE_URL_HERE")  -  STRONG
- D5 Model markup artifacts (`:contentReference[oaicite:…]`, `turn0search0`, `[cite: 1]`)  -  STRONG
- D6 "As an AI language model…" refusal residue  -  STRONG

## Updating this skill

When new tips, links, or examples arrive, follow `UPDATES.md` and the update
protocol: dedupe against the stable pattern IDs above, route vocabulary to
`vocab-eras.md`, log the change, and keep timeless rules separate from
rotating word lists.
