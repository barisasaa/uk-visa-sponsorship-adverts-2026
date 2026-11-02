# Visa sponsorship in UK job adverts (2026)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23886878.svg)](https://doi.org/10.5281/zenodo.23886878)

Roughly **1 in 6** job adverts from employers we match to the UK Home Office register of licensed sponsors ruled out visa sponsorship, or required UK nationality, years of UK residence, security clearance or an existing right to work (November 2026 edition). Where the full advert could be read, it was about **1 in 5**. On the employers already covered in the September 2026 edition, the rate didn't change. Fewer than **1 in 100** adverts said sponsorship is available.

This repository holds the aggregate data behind the study published by [SponsorJobs](https://sponsorjobs.co):
**[Roughly 1 in 6 UK visa sponsor job adverts rule out sponsorship](https://sponsorjobs.co/research/visa-sponsorship-adverts-2026)** (full write-up, charts and sources).

## Editions

| Edition | Adverts read | Ruled out | Full adverts ruled out | File |
|---|---:|---:|---:|---|
| **November 2026** (3 Oct – 1 Nov 2026) | 202,073 | 16.1% | 19.1% | [`data/visa-sponsorship-adverts-2026-11.csv`](data/visa-sponsorship-adverts-2026-11.csv) |
| September 2026 (live 23 Sep + 2 days) | 92,598 | 14.1% | 21.6% | [`data/visa-sponsorship-adverts-2026.csv`](data/visa-sponsorship-adverts-2026.csv) |

Each edition is tagged (`2026-09`, `2026-11`). Earlier files are never overwritten. See [CHANGELOG.md](CHANGELOG.md).

Also on [Zenodo](https://doi.org/10.5281/zenodo.23886878) (DOI 10.5281/zenodo.23886878), [Hugging Face](https://huggingface.co/datasets/sponsorjobs/uk-visa-sponsorship-adverts-2026) and [Kaggle](https://www.kaggle.com/datasets/sponsorjobsco/visa-sponsorship-in-uk-job-adverts-2026).

## Key figures, November 2026

| Measure | Adverts | Ruled out | % |
|---|---:|---:|---:|
| All adverts read 3 Oct – 1 Nov 2026 (unique employer + advert text) | 202,073 | 32,465 | 16.1 |
| Adverts where the full text could be read | 163,891 | 31,345 | 19.1 |
| Full text, employers and sources already covered in September | 53,014 | 12,423 | 23.4 |
| Full text, employers and sources added since September | 110,877 | 18,922 | 17.1 |
| Full text, without the 10 employers with the most refusals | 153,372 | 22,962 | 15.0 |

- **Like for like, nothing changed.** On the employers covered in both editions, 23% of full adverts ruled sponsorship out, against about 22% in September. The lower overall full-advert figure comes from wider coverage: the employers added since September say no less often.
- **Refusals are more spread out than September suggested.** The 10 employers with the most refusals account for about a quarter of them (September: about half). Of the 2,105 employers with 10 or more adverts, 1,141 ruled sponsorship out in none.
- **Early-career roles are hit hardest:** 48% of internship and placement adverts, 24% of entry-level adverts, 10% at director level.
- **By type of work:** security (44%) and care (41%) are highest, then engineering (25%); legal (7%), healthcare (8%), sales (8%) and accounting (9%) are lowest.
- **Saying yes is still rare:** 0.9% of live adverts offer sponsorship (September 0.5%), from 102 employers (September 45). For every advert that offers it, about 40 rule it out.

## The data

Each CSV holds aggregate counts only. No advert text, no personal data.

| Column | Meaning |
|---|---|
| `table` | Which breakdown the row belongs to: `headline`, `reason`, `job_function`, `seniority`, `employer_industry`, `offers_live`, `text_length_check`, and from November `accuracy_check` |
| `group` | The group within that breakdown (for example a job function or seniority level) |
| `adverts` | Number of unique adverts in the group |
| `ruled_out` | Adverts that ruled out sponsorship (see definition below) |
| `ruled_out_pct` | `ruled_out / adverts`, in % |
| `offered` | Adverts that explicitly offer sponsorship (where measured) |
| `offered_pct` | `offered / adverts`, in % |
| `note` | How the row was defined |

## Method

Every advert SponsorJobs collects from an employer on the Home Office sponsor register is read by a language model when it arrives. It checks whether the advert offers sponsorship, might, says nothing, or rules it out. A "rules it out" verdict also needs the matching wording to be present in the text.

- **Ruled out:** says sponsorship isn't available; asks that you already have the right to work in the UK; UK nationality; several years of UK residence or a checkable UK history; or security clearance (SC or DV). Routine right-to-work checks, BPSS and DBS checks don't count. Same definition in both editions.
- **Adverts, not jobs:** each employer's advert text is counted once, so reposts and copies across sites aren't double counted.
- **Frame:** September is a snapshot of the adverts live on 23 September 2026 plus new ones over the next two days. November counts every advert read from 3 October to 1 November 2026, including the ones SponsorJobs doesn't list.
- **Sources:** public job boards and employer career sites. About 1 in 7 adverts (September: 1 in 3) arrive as short snippets (around 500 characters) that usually cut off the sponsorship line, which is why the full-advert rate is higher than the overall one.
- **Accuracy (November):** in a random check of 80 ruled-out adverts, 91% were right by these rules (69% if a bare "you must have the right to work in the UK" or "this role may require security clearance" is not counted as a refusal). A check of 80 adverts that were kept found no clear refusals missed. September: 97.5% (90%).

## Limits

- These are adverts collected from employers on the sponsor register, not every job advert in the UK.
- Coverage more than doubled between editions, so compare the like-for-like rows, not the totals.
- Employers are matched to the register by name; a small number of matches will be wrong.
- Reason categories come from advert wording and are approximate.

## Licence and citation

Data: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). You're welcome to use it with a credit and a link.

> SponsorJobs (2026). *Do UK visa sponsors' job adverts offer sponsorship?* November 2026 edition. https://sponsorjobs.co/research/visa-sponsorship-adverts-2026. DOI: 10.5281/zenodo.23886878

SponsorJobs is an independent UK job board that lists jobs at Home Office-licensed sponsors and reads every advert. It is not affiliated with the Home Office or UK Visas and Immigration, and this is not immigration advice.
