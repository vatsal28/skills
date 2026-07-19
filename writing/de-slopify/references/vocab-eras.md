# de-slopify  -  rotating AI vocabulary by model era

AI vocabulary is not a fixed blacklist. It drifts as models change, and today's
tell becomes tomorrow's ordinary word. Keep this list **separate** from the
timeless rules in `patterns.md` so word rot never contaminates the durable
guidance.

**How to use this file**

- These are *cluster* signals. A single word here is not slop (see B1 and
  `weak-signals.md`). Flag when several co-occur, or when a word is used
  figuratively/inflationarily against its plain meaning.
- Any word here is fine in its genuine domain: "robust" in an engineering doc,
  "delve" quoting Beowulf scholarship, "landscape" describing actual terrain.
- Newer eras add words but rarely retire the old ones from human suspicion  - 
  weight recent-era clusters more heavily, but keep the older lists.
- When Vatsal shares new era observations, append a dated block below and log it
  in `../UPDATES.md`. Do not rewrite history; add.

---

## Era 1  -  2023 to mid-2024 (GPT-4 generation)

delve, tapestry, testament, boasts, intricate, pivotal, realm, showcase,
underscore, foster, nuanced, multifaceted, meticulous, myriad, bustling,
crucial, vibrant, seamless, unwavering, treasure trove.

Signature figurative tics: "rich tapestry of," "stands as a testament to,"
"delve into," "navigate the complexities of."

## Era 2  -  mid-2024 to mid-2025 (GPT-4o generation)

fostering, showcasing, align with, vibrant, leverage, streamline, empower,
elevate, resonate, holistic, synergy, robust, dynamic, curated, intentional,
game-changer, spearhead.

Signature tics: "align with your goals," "showcasing the importance of,"
"foster a sense of community," "in today's fast-paced world."

## Era 3  -  mid-2025 onward (GPT-5 generation and later)

emphasizing, enhance, highlighting, showcasing, notability-speak (framing that
justifies why a subject "matters" or is "recognized"), "reflects a broader,"
"underscores the significance of," "plays a key role in."

Behavioral shift: some newer models (e.g., GPT-5.1) **actively suppress em
dashes**. Consequence: em-dash density (C1) is a weaker AI signal for text from
these models, and *absence* of em dashes is not evidence of human authorship.
Weight the content-level tells (A-class, B13, B15, B16) more heavily for
recent-era text.

---

## Standing caveats

- **Word lists rot.** Re-check the upstream Wikipedia page ("Signs of AI
  writing") periodically; it is actively maintained and tracks new eras. Add
  new blocks here rather than editing rules elsewhere.
- **Human drift.** As these words enter ordinary speech and writing, their
  signal value falls. When in doubt, treat a word here as WEAK and rely on
  clustering plus content-level tells.
- **Never a hard ban.** Nothing in this file authorizes find-and-replace
  deletion of a word. The decision is always contextual.
