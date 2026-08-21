---
name: personality-analysis
description: Infer personality indicators from a person's writing using established frameworks — Big Five (OCEAN), MBTI-style dichotomies, DISC, and Enneagram — grounded in observable linguistic markers. Use this skill whenever asked to analyze someone's personality, character, temperament, communication style, or psychological profile from a writing sample, alone or alongside a writing-quality evaluation (see the companion writing-evaluation skill). Produces evidence-based, appropriately hedged profiles, never clinical diagnoses.
---

# Personality Analysis from Writing

Infer what a writing sample suggests about its author's personality — rigorously, with quoted linguistic evidence for every inference, calibrated confidence, and explicit limits.

## When to use this skill

- "What does my writing say about my personality?"
- "Analyze the personality / character / temperament of whoever wrote this"
- "What's this person's MBTI / Big Five / DISC / Enneagram type based on their writing?"
- "Describe this writer's communication style"

## Critical boundaries — read first

- **This is not psychological assessment.** Text-based inference is informal and probabilistic. Never present results as diagnosis, clinical evaluation, or a substitute for validated instruments. Never infer mental-health conditions.
- **Refuse harmful uses.** Do not produce profiles intended to manipulate, harass, discredit, or make consequential decisions about a person (hiring, lending, legal). Profiles of non-consenting third parties should be declined or limited to communication-style observations.
- **State confidence honestly.** A single short sample supports weak inferences at best. Formal or professionally edited writing masks personality. Say so.
- Load `references/ethics-and-limitations.md` before every analysis and apply it.

## How to use this skill

### Step 1: Intake and suitability check

1. Obtain the writing sample(s). More text and more contexts = better inference. Ideal: 500+ words across 2+ registers (e.g., an email and an essay).
2. Determine: Is the author the requester (self-analysis, fine), a consenting subject (fine), or a third party (limit scope per the ethics reference)?
3. Note masking factors: heavy editing, formal genre constraints, collaborative authorship, non-native language, AI assistance. These cap confidence.

### Step 2: Extract linguistic markers

Run `agents/marker-extractor.md` (or follow it as a checklist). It converts the raw text into the evidence base every framework profiler uses: pronoun patterns, emotion vocabulary, cognitive-process words, certainty language, social orientation, energy and pace markers. Ground this in `references/linguistic-markers.md`, which maps marker families to trait research.

### Step 3: Profile through each requested framework

Run the framework agents the user asked for; run Big Five plus one intuitive framework (MBTI-style or Enneagram) when they didn't specify. Each agent works only from the extracted markers plus its own targeted re-read of the text.

| Framework | What it yields | Agent |
|---|---|---|
| Big Five (OCEAN) | The scientifically grounded backbone: five trait dimensions with facets | `agents/big-five-profiler.md` |
| MBTI-style dichotomies | Four accessible preference axes (E/I, S/N, T/F, J/P) | `agents/mbti-profiler.md` |
| DISC | Workplace communication style (Dominance, Influence, Steadiness, Conscientiousness) | `agents/disc-profiler.md` |
| Enneagram | Motivational hypothesis: core desire/fear patterns | `agents/enneagram-profiler.md` |

Framework details, scoring conventions, and validity notes are in `references/frameworks.md`. Every trait claim needs quoted evidence and a confidence level.

### Step 4: Synthesize

Run `agents/profile-synthesizer.md` to merge framework outputs into one profile:

1. **Portrait** — a few paragraphs describing the person the evidence supports, in plain language, hedged proportionally to the evidence.
2. **Framework results** — per-framework summaries with confidence levels; convergences highlighted (traits multiple frameworks agree on are the trustworthy ones), divergences explained.
3. **Communication style guide** — the practical payoff: how this person likely prefers to give/receive information, decide, and collaborate.
4. **Evidence appendix** — the marker-to-inference chain, quoted.
5. **Limitations box** — sample size, masking factors, what this analysis cannot claim.

## Guidelines

- **Markers, then traits — never the reverse.** Extract evidence before forming impressions, or confirmation bias will write the profile for you.
- **Convergence is the signal.** An inference supported by multiple independent marker families (and multiple frameworks) deserves confidence; a single-marker inference stays a hypothesis.
- **Content ≠ trait.** Someone writing about anxiety before an exam is situationally anxious, not necessarily high-neuroticism. Distinguish state from trait; only stable patterns across the sample count.
- **Genre is a confound.** A cover letter is performed conscientiousness. Weight markers the genre doesn't demand (function words, sentence rhythm, hedging habits) over markers it does (achievement vocabulary in a résumé).
- **Positive-trait bias check.** If your draft profile contains only flattering traits, you are describing the genre, not the person. Revisit the evidence.

## Keywords

personality analysis, personality type, Big Five, OCEAN, MBTI, 16 personalities, DISC, Enneagram, psycholinguistics, writing style analysis, communication style, character assessment, temperament
