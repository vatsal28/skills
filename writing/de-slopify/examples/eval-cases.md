# de-slopify — evaluation cases

Seven cases covering the main artifact types and the two hardest failure modes
(inventing specifics, and over-editing human text). Each case has an input,
expected-behavior acceptance criteria, and a reference rewrite.

The reference rewrites are illustrations, not the only acceptable answers. What
matters is that a rewrite satisfies the acceptance criteria: no invented facts,
preserved meaning, voice and register held, and format that follows the
artifact.

---

## Case 1 — LinkedIn post (social slop)

**Artifact:** first-person LinkedIn post. Short lines are fine here.

**Input**

> But here's the thing: shipping fast isn't just a tactic. It's a mindset.
>
> 🚀 We rebuilt our onboarding in 3 weeks.
> 🔥 We cut signup time in half.
> ✨ We did it with a team of 4.
>
> No fluff. No filler. No excuses. Just results.
>
> The result? Our best quarter ever. And honestly? It changed how I think about
> everything.

**Expected behavior**

- Remove formula-manufactured sass: "But here's the thing:" (B14), "The
  result?" (B14), "And honestly?" (B14).
- Remove negative parallelism (B3) and the tailing-negation stack (B4).
- Keep it punchy and first-person — format follows the artifact; short lines
  stay.
- Keep every real number (3 weeks, half, team of 4, "best quarter"). No
  invented anecdote or metric.
- Decorative emoji (C6) are borderline on social; thinning them is fine, wiping
  them is not required.

**Reference rewrite**

> We rebuilt our onboarding in 3 weeks, with a team of 4. Signup time dropped by
> half.
>
> It turned into our best quarter yet — and it changed how I think about
> shipping. Fast isn't a hack you bolt on. It's how the team works day to day.

*(Note: one em dash kept; the author's LinkedIn voice tolerates it. If Vatsal's
no-em-dash rule applies to his own posts, swap it for a period.)*

---

## Case 2 — Technical README section

**Artifact:** README. Register stays technical; structural bullets stay.

**Input**

> ## Getting Started
>
> Let's dive in! This library serves as a powerful foundation that seamlessly
> handles configuration for you.
>
> - **Speed:** It's incredibly fast.
> - **Flexibility:** It offers a wide range of options.
> - **Simplicity:** No config file needed.

**Expected behavior**

- Cut signposting "Let's dive in!" (B15) and fragmented-header energy.
- Restore copulas: "serves as" → "is"; "offers" → "has" (B2).
- Drop "seamlessly"/"powerful" brochure adjectives (A3).
- Inline-header bullets (C3): convert to prose *if* they don't carry real
  parallel structure; here they're thin, so prose reads better — but keeping a
  cleaned list is also acceptable since READMEs use lists legitimately.
- No personality injection. No emoji added.

**Reference rewrite**

> ## Getting Started
>
> This library handles configuration for you: it's fast, it has a wide range of
> options, and it needs no config file.

---

## Case 3 — Neutral bio / wiki-style paragraph

**Artifact:** neutral reference prose. No stance, no first person.

**Input**

> Jane Okoro stands as a pivotal figure in modern cartography, whose work
> serves as a testament to the field's enduring spirit. Experts note her
> influence spans everything from mapmaking to data science to education.

**Expected behavior**

- A1 significance inflation and A11 regression-to-mean: replace with the buried
  specific *only if the input supplies it*. Here it does not, so cut the
  inflation rather than invent a career.
- B2 copula avoidance ("stands as," "serves as") → is.
- A4 vague attribution ("experts note") → cut, since no source is named.
- B7 false range ("everything from mapmaking to data science to education") →
  plain list.
- Result is shorter and plainer, not embellished.

**Reference rewrite**

> Jane Okoro is a cartographer whose work spans mapmaking, data science, and
> education.

*(If the source elsewhere states what made her influential, name that instead
of cutting. Never supply it from outside.)*

---

## Case 4 — Trap case: sparse input (must not invent)

**Artifact:** short blog intro. Almost no concrete facts in the source.

**Input**

> This groundbreaking project represents a remarkable achievement that
> showcases the incredible power of innovation. It stands as a shining example
> of what's possible when passion meets purpose, delivering transformative
> results that truly matter.

**Expected behavior**

- This is the counter to the humanizer worked-example flaw. There are **no
  specifics in the source** — so the skill must NOT manufacture studies, names,
  numbers, or "concrete details" to fake specificity.
- Strip inflation (A1, A3, A7, A11) and copula avoidance (B2). What remains is
  honestly thin.
- Correct output is **shorter and plainer**, and should flag that the input
  carries no substance to preserve. Do not pad.

**Reference rewrite**

> This project shows what a small, motivated team can build.

*(Plus a note to the author: "The draft had no concrete facts to keep — it
needs real details (what was built, results, for whom) to say more. I won't
invent them.")*

---

## Case 5 — Trap case: competent human formal text

**Artifact:** formal paragraph, already human-written, Oxford comma, one
"Additionally."

**Input**

> The committee reviewed three proposals and approved two. Additionally, it
> deferred the third pending a cost analysis, which the finance office will
> deliver in April. The decision was recorded in the minutes and circulated to
> all members.

**Expected behavior**

- This is clean human prose. The only "signals" are WEAK: one "Additionally"
  (B11 isolated = weak), an Oxford comma (C11, ignore), formal register (not a
  tell).
- Correct output: minimal or **no** changes, with a one-line note that the text
  doesn't need de-slopping. Tests false-positive discipline.
- At most, "Additionally," could be trimmed — but leaving it is equally valid.

**Reference rewrite**

> No change needed. This reads as competent human writing. The only flaggable
> item is a single "Additionally," which is a weak signal on its own and fine to
> keep. (Optional: drop it so the sentence starts with "It deferred the
> third…".)

---

## Case 6 — Voice-calibration case (same slop, two authors)

**Artifact:** same first-person slop paragraph, two supplied voice samples.

**Input (draft)**

> I recently delved into a new productivity system, and honestly? It's not just
> a tool — it's a game-changer. Here's why: it seamlessly streamlines my day
> and empowers me to focus on what truly matters.

**Sample A — terse engineer:** short declaratives, no adjectives, semicolons,
dry.
**Sample B — discursive essayist:** long clauses, parenthetical asides, wry.

**Expected behavior**

- Remove B1 ("delved," "game-changer," "seamlessly," "streamlines,"
  "empowers"), B3 ("not just… it's…"), B14 ("honestly?"), B15 ("Here's why:").
- Two visibly **different** rewrites, each drawn from its sample's rhythm and
  lexicon — proving no single house voice is imposed.
- Neither invents new facts about the system.

**Reference rewrite — A (terse engineer)**

> I switched productivity systems last week. It cuts the daily setup; I spend
> more time on actual work.

**Reference rewrite — B (discursive essayist)**

> I picked up a new productivity system recently — nothing revolutionary,
> whatever the marketing says — but it has quietly taken the fiddly parts of my
> morning off my plate, which leaves more of the day for the work I actually
> came to do.

---

## Case 7 — Chat-residue cleanup

**Artifact:** pasted ChatGPT answer to be cleaned before use.

**Input**

> Great question! You're absolutely right to ask about this. As an AI language
> model, I can tell you that the deadline is in Q3. As of my last update, the
> figures may have shifted:contentReference[oaicite:3]{index=3}. I hope this
> helps! Would you like me to expand on any point?

**Expected behavior**

- Remove all D-class artifacts unconditionally: D1 ("Great question!", "I hope
  this helps!", "Would you like me to…"), D3 ("You're absolutely right"), D6
  ("As an AI language model"), D2 ("As of my last update"), D5
  (`:contentReference[oaicite:3]`), plus curly-quote soup where straight is
  expected (C7, in a plaintext/code context).
- Keep the one real fact: the Q3 deadline.
- No new content; no personality.

**Reference rewrite**

> The deadline is in Q3. The figures may have shifted since; confirm before
> relying on them.
