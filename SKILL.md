---
name: swedish-rules
description: Verify official Swedish rules — immigration and residence (uppehållstillstånd, work permits, PUT, citizenship), tax and civil registration (Skatteverket, folkbokföring), social insurance (Försäkringskassan, föräldrapenning, a-kassa), employment law and working conditions, credential recognition, driving licences, and healthcare. Use this skill whenever the user asks "what are the rules in Sweden for X", "can I do X on my current permit", "how long does it take", "what documents do I need", "do I meet this requirement", or asks you to check something they heard. Getting a rule wrong has visa or tax consequences, so run the check against official sources even when the question looks simple — remembered Swedish rules are frequently the previous version, since immigration and citizenship law have been amended repeatedly in recent years.
---

# Verifying Swedish rules

Getting a rule wrong costs the user a visa or a tax outcome: either they build a plan that cannot be executed, or they miss the window to apply. Search results mix the 2018 and the 2026 generations of a rule, worded with identical authority, so the entire value of the check lies in **establishing which one is currently `gällande` (in force), and what it means for this particular person**.

## Search in Swedish

The English and other translated pages on official sites lag behind the Swedish ones, sometimes by months after an amendment. **Search in Swedish terms and treat the Swedish page as authoritative**; use the English page only to confirm you have read the term correctly. Where the two disagree, the Swedish page is the correct one.

## Official sources

Conclusions rest on official sites only. These are the ones easily missed — go straight there when the question falls in their domain:

| Domain | Site |
|---|---|
| Working environment and labour law | av.se |
| Unemployment insurance, a-kassa | iaf.se and the individual a-kassa sites |
| Recognition of foreign qualifications | uhr.se |
| Pensions | pensionsmyndigheten.se |
| Company registration | bolagsverket.se |
| Driving licences and vehicles | transportstyrelsen.se |
| Healthcare | 1177.se |

Forums, immigration consultants, news, and Reddit are for **locating** the official provision — they tell you which statute to look up and which Swedish term to search. Once located, go back to the official page for the conclusion; the second-hand account itself never enters the answer.

## Three things that always get stated

**Which state the rule is in.** Saying only "the current rule is X" leads the user to plan years ahead against a rule that is being replaced. Mark every rule as either `gällande` (the `SFS` is published, the `ikraftträdande` date has passed, this is what applies now), passed but not yet in force (the `ikraftträdande` date is in the future, so any plan crossing that date runs on the new rule), or under deliberation (`SOU` / `remiss` / `lagrådsremiss` — worth watching, not settled). When citing an amendment, give the SFS number and the `ikraftträdande` date, and take the statutory text from riksdagen.se. The citizenship reform of 2026-06-06 was still in the third state throughout 2025 — the people who flagged it as such got their multi-year plans right.

**Statute vs practice.** The statutory conditions and Migrationsverket's actual processing times are different things; give both, labelled. Processing times are not in the statute — they exist only on Migrationsverket's current statistics pages, broken down by case type. Those page paths have changed before, so search the site for the current statistics rather than guessing a URL. The user plans their timeline on the practical number and judges their eligibility on the statutory one.

**Who this person is.** The page you found describes the general case, and third-country nationals and EU citizens are treated differently under nearly every immigration rule, so a generic answer applied to a specific person is often wrong. Run the conclusion through their nationality, permit type, and visa timeline. If you do not already have those, ask before answering — answering for the general case is the same as not having checked.

## Output

```
## Answer
[the thing they actually asked, in one or two sentences]

## Basis
- [rule] — [official page link or SFS number], `gällande` since YYYY-MM-DD / passed, in force from YYYY-MM-DD / under deliberation (SOU number)

## Timing
- Statutory conditions: [the years and conditions required to qualify]
- Current processing time: [the figure from Migrationsverket's statistics page, with the case type and the date you looked it up]

## What it means for you
[given their permit type and timeline, what this rule produces for them, and what they need to do by when]

## Not established
[anything the official sources do not cover or state ambiguously, saying which of the two it is]
```

When the question has nothing to do with waiting times, write "not applicable" under `## Timing` rather than inventing a number to fill it.

Anything the official sources do not answer belongs under "Not established", along with which authority to phone or which form to use to ask. An authoritative-looking guess is worse than saying it could not be established — the user will take it into a visa decision.
