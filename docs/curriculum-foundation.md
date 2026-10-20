# Chinese 500 — Curriculum foundation (draft v0.1)

## Status / scope
- Working branch for curriculum groundwork. Do not merge to `main` until reviewed.
- 30 examples from Section 01–03 are **prototypes**, not finalized publication content.
- Items in `targets.seed.csv` were **reverse-extracted from prototypes**, so its coverage rate is **not** coverage of the intended 500-sentence curriculum.
- Difficulty, targets and Japanese meanings are editorial hypotheses; not authoritative HSK levels or frequency measures.
- No native Chinese language review, corpus-frequency verification, learning-effect validation or license clearance has been completed.

## Product hypothesis
For Japanese-speaking intermediate Chinese learners (approximate HSK4–5 range): use a dense, finite set of **500 Chinese sentences = 50 loosely connected minidramas × 10 sentences**, with optional people/place names as memory hooks. Each sentence must still make sense when encountered alone. Optimize for active spoken recall, natural collocations, listening and reuse, not for brute-force compression.

## Item categories
- `vocab`: lexical unit
- `chunk`: collocation or fixed expression
- `grammar`: grammatical pattern with a particular sense
- `discourse`: discourse connector, pragmatic marker, conversational expression

## Planning & quality gates
1. Build an independent target curriculum from HSK syllabus, natural language examples, frequency evidence and Japanese learner difficulty; record sources and usage senses. **Never** equate the reverse-extracted seed with that curriculum.
2. Assign stable item IDs. Track meaning/sense, planned number of exposures, prerequisite status, priority and provenance.
3. Plan which items debut in each section, what recurs, and why; deliberate recycling is desired.
4. Write a one-paragraph minidrama arc and character/place registry per 10-sentence Section.
5. Generate multiple candidate sentences and select on conversational naturalness, solo intelligibility, target coverage, memorability and scene continuity.
6. Check referential integrity automatically with `tools/coverage_check.py`; separately collect human native reviews of word choice, register, pronunciation, cultural fit and translations.
7. A checker must **not** infer mastery/valid usage from string matching. A reviewer must decide whether a sentence genuinely exemplifies the target sense.
8. Do not automatically remove repeats; classify as planned review, story continuity, unintended duplication or unresolved.

## Prototype data
- `data/sections.seed.csv`: three arcs and name/place anchors.
- `data/sentences.seed.csv`: the existing 30 original trial sentences.
- `data/targets.seed.csv`: candidate learning targets identified from those sentences.
- `data/appearances.seed.csv`: links targets to example sentence IDs. First occurrence is `primary`; subsequent occurrences are `review`. This is an initial mechanical assignment, not yet an approved teaching plan.

Run `python tools/coverage_check.py` to inspect integrity and seed-only coverage. See `tests/test_coverage_check.py` for basic tests.

## Decisions
- No user decision is needed for cataloguing, identifying gaps, and designing the first pilot.
- User decisions should be requested only once concrete side-by-side samples expose a genuine tradeoff (difficulty, sentence length and audio review experience).
- Final curriculum counts, exact HSK standard/version and publication decisions remain provisional; do not guess them.

## Immediate next work
1. Independently source/curate candidate vocabulary+grammar (not only this seed).
2. Review Section 01 targets for wrong senses/grammar patterns and fix prototype mappings.
3. Add source metadata, planned repetitions, prerequisite ordering and objective quality scoring.
4. Produce the first native-reviewed pilot and structured listening/shadowing evaluation.
