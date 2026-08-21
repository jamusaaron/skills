---
name: writing-evaluation
description: Comprehensive evaluation of a person's writing across clarity, structure, grammar and mechanics, style and voice, and readability. Use this skill whenever asked to assess, critique, grade, score, or give feedback on someone's writing — essays, articles, emails, reports, cover letters, fiction, or any prose sample. Produces rubric-based scores, evidence-backed findings, and actionable revision guidance.
---

# Writing Evaluation

Evaluate a writing sample the way a skilled editor and writing instructor would: systematically, with evidence for every judgment, and with feedback the writer can actually act on.

## When to use this skill

- "Evaluate / critique / grade / review my writing"
- "What are the strengths and weaknesses of this essay?"
- "Score this piece" or "How readable is this?"
- "Give me editorial feedback on this draft"
- Any request to assess writing quality, alone or alongside personality analysis (see the companion `personality-analysis` skill)

## How to use this skill

### Step 1: Intake

1. Obtain the writing sample. If none is provided, ask for it (or for a file path).
2. Establish context — it changes every judgment that follows:
   - **Genre and purpose** (persuasive essay, technical report, fiction, business email, etc.)
   - **Intended audience** (experts, general readers, a hiring manager, children)
   - **The writer's goal** for the evaluation (a grade, revision help, publication readiness)
3. If context is not stated and cannot be asked for, infer it from the text and state your assumption explicitly in the report.

### Step 2: Evaluate each dimension

Assess the five core dimensions. For each, load the rubric in `references/scoring-rubric.md` and record a 1–5 score plus at least two pieces of quoted evidence from the text.

| Dimension | What it covers | Agent (for delegated runs) |
|---|---|---|
| Clarity & concision | Precision of meaning, wordiness, ambiguity, jargon | `agents/clarity-evaluator.md` |
| Structure & organization | Thesis/through-line, paragraphing, transitions, logical flow | `agents/structure-evaluator.md` |
| Grammar & mechanics | Grammar, usage, punctuation, spelling, formatting consistency | `agents/grammar-mechanics-evaluator.md` |
| Style & voice | Tone, register, diction, sentence variety, distinctiveness | `agents/style-voice-evaluator.md` |
| Readability & audience fit | Quantitative readability, sentence/word statistics, audience match | `agents/readability-analyst.md` |

When subagents or parallel task execution are available, dispatch one agent per dimension using the agent prompt files in `agents/`, then merge results with `agents/synthesis-reporter.md`. When running single-threaded, work through the dimensions in the order above yourself, following each agent file as a checklist.

For the readability dimension, compute the metrics defined in `references/readability-metrics.md` (Flesch Reading Ease, Flesch–Kincaid Grade Level, average sentence length, lexical density). Prefer running the computation as code over estimating.

### Step 3: Apply genre expectations

Consult `references/genre-guides.md` and adjust interpretation — sentence fragments are a defect in a legal memo and a technique in fiction. Never penalize a deliberate, effective genre convention.

### Step 4: Synthesize the report

Follow `agents/synthesis-reporter.md` to produce the final report. It must contain:

1. **Summary verdict** — two or three sentences: overall quality, the single biggest strength, the single highest-leverage improvement.
2. **Scorecard** — the five dimension scores (1–5) and a weighted overall score.
3. **Findings per dimension** — each finding stated as *observation → quoted evidence → why it matters → concrete fix*.
4. **Top 3 revision priorities** — ordered by impact, each with a before/after rewrite of one real sentence from the sample.
5. **What to keep** — genuine strengths, quoted, so the writer doesn't revise them away.

## Guidelines

- **Evidence or it didn't happen.** Every criticism and every compliment must quote the text. No generic feedback ("could be clearer") without a specific example and fix.
- **Calibrate honestly.** Use the full 1–5 range. A competent-but-unremarkable sample is a 3, not a 4. Do not inflate to be kind; do not nitpick to seem rigorous.
- **Respect the writer's voice.** Recommend changes that make the writing more itself, not more like yours. Flag voice-flattening edits as optional.
- **Separate defects from preferences.** Label each finding as *error* (objectively wrong), *weakness* (hurts effectiveness), or *preference* (stylistic choice you'd make differently).
- **Short samples get hedged conclusions.** Under ~150 words, say that scores are low-confidence and skip the readability statistics, which are unstable on short texts.

## Keywords

writing evaluation, writing feedback, critique, essay grading, editorial review, proofreading assessment, readability, writing quality, rubric, revision
