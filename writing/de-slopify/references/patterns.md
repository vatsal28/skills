# de-slopify — full pattern catalog

Deduplicated taxonomy of AI-writing signs, merged from four sources (see
`../LICENSE` for attribution). Each entry carries a stable ID, a strength
rating, and a compact before → after pair.

**Strength ratings**

- **STRONG** — reliable tell; fix when found.
- **MODERATE** — fix when it reads badly or co-occurs with other tells.
- **WEAK / CONTEXT** — not reliable alone; do not blanket-remove. Detailed in
  `weak-signals.md`.

**Read this alongside two rules from `SKILL.md`:** signals are probabilistic
(density and co-occurrence matter, single hits usually don't), and specificity
beats deletion *only when the specific exists in the source* — never invent it.

Before/after pairs illustrate the shape of each pattern. They are not scripts.
The correct rewrite of any real draft depends on its artifact, register, and
author voice.

---

## A. Content-level patterns (what is said)

### A1 — Significance inflation / legacy-speak — STRONG
Inflated importance framing: "marking a pivotal moment," "stands as a
testament," "reflects broader trends," "enduring legacy," "setting the stage
for."

- Before: "The 1974 bylaw marked a pivotal moment, standing as a testament to
  the town's enduring civic spirit."
- After: "The 1974 bylaw let the town issue its own building permits."
  *(Only if the source contains that fact; otherwise: "The town passed a bylaw
  in 1974." Cut the inflation, don't replace it with invented substance.)*

### A2 — Superficial -ing analysis — STRONG
Tacked-on present-participle clauses that add fake depth: "…, highlighting the
importance of…," "…, reflecting the community's deep connection."

- Before: "The festival draws thousands, reflecting the region's deep cultural
  roots and underscoring its growing appeal."
- After: "The festival draws thousands." *(Keep a follow-on clause only if it
  states a real, sourced fact — e.g., "…, up from a few hundred in 2015.")*

### A3 — Promotional / brochure language — STRONG
Travel-brochure adjectives: "nestled," "vibrant," "rich tapestry,"
"breathtaking," "boasts," "renowned," "stunning."

- Before: "Nestled in the vibrant heart of the city, the café boasts a rich
  tapestry of flavors."
- After: "The café is on Grafton Street and roasts its own beans."

### A4 — Vague attribution / weasel wording — STRONG
One source inflated into a chorus: "experts argue," "observers have noted,"
"industry reports suggest."

- Before: "Experts argue the policy could reshape the sector."
- After: "In a 2025 op-ed, economist Dana Ríos argued the policy could reshape
  the sector." *(If the source names no one, cut the attribution rather than
  invent an authority.)*

### A5 — Notability name-dropping — STRONG
Listing coverage or presence as proof of importance: "maintains an active
social media presence," "has been featured in numerous outlets."

- Before: "She maintains an active social media presence and has been featured
  in numerous publications."
- After: Cut, unless a specific, sourced credential replaces it ("Her 2024
  paper in *Nature* was cited 300 times").

### A6 — Formulaic "Challenges & Future Prospects" — STRONG
Forced upbeat arc: "Despite these challenges, the project continues to thrive."

- Before: "Despite these challenges, the initiative continues to thrive and
  looks poised for growth."
- After: State the actual challenge and the actual status: "Funding fell 20% in
  2025; the program still runs three of its four clinics."

### A7 — Generic positive conclusions — STRONG
"The future looks bright," "Exciting times lie ahead."

- Before: "The future looks bright for the team."
- After: End on a concrete fact, or just stop. "The team's next release ships
  in March."

### A8 — Summarize-and-restate endings — MODERATE
"In summary…," "In conclusion…," a closing paragraph that repeats the piece.
Mostly older models, still common in essays.

- Before: "In conclusion, as we have seen, the three factors above all matter."
- After: Delete, or land a real final point instead of a recap.

### A9 — Didactic disclaimers — MODERATE
"It's important to note that…," "worth noting," safety caveats aimed at an
imagined reader.

- Before: "It's important to note that results may vary."
- After: "Results vary." *(Keep genuine, load-bearing caveats; cut reflexive
  ones.)*

### A10 — Editorializing into neutral prose — MODERATE
Value judgments injected where the genre expects neutrality.

- Before: "The remarkable and groundbreaking study changed everything."
- After: "The study measured X in 400 patients." *(In neutral/reference prose;
  in an opinion piece a stance is fine.)*

### A11 — Superficial breadth over specific depth — STRONG *(root cause)*
Regression to the mean: sharp specifics swapped for generic grandiosity. This
is the disease behind most of A1–A10.

- Before: "a titan of nineteenth-century industry"
- After: "the inventor of the first automatic train-coupling device"
  *(only because the source said so).* The de-slopify move is to pull the
  buried specific back to the surface — and, when there is none, to prefer the
  plain small truth over the big empty phrase.

---

## B. Language & grammar patterns (how it's said)

### B1 — AI vocabulary clusters — STRONG in clusters / WEAK as singles / era-dependent
delve, tapestry, testament, intricate, pivotal, crucial, foster, underscore,
showcase, landscape (abstract), interplay, garner, meticulous, robust, vibrant,
align with, enhance, boasts, bolstered, valuable, key (adj.). See
`vocab-eras.md` — these rotate by model era. Flag *clusters* and figurative
misuse, never a lone token.

- Before: "This crucial and intricate work underscores a pivotal shift in the
  landscape."
- After: "This work marks a real shift in the field." *(Then check: does the
  source say what shift? Name it.)*

### B2 — Copula avoidance — STRONG
"serves as," "stands as," "functions as," "features," "offers," "refers to" in
place of is/are/has.

- Before: "The library serves as a hub and features a wide selection."
- After: "The library is a hub and has a wide selection."

### B3 — Negative parallelism — STRONG
"It's not just X, it's Y," "Not only… but also…," "This isn't X — it's Y," and
reversed forms ("…rather than ideological purity").

- Before: "It's not just a tool. It's a movement."
- After: "It's a tool people organize around." *(Say the actual claim without
  the see-saw.)*

### B4 — Tailing negation fragments — STRONG (social-copy variant)
"No guessing.", "No fluff.", "No X. No Y. Just Z."

- Before: "No fluff. No filler. Just results."
- After: "Here's what it does." *(Or fold the promise into a real sentence.)*

### B5 — Rule-of-three overuse — MODERATE
Triads of adjectives/phrases/clauses forced everywhere. Humans use triads too —
flag density, not existence.

- Before: "fast, powerful, and intuitive… simple, elegant, and reliable…
  clean, modern, and flexible"
- After: Keep one earned triad; break the rest into plain description.

### B6 — Elegant variation / synonym cycling — MODERATE
Same referent renamed to avoid repetition: protagonist → main character →
central figure → hero. Non-native writers do this too; be gentle.

- Before: "The protagonist… the central figure… our hero… the main character…"
- After: Use one name (usually the actual name) consistently.

### B7 — False ranges — STRONG
"from X to Y" where X and Y aren't endpoints of any real scale.

- Before: "everything from marketing to philosophy to lunch"
- After: List them plainly, or name the real span: "marketing, philosophy, and
  where to eat."

### B8 — Filler phrases — MODERATE
"in order to," "due to the fact that," "at this point in time," "has the
ability to." Note: some wordiness is human (see `weak-signals.md`); don't
scrub to sterile efficiency.

- Before: "In order to reduce costs, due to the fact that margins were thin…"
- After: "To cut costs, because margins were thin…"

### B9 — Excessive hedging — MODERATE
Stacked qualifiers: "could potentially possibly." Single hedges are human;
stacks are the tell.

- Before: "This could potentially possibly help in some cases."
- After: "This might help." *(One hedge is fine.)*

### B10 — Complex prepositional phrases — WEAK
"in the context of," "taking into account," "with regard to." Weak alone; note
only in a cluster.

- Before: "In the context of the wider debate, taking into account all
  factors…"
- After: "In the debate…" / cut.

### B11 — Overused transitions — MODERATE (density is the signal)
Sentence-initial "Additionally," "Furthermore," "Moreover," "Consequently," in
stilted rotation. Isolated transition words are a weak tell; rotation/density
is the signal.

- Before: "Additionally, … Furthermore, … Moreover, … Consequently, …"
- After: Let most sentences start with their subject; keep a transition only
  where the logic genuinely turns.

### B12 — Passive voice / subjectless fragments — MODERATE
"No configuration file needed." "It should be noted."

- Before: "No configuration file is needed. Errors are handled automatically."
- After: "You don't need a config file. It handles errors for you." *(Passive
  is fine where the actor is genuinely unknown or irrelevant.)*

### B13 — Persuasive authority tropes — STRONG
"The real question is," "at its core," "fundamentally," "the heart of the
matter."

- Before: "At its core, the real question is fundamentally about trust."
- After: "The question is whether people trust it."

### B14 — Forced sass / ta-da framing — STRONG (social copy)
Manufactured edge or reveal: "But here's the thing:," "Hot take:," "And
honestly?," "The result?," "Then I realized:."

- Before: "But here's the thing: most people get this completely wrong."
- After: "Most people get this wrong." *(Keep a genuine turn if the author
  actually earns one; cut the manufactured drumroll.)*

### B15 — Signposting / meta-announcements — STRONG
"Let's dive in," "Here's what you need to know," "let's break this down,"
sentences opening "Here's why…."

- Before: "Let's dive in. Here's what you need to know."
- After: Start with the thing itself.

### B16 — Generic question-openings / cliché scene-setters — STRONG
"Have you ever wondered…," problem-solution boilerplate, "In today's fast-paced
digital landscape…."

- Before: "In today's fast-paced digital world, have you ever wondered how to
  stay ahead?"
- After: Open on the specific situation: "Most teams still deploy by hand on
  Fridays."

---

## C. Formatting & style patterns

Format is artifact-dependent. Fix these only when they fight the artifact's own
conventions.

### C1 — Em dash overuse — MODERATE → STRONG in density
Spaced or jammed em dashes replacing commas/parens for punchy-sales rhythm.
Note: newer models actively suppress em dashes, and humans use them
legitimately. Density-based and style-config-aware — if the author's own style
guide bans em dashes, that rule wins in their docs.

- Before: "It works — really works — and it's fast — trust me."
- After: "It works, and it's fast." *(One em dash in a paragraph is not slop.)*

### C2 — Boldface spam — STRONG
Mechanical bolding of "key" phrases throughout.

- Before: "This is **important** because **speed** matters for **users**."
- After: Bold nothing, or bold the one thing that truly stands out.

### C3 — Inline-header bullet lists — STRONG
"**Speed:** …", "**Quality:** …" as a reflex structure.

- Before: "**Speed:** It's fast. **Quality:** It's good. **Price:** It's cheap."
- After: Write it as a sentence or two of prose, unless the list carries real
  parallel structure.

### C4 — List-itis — MODERATE
Bulleting content that reads better as prose; unnecessary mini-tables.

- Before: a five-bullet list where each bullet is a full flowing sentence.
- After: a short paragraph. *(Keep lists that are genuinely scannable items.)*

### C5 — Title Case Headings — MODERATE
Strong only where sentence case is the house norm; many style guides use title
case legitimately.

- Before: "How To Get Started With The New Tool"
- After (if sentence case is the norm): "How to get started with the new tool"

### C6 — Emoji as decoration — MODERATE
Emoji on every heading/bullet. Chat and social context makes emoji human, so
judge by artifact.

- Before: "🚀 Features 🔥 / ✨ Benefits ✨"
- After: Drop decorative emoji in a formal doc; keep them in a Discord message.

### C7 — Curly quotes where straight expected — WEAK
Word processors auto-curl; rarely worth acting on. Fix only in code/plaintext
contexts where straight quotes are required.

### C8 — Hyphenated-pair uniformity — WEAK → MODERATE
Perfectly consistent "data-driven," "high-quality." **Caution:** do not "fix"
by deleting hyphens — that introduces grammar errors. The rule is *vary
naturally where variation is correct*, not de-hyphenate.

- Before: every compound modifier hyphenated with mechanical regularity.
- After: keep correct hyphenation; relax only where the open form is equally
  standard.

### C9 — Fragmented headers — STRONG
A heading immediately followed by a one-line restatement of that heading.

- Before: "## Performance\nPerformance is a key focus of this release."
- After: Let the heading do its job; open the section with real content.

### C10 — Thematic breaks / skipped heading levels — MODERATE
`---` before every heading; jumping from H2 to H4. Often a markdown-export
artifact.

- Before: `---` stacked before each heading, inconsistent levels.
- After: Remove decorative rules; keep heading levels sequential.

### C11 — Oxford comma; American spellings — WEAK
**Do not act on these.** Millions of humans use both. Listed only so they are
not mistaken for tells. See `weak-signals.md`.

---

## D. Artifact patterns (mechanical residue — remove unconditionally)

These are near-proof of AI and matter mostly when cleaning pasted AI text.
Remove them without needing corroboration.

### D1 — Chatbot correspondence residue — STRONG
"Great question!", "I hope this helps!", "Would you like me to…", "Certainly!"

- Before: "Great question! Here's a breakdown. I hope this helps!"
- After: Deliver the content; drop the framing.

### D2 — Knowledge-cutoff disclaimers — STRONG
"as of my last update," "while specific details are limited…."

- Before: "As of my last update, the figures may have changed."
- After: State what's known; if unknown, say so plainly or cut.

### D3 — Sycophancy — STRONG
"You're absolutely right!", flattery padding.

- Before: "You're absolutely right to ask — great thinking!"
- After: Delete.

### D4 — Phrasal templates / unfilled placeholders — STRONG
"[Your Name]", "PASTE_URL_HERE", "2025-XX-XX", "[insert detail]."

- Before: "Best regards, [Your Name]"
- After: Fill from the source, or flag the gap to the author — never invent the
  value.

### D5 — Model markup artifacts — STRONG
`:contentReference[oaicite:…]`, `turn0search0`, `[cite: 1]`,
`grok_render_citation_card_json`, stray ```` ```wikitext ```` fences, mixed
Markdown/wikitext.

- Before: "The study found X:contentReference[oaicite:3]{index=3}."
- After: "The study found X." *(Preserve the real citation if one exists;
  strip the machine residue.)*

### D6 — "As an AI language model…" refusal residue — STRONG
- Before: "As an AI language model, I can't have opinions, but…"
- After: Delete.

---

## E. Anti-patterns of the rewrite

Calibration targets that keep de-slopify from overcorrecting. Full treatment in
`weak-signals.md`; summary here so the catalog is self-contained.

- Humans use simple is/has phrases, plain verbs, confident superlatives ("one
  of the best," "was the first"), mild hedges (perhaps, tends to), and even the
  occasional wordy construction. A rewrite scrubbed to perfect efficiency is
  its own tell.
- **Soulless-but-clean is still slop.** Uniform sentence length, zero opinion,
  no first person where it would be natural, no mess. The fix is rhythm
  variation and (where the artifact and author permit) a real stance — not
  decoration, and never a fabricated stance.
