# de-slopify — updates log

A running record of sourced revisions. When a new tip, link, or example is
added to this skill, log one line here so the provenance stays traceable and
word rot never quietly rewrites the durable rules.

## Update protocol

1. **Fetch/read** the shared material. Extract candidate patterns or
   counter-examples.
2. **Dedupe** against `references/patterns.md`. The pattern IDs (A1–A11,
   B1–B16, C1–C11, D1–D6, E) are stable — cite them.
   - New pattern → add to `patterns.md` with source URL, date, and a strength
     rating.
   - Refinement of an existing one → amend that entry in place.
3. **Vocabulary** changes go to `references/vocab-eras.md` as a dated era block,
   never merged into the timeless rules.
4. **Log** one line below: date, source link, what changed, affected IDs.
5. **Version** the skill in `SKILL.md` frontmatter if a `version:` field is in
   use (semver: new pattern = minor, wording fix = patch).
6. **Commit** to the canonical repo with a conventional message
   (`de-slopify: add pattern Bxx from <source>`); push per normal approval
   rules.
7. **Quarterly / on request:** re-check the upstream Wikipedia page ("Signs of
   AI writing") for new sections — it is actively maintained and is the source
   of record.

## Source discipline

- Include source URLs and access dates when adding material.
- Paraphrase; do not paste long passages from copyrighted sources.
- Do not add detector-evasion techniques, universal word blacklists, or
  intentional-error tricks — these are out of scope by design.

## Log

| Date | Source | Change | IDs |
|------|--------|--------|-----|
| 2026-07-19 | Initial build from research spec (blader/humanizer, Wikipedia "Signs of AI writing", ETBI, Hunting the Muse) | Created taxonomy, weak-signals, vocab-eras, eval cases | A1–A11, B1–B16, C1–C11, D1–D6, E |
