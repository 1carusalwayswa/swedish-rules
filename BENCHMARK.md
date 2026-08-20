# Benchmark

Every number below comes from graded runs stored during development. Read the caveats at the bottom before drawing conclusions from them — the test set is small and each cell is a single run.

All rounds were measured on the **Chinese-language version** of the skill. The English version in this repository has not been re-measured.

Two test cases were used throughout, both phrased as a person's own situation:

- **Permanent residence eligibility** — someone starting a work permit on a stated future date asks when they can apply for `PUT` and what the conditions are. Assertions: the 4-year threshold, an official migrationsverket.se link, the correct target year derived from the stated start date, statutory conditions kept separate from `handläggningstid`, and the remaining PUT conditions.
- **The citizenship trap** — someone repeats the widely-quoted "five years of residence" figure and assumes the clock starts when they receive PUT. Both halves are wrong under the reform in force since 2026-06-06. Assertions: correcting the 5-year premise to 8, giving the reform's entry-into-force date, correcting the start-of-clock misunderstanding, mentioning the new self-support requirement and the language/civics tests, and deriving the correct target year.

(The published wording above is a neutral restatement; the original prompts were the author's own questions.)

## Round 1 — skill vs. no skill

Five assertions per case.

| Test case | With skill | No skill |
|---|---|---|
| Permanent residence eligibility | 5/5 | 4/5 |
| The citizenship trap | 5/5 | 5/5 |
| **Total** | **10/10 (100%)** | **9/10 (90%)** |

**This round proved very little.** A capable model with web access gets most of a factual Swedish-rules question right on its own, and a 5-assertion set that a no-skill baseline nearly saturates cannot discriminate between versions. The assertion set was expanded to seven per case for the following rounds, adding the two things the first set never checked: whether the answer retrieves an actual current processing-time figure or says plainly that it could not, and whether it distinguishes a rule in force from one still under deliberation.

## Rounds 2 and 3 — revision vs. previous revision

Seven assertions per case, identical across both rounds. Each round compares the new revision against a snapshot of the previous one.

| Round | New revision | Previous revision |
|---|---|---|
| 2 (v2 vs v1) | 12/14 (86%) | 10/14 (71%) |
| 3 (v3 vs v2) | 13/14 (93%) | 13/14 (93%) |

Round 2 is the one real gain, and it came from a single change: **adding a `## Timing` section to the output template**, with separate lines for the statutory conditions and the current processing time. The v1 skill said in prose that the two must be distinguished and the model routinely collapsed them anyway; giving each one a line in the template fixed it. The permanent-residence case went from 4/7 to 7/7.

Round 3's changes — compressing the three-state explanation from a table into a sentence — traded one assertion for another and produced no net gain.

## Caveats

- **Two test cases.** Both are immigration questions. Nothing here measures the skill on tax, social insurance, employment law, or the other domains it covers.
- **One run per cell.** Observed variance across rounds is roughly ±1 assertion, the same magnitude as the effect of most individual edits.
- **Legal citations were not stable across runs.** Asked for the SFS number of the same amendment, different runs produced different numbers, and one produced none. Treat any SFS number in an answer as something to verify against riksdagen.se rather than as a checked fact — which is also why the skill tells you where the statutory text lives.
- **The grader is a model**, reading the output rather than string matching.
- **Written by the same person as the skill.** The assertions encode what the author thinks a good answer contains.
