# AI Citation Share by Vertical: A Curated Sample

**Curated by Josh Blyskal · Published by Profound · Data through 2026-11-17**

> **Please read before using.** This is a small, hand-curated sample of verticalized citation data, selected by the curator and released for public use. It is **not** a representative sample of Profound's dataset, and no file is a complete picture of its category or answer engine. Use it for illustration and exploration, not as a definitive or industry-wide measurement.

Global "citation share" headlines average every industry together. This sample breaks the measurement down by vertical and by answer engine, so you can see which sources each engine cited for a set of questions in a given category, and how that changed over four weeks.

- **Contents:** 67 vertical files, plus one stacked file with every row, covering 4 answer engines
- **Period:** 4 weeks ending Nov 17, 2026 (2026-10-21 → 2026-11-17), reported week by week
- **Metrics:** weekly citation share for each of the 4 weeks (7-day aggregates), plus one 4-week change (week 4 − week 1). No daily figures, and no raw citation or question volumes.
- **Terms:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Free to use, share and adapt, with attribution (see below).

## About this sample

- **Hand-curated.** The curator chose which verticals and question sets to include, and left many out. Selection is editorial: it follows no statistical sampling design and is not exhaustive.
- **Not representative.** Don't read results as representative of Profound's full dataset, of any industry or market as a whole, or of what any individual user sees in an AI answer.
- **Partial coverage within each vertical.** Each file reflects a limited set of non-branded questions about that vertical. It doesn't cover every topic, question type, persona, or brand in the category.
- **Not a measure of traffic, market share or brand performance.** Citation share only describes which sources answer engines linked to, for these questions, in these time windows.
- **May not match other Profound figures.** Profound's platform, reports and other publications use different data, scope and methods, so their numbers can differ from this sample.
- **Provided as is**, without warranty of accuracy, completeness or fitness for any particular purpose.

## Use and attribution

Licensed under [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/) (`LICENSE`). You may use, share, adapt and republish this data, provided you attribute it. Credit it as:

> Source: Profound, *AI Citation Share by Vertical: A Curated Sample* (data through 2026-11-17), curated by Josh Blyskal. tryprofound.com

When you publish figures from this sample, please describe them as coming from a curated sample, not as measurements of an entire industry or market.

## What's in the pack

```
README.md                 this file
LICENSE                   CC BY 4.0
manifest.csv              one row per vertical: sector and engines covered
data/<vertical>.csv       one file per vertical (e.g. data/credit-cards.csv)
data/all-verticals.csv    the same rows, stacked in manifest order (4,144 rows)
```

- Every data file has **identical columns**, so you can stack them. `data/all-verticals.csv` is that stack. Each row carries its own `vertical`.
- Files don't overlap: no citation is counted in more than one file.
- Each file stands alone: ranks and shares are relative to that vertical and answer engine only.

## Quick start

1. Find your vertical in `manifest.csv` or the catalog below, and open its file. Or open [`data/all-verticals.csv`](data/all-verticals.csv) and filter `vertical`.
2. Filter `model_name` to the answer engine you care about.
3. Read the four weekly share columns left to right to see each domain's trend, or sort by `change_week1_to_week4_pts` to see which domains gained or lost the most share over the 4 weeks. `weeks_in_top10` shows how consistently a domain held a top-10 spot.

## Time windows

| Week | Dates | Share column |
|---|---|---|
| Week 1 (oldest) | 2026-10-21 → 2026-10-27 | `citation_share_week1_pct` |
| Week 2 | 2026-10-28 → 2026-11-03 | `citation_share_week2_pct` |
| Week 3 | 2026-11-04 → 2026-11-10 | `citation_share_week3_pct` |
| Week 4 (latest) | 2026-11-11 → 2026-11-17 | `citation_share_week4_pct` |

Days are bucketed in US Eastern Time. Weeks are back-to-back 7-day windows ending on the latest complete day (2026-11-17), not calendar Mon–Sun weeks.

### Smoothing

Every share in the pack is a **7-day aggregate**, never a single day. A domain's weekly share is its citations summed over the seven days ÷ the engine's citations to all domains over the same seven days. That equals the average of the seven daily shares, with each day counted in proportion to how many citations it had. Aggregating over a week smooths out day-to-day swings, which at this level of detail are mostly noise. The pack contains no daily figures, and its one change column compares week 4 with week 1 rather than consecutive days or weeks.

## Which domains appear in each file

Within each file, rows are selected **separately for each answer engine**:

- **Top 10:** every domain that was among the engine's 10 most-cited domains in **any** of the four weeks. Each one appears with all four weekly shares, so domains entering and leaving the top 10 are both visible.
- **Pinned social watchlist:** `youtube.com`, `linkedin.com`, `reddit.com` and `facebook.com` are always included when cited at least once in any of the four weeks, even outside the top 10.

The long tail of other cited domains is not listed, but it **is** counted in every share's denominator.

## Column dictionary

| Column | Label | Meaning |
|---|---|---|
| `vertical` | Vertical | Industry vertical (see catalog below). |
| `model_name` | Answer engine | The answer engine that cited the domain. |
| `rootdomain` | Cited domain | Cited site, normalized to its registrable root domain (e.g. `news.google.com` → `google.com`). |
| `channel_group` | Why it's listed | `Top 10` = in the engine's top 10 in at least one of the four weeks; `Pinned social` = pinned social domain that was never in the top 10; `Both` = pinned social domain that was also top 10 in at least one week. |
| `weeks_in_top10` | Weeks in top 10 | Number of the four weeks (0–4) in which the domain ranked in the engine's top 10. 4 = top 10 every week; 0 only for pinned social domains. |
| `rank_week4` | Rank, latest week | Rank among **all** domains this engine cited for this vertical in week 4 (1 = most cited). Blank = not cited in week 4. Ties are broken alphabetically. |
| `citation_share_week1_pct` … `citation_share_week4_pct` | Weekly citation share, 4 weeks ending Nov 17 | The domain's share of all citations this engine gave for this vertical in that week, in percent (a 7-day aggregate; see Smoothing). Week 1 is the oldest, week 4 the latest. **The headline metric.** |
| `change_week1_to_week4_pts` | 4-week change | Week 4 share − week 1 share, in percentage points. Positive = gained share over the 4 weeks. |

Shares are rounded to two decimals, and the change is calculated from the rounded shares so it reconciles. A share of 0.00 means the domain received less than 0.005% of that engine's citations in the week, or none.

### manifest.csv

| Column | Meaning |
|---|---|
| `sector`, `vertical` | Where the file sits in the taxonomy. |
| `file` | Path of the data file inside the pack. |
| `engines` | Answer engines with data in the file. |

## How to read it (and how not to)

- **Shares are within vertical × engine.** If a domain shows 3.30 in `citation_share_week4_pct` for Credit Cards / Google AI Overviews, then 3.30% of the citations Google AI Overviews gave for this sample's credit-card questions in week 4 went to that domain.
- **Read the four weeks as a trend.** A move that builds or holds across several weeks says more than a single jump. Small changes can be sampling noise, especially for low-share domains.
- **Compare an engine with itself over time.** Engines cite sources at very different rates, so the same share means different things on different engines.
- **Shares in a file won't sum to 100%.** Only the top domains are listed; everything else is in the denominator.
- **Ranks are for the latest week only.** Use `weeks_in_top10` for consistency across the four weeks. Below roughly 1% share, a domain can jump many rank positions on a small change.
- **Don't generalize.** A move in this sample is a move in this sample, not evidence of an industry-wide shift.

## Answer engines

| Engine | Files with data |
|---|---|
| ChatGPT | 67 of 67 |
| Google AI Mode | 67 of 67 |
| Google AI Overviews | 67 of 67 |
| Google Gemini | 67 of 67 |

## How the sample was built

- **Questions:** a curated set of open-ended questions that don't name a brand (e.g. "Which tools are most effective for security monitoring?"), drawn from Profound's dataset. Brand-specific questions are excluded.
- **Citations and shares:** a citation is one linked source in one answer-engine response. A weekly share is a 7-day aggregate: a domain's citations ÷ the engine's total citations for the same vertical, both summed over the seven days.
- **Cleaning:** ChatGPT links to openai.com (the engine's own platform links) are removed, domains are normalized to their root domain, and vertical names are harmonized.
- **Curation:** question sets were selected and reviewed by hand for each vertical. Every included question set ran throughout all four weeks. Sets judged off-topic, mixed-topic or sensitive were left out, as were cross-industry umbrella sets. Profound's own category (AI search optimization) is excluded to avoid a conflict of interest. Inclusion or exclusion is an editorial choice and says nothing about a vertical's importance.

## Catalog

| Sector | Vertical | File |
|---|---|---|
| Automotive | Auto Parts | `data/auto-parts.csv` |
| Automotive | Automakers | `data/automakers.csv` |
| Consumer Products | Beauty | `data/beauty.csv` |
| Consumer Products | Beer | `data/beer.csv` |
| Consumer Products | Consumer Electronics | `data/consumer-electronics.csv` |
| Consumer Products | Consumer Packaged Goods | `data/consumer-packaged-goods.csv` |
| Consumer Products | Furniture | `data/furniture.csv` |
| Consumer Products | Household Appliances | `data/household-appliances.csv` |
| Consumer Products | Household Cleaning Products | `data/household-cleaning-products.csv` |
| Consumer Products | Packaged Food & Beverages | `data/packaged-food-and-beverages.csv` |
| Consumer Products | Soft Drinks | `data/soft-drinks.csv` |
| Consumer Products | Watches | `data/watches.csv` |
| Energy & Industrials | Aerospace | `data/aerospace.csv` |
| Energy & Industrials | Oil & Gas | `data/oil-and-gas.csv` |
| Energy & Industrials | Packaging | `data/packaging.csv` |
| Energy & Industrials | Renewable Energy | `data/renewable-energy.csv` |
| Energy & Industrials | Semiconductors | `data/semiconductors.csv` |
| Financial Services | Business Banking | `data/business-banking.csv` |
| Financial Services | Credit Cards | `data/credit-cards.csv` |
| Financial Services | Cryptocurrency | `data/cryptocurrency.csv` |
| Financial Services | Fintech | `data/fintech.csv` |
| Financial Services | Investment Banks | `data/investment-banks.csv` |
| Financial Services | National Banks | `data/national-banks.csv` |
| Financial Services | Private Equity | `data/private-equity.csv` |
| Financial Services | Venture Capital | `data/venture-capital.csv` |
| Healthcare | Hospitals | `data/hospitals.csv` |
| Healthcare | Pharmaceuticals | `data/pharmaceuticals.csv` |
| Healthcare | Pharmacies | `data/pharmacies.csv` |
| Insurance | Auto Insurance | `data/auto-insurance.csv` |
| Insurance | Health Insurance | `data/health-insurance.csv` |
| Insurance | Life Insurance | `data/life-insurance.csv` |
| Insurance | Property Insurance | `data/property-insurance.csv` |
| Media, Sports & Entertainment | American Football | `data/american-football.csv` |
| Media, Sports & Entertainment | Basketball | `data/basketball.csv` |
| Media, Sports & Entertainment | Esports | `data/esports.csv` |
| Media, Sports & Entertainment | Soccer | `data/soccer.csv` |
| Media, Sports & Entertainment | Social Media Platforms | `data/social-media-platforms.csv` |
| Media, Sports & Entertainment | Sports Betting | `data/sports-betting.csv` |
| Media, Sports & Entertainment | Streaming Services | `data/streaming-services.csv` |
| Media, Sports & Entertainment | Video Games | `data/video-games.csv` |
| Professional Services | Accounting Firms | `data/accounting-firms.csv` |
| Professional Services | Consulting Firms | `data/consulting-firms.csv` |
| Professional Services | Law Firms | `data/law-firms.csv` |
| Real Estate | Multifamily Housing | `data/multifamily-housing.csv` |
| Real Estate | Real Estate | `data/real-estate.csv` |
| Restaurants | Casual Dining | `data/casual-dining.csv` |
| Restaurants | Coffee Chains | `data/coffee-chains.csv` |
| Restaurants | Fast Food | `data/fast-food.csv` |
| Retail | Electronics Retailers | `data/electronics-retailers.csv` |
| Retail | Fashion Retailers | `data/fashion-retailers.csv` |
| Retail | Grocery Chains | `data/grocery-chains.csv` |
| Technology & Software | AI Model Providers | `data/ai-model-providers.csv` |
| Technology & Software | CRM Software | `data/crm-software.csv` |
| Technology & Software | Cloud Platforms | `data/cloud-platforms.csv` |
| Technology & Software | Cybersecurity | `data/cybersecurity.csv` |
| Technology & Software | Developer Tools | `data/developer-tools.csv` |
| Technology & Software | Email Marketing | `data/email-marketing.csv` |
| Technology & Software | HR Software | `data/hr-software.csv` |
| Technology & Software | Marketing Automation | `data/marketing-automation.csv` |
| Technology & Software | Online Learning Platforms | `data/online-learning-platforms.csv` |
| Telecom & Consumer Services | Gyms & Fitness Chains | `data/gyms-and-fitness-chains.csv` |
| Telecom & Consumer Services | Wireless Providers | `data/wireless-providers.csv` |
| Travel & Hospitality | Airlines | `data/airlines.csv` |
| Travel & Hospitality | Cruise Lines | `data/cruise-lines.csv` |
| Travel & Hospitality | Hotels | `data/hotels.csv` |
| Travel & Hospitality | Online Travel Agencies | `data/online-travel-agencies.csv` |
| Travel & Hospitality | Vacation Rental Platforms | `data/vacation-rental-platforms.csv` |

---

Source: Profound, *AI Citation Share by Vertical: A Curated Sample* (data through 2026-11-17), curated by Josh Blyskal. tryprofound.com
