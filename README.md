# Visa sponsorship in UK job adverts (September 2026)

Roughly **1 in 7** job adverts from employers on the UK Home Office register of licensed sponsors ruled out visa sponsorship, or required UK nationality, years of UK residence or security clearance. Where the full advert could be read, it was about **1 in 5**. Fewer than **1 in 100** adverts said sponsorship is available.

This repository holds the aggregate data behind the study published by [SponsorJobs](https://sponsorjobs.co):
**[Roughly 1 in 7 UK visa sponsor job adverts rule out sponsorship](https://sponsorjobs.co/research/visa-sponsorship-adverts-2026)** (full write-up, charts and sources).

## Key figures

| Measure | Adverts | Ruled out | % |
|---|---:|---:|---:|
| All adverts read 24–25 Sep 2026 (unique employer + advert text) | 92,598 | 13,018 | 14.1 |
| Adverts where the full text could be read | 56,568 | 12,240 | 21.6 |
| Full-text adverts live on 23 Sep 2026, duplicates removed | 44,855 | 10,095 | 22.5 |
| Same, without the 10 employers with the most refusals | 38,294 | 5,247 | 13.7 |

- **A few big employers post most of the refusals.** Ten employers account for half of the full-text refusals. Of the 778 employers with 10 or more adverts, 464 ruled sponsorship out in none of them.
- **Early-career roles are hit hardest:** 61% of internship and placement adverts, 32% of entry-level adverts.
- **By type of work:** care (48%) and engineering (40%) are highest; legal (6%), accounting (8%), marketing (8%) and sales (9%) are lowest.
- **Saying yes is rare:** for every advert that offers sponsorship, about 25 rule it out.

## The data

[`data/visa-sponsorship-adverts-2026.csv`](data/visa-sponsorship-adverts-2026.csv): aggregate counts only. No advert text, no personal data.

| Column | Meaning |
|---|---|
| `table` | Which breakdown the row belongs to: `headline`, `reason`, `job_function`, `seniority`, `employer_industry`, `offers_live`, `text_length_check` |
| `group` | The group within that breakdown (for example a job function or seniority level) |
| `adverts` | Number of unique adverts in the group |
| `ruled_out` | Adverts that ruled out sponsorship (see definition below) |
| `ruled_out_pct` | `ruled_out / adverts`, in % |
| `offered` | Adverts that explicitly offer sponsorship (where measured) |
| `offered_pct` | `offered / adverts`, in % |
| `note` | How the row was defined |

## Method

Every advert SponsorJobs collects from an employer on the Home Office sponsor register is read by a language model when it arrives. It checks whether the advert offers sponsorship, might, says nothing, or rules it out. A "rules it out" verdict also needs the matching wording to be present in the text.

- **Ruled out:** says sponsorship isn't available; asks for the right to work without sponsorship; UK nationality; several years of UK residence or a checkable UK history; or security clearance (SC or DV). Routine right-to-work checks, BPSS and DBS checks don't count.
- **Adverts, not jobs:** each employer's advert text is counted once, so reposts and copies across sites aren't double counted.
- **Sources:** public job boards and employer career sites. About a third of adverts arrive as short snippets (around 500 characters) that usually cut off the sponsorship line, which is why the full-advert rate is higher than the overall one.
- **Accuracy:** in a random check of 80 ruled-out adverts, 97.5% were right by these rules (90% if a bare "you must have the right to work in the UK" is not counted as a refusal). A check of 80 adverts that were kept found no clear refusals missed.

## Limits

- These are adverts collected from licensed sponsors, not every job advert in the UK.
- It's a snapshot of late September 2026: adverts live on 23 September plus new ones over the next two days.
- Employers are matched to the register by name; a small number of matches will be wrong.
- Reason categories come from advert wording and are approximate.

## Licence and citation

Data: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). You're welcome to use it with a credit and a link.

> SponsorJobs (2026). *Do UK visa sponsors' job adverts offer sponsorship?* https://sponsorjobs.co/research/visa-sponsorship-adverts-2026

SponsorJobs is an independent UK job board that lists jobs at Home Office-licensed sponsors and reads every advert. It is not affiliated with the Home Office or UK Visas and Immigration, and this is not immigration advice.
