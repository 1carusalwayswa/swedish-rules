# Swedish Rules

An agent skill for checking official Swedish rules — immigration and residence permits, tax and `folkbokföring`, social insurance, employment law, credential recognition, driving licences, healthcare.

It answers from official Swedish-language sources, states **whether the rule is actually in force**, separates **statutory conditions from current processing times**, and applies the result to **your specific permit and timeline**.

## Why

Swedish immigration and citizenship law has been amended repeatedly in recent years, and search results happily mix the 2018 and the 2026 version of a rule with identical authority. An agent answering from memory will often hand you the previous generation of the rule, phrased with complete confidence.

Two failure modes cost real money and real time:

- **Planning against a rule that is being replaced.** The citizenship reform that took effect on 2026-06-06 spent all of 2025 as a government inquiry. Anyone building a multi-year plan in 2025 needed to know that — an answer describing only what was in force at the time was misleading precisely because it was accurate.
- **Confusing the statute with the queue.** How many years you need is in the law. How long the authority takes to process the case is not — it lives only in the current statistics, and it is the number your actual calendar runs on.

## What it does

| | |
|---|---|
| Searches in Swedish | Translated pages on official sites lag the Swedish ones after an amendment |
| Official sources only | Forums and consultants locate the provision; the conclusion comes from the authority's own page |
| Marks the rule's state | `gällande` / passed but not yet in force / under deliberation (`SOU`, `remiss`, `lagrådsremiss`) |
| Cites amendments properly | `SFS` number plus `ikraftträdande` date, statutory text from riksdagen.se |
| Splits statute from practice | Statutory conditions and current processing times, both given, both labelled |
| Applies it to you | Third-country nationals and EU citizens differ under nearly every immigration rule |
| Admits gaps | What could not be established, and which authority to call about it |

Output is a short answer, the basis with source and rule state, the timing, what it means for you specifically, and what could not be established.

## Installation

No build step and no dependencies — the skill is plain Markdown.

**Claude Code:**

```bash
git clone https://github.com/1carusalwayswa/swedish-rules.git ~/.claude/skills/swedish-rules
```

**Codex / other harnesses:** clone anywhere, then symlink into the directory your harness reads skills from.

```bash
git clone https://github.com/1carusalwayswa/swedish-rules.git ~/.codex/skills/swedish-rules
ln -s ~/.codex/skills/swedish-rules ~/.claude/skills/swedish-rules
```

Verify:

```bash
ls ~/.claude/skills/swedish-rules/SKILL.md
```

The directory name must be `swedish-rules` so it matches the `name` field in the frontmatter.

## Usage

The skill triggers on its own when you ask about a Swedish rule. Nothing to invoke by hand.

```
How many years do I need before I can apply for permanent residence?
Someone told me the citizenship requirement is five years — is that still true?
Can I change employers on my current work permit?
How long is Migrationsverket taking on this type of case right now?
```

It will ask for your nationality, permit type, and timeline if it does not already have them — the general-case answer is wrong often enough that answering without them is not a check at all.

## Development

The skill was developed against a small evaluation set of real questions, comparing each revision against the previous one. Across three rounds the pass rate on those assertions went from 71% to 93%, measured on the Chinese-language version; this English version has not been re-measured. There is no measurement against a no-skill baseline.

## Structure

```
swedish-rules/
└── SKILL.md
```

## License

MIT
