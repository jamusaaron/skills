# Readability Metrics

Compute these metrics with code (a short Python script) rather than estimating. Report each number alongside its interpretation for the stated audience.

## Preprocessing

- Strip headings, code blocks, URLs, and citations before counting.
- Sentence = text ending in `.`, `!`, or `?` (handle abbreviations like "e.g." and "Dr." as best as reasonable; perfect segmentation is not required).
- Word = whitespace-delimited token containing at least one letter or digit.
- Syllable counting heuristic: count vowel groups (`[aeiouy]+`) per word; subtract one for silent trailing `e` (except `-le`); minimum one syllable per word.

## Core metrics

### Flesch Reading Ease (FRE)

```
FRE = 206.835 − 1.015 × (words / sentences) − 84.6 × (syllables / words)
```

| FRE | Reading level |
|---|---|
| 90–100 | 5th grade — very easy |
| 80–90 | 6th grade — easy, conversational |
| 70–80 | 7th grade — fairly easy |
| 60–70 | 8th–9th grade — plain English (target for general audiences) |
| 50–60 | 10th–12th grade — fairly difficult |
| 30–50 | College — difficult |
| 0–30 | Graduate/professional — very difficult |

### Flesch–Kincaid Grade Level (FKGL)

```
FKGL = 0.39 × (words / sentences) + 11.8 × (syllables / words) − 15.59
```

Interpret as the US school grade needed to read the text comfortably. Most professional writing targets 8–12; consumer-facing writing targets 6–8.

### Gunning Fog Index

```
Fog = 0.4 × [(words / sentences) + 100 × (complex words / words)]
```

Complex word = 3+ syllables, excluding proper nouns, compound words, and common suffixed forms (`-es`, `-ed`, `-ing` added to a 2-syllable word). Target under 12 for broad audiences.

## Descriptive statistics

Report these regardless of formulas — they drive the concrete feedback:

- **Average sentence length** (words). Under 14 = brisk; 14–20 = standard; 20–25 = demanding; over 25 = flag for review.
- **Sentence length standard deviation.** Below ~5 suggests monotony; healthy varied prose usually sits at 7+.
- **Longest sentence** — quote it; it is almost always a revision candidate.
- **Lexical density** = unique words / total words (on samples of comparable length). Higher = more information-dense.
- **Passive voice rate** — percentage of sentences containing a `be`-verb + past participle. Over ~20% in general prose deserves a finding; scientific writing tolerates more.
- **Adverb rate** — `-ly` adverbs per 100 words; over ~4 often signals telling instead of showing or weak verb choices.

## Interpretation rules

- **Never score on formulas alone.** A legal contract at FKGL 16 written for lawyers is well-targeted; a children's story at FKGL 10 is not.
- **Short samples are unstable.** Below ~150 words, report the numbers with an explicit low-confidence caveat or omit them.
- **Dialogue and lists distort formulas.** Compute on narrative/expository prose only when the sample mixes modes, and say so.
- **A mismatch is a finding, not a verdict.** If numbers are off-target, locate *which passages* drive them (usually a handful of long sentences or polysyllabic clusters) and quote those in the report.
