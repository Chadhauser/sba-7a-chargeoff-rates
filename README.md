# SBA 7(a) Charge-Off Rates by Franchise Brand, Industry and State

Aggregate charge-off rates computed from the complete public record of US Small
Business Administration 7(a) lending, fiscal years 1992 to 2026.

**1,912,539 loans. 1,363,711 resolved.**

Published by [Finance Clearly](https://financeclearly.com). Licensed
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — free to use,
including commercially, with attribution.

---

## Why this exists

The SBA publishes its loan-level data openly, but not aggregated by outcome.
Franchisors publish Item 19 financial performance representations; nobody
publishes what happened to the people who borrowed to buy in.

These tables answer one question: **of loans that reached a conclusion, what
share were charged off?**

## Headline finding

**Franchised businesses are no safer than independents.**

| | Resolved loans | Charge-off rate |
|---|---|---|
| Franchise | 94,550 | **16.0%** |
| Independent | 1,269,161 | **15.8%** |

Effectively identical. But among brands with at least 400 resolved loans,
charge-off rates run from **4.5% to 34.8%** — a 7.7-fold spread that dwarfs
anything attributable to franchising itself.

Buying into a brand does not reduce risk. Choosing the right brand does.

## Files

| File | Rows | Contents |
|---|---|---|
| `chargeoff_by_franchise.csv` | 23 | Brands with ≥400 resolved loans |
| `chargeoff_by_industry.csv` | 20 | NAICS industries with ≥5,000 resolved loans |
| `chargeoff_by_state.csv` | 52 | All states, DC and Puerto Rico with ≥2,000 resolved loans |

All files share the same columns: the grouping key, `resolved_loans`,
`charged_off`, and `chargeoff_pct`.

## Method

- **Source:** SBA 7(a) loan-level data, published under the US Freedom of
  Information Act. Fiscal years 1992–2026.
- **Charge-off rate** = loans with status `CHGOFF` as a share of *resolved*
  loans, where resolved means either paid in full (`PIF`) or charged off.
- **Outstanding loans are excluded.** Their outcome is unknown, and including
  them would understate charge-off rates for recent years.
- **Minimum thresholds applied** before ranking, so small samples cannot
  distort the tables.

### Known data quality issue: franchise names

**Franchise names in the source data are not consistently formatted.** The same
brand appears under multiple spellings — differing in case, punctuation and
trailing whitespace. Aggregating on the raw field splits brands across several
rows and produces wrong figures.

This dataset normalises names before aggregating (uppercase, strip
non-alphanumerics) and merges the resulting groups. Anyone working from the raw
SBA file should do the same. Where the SBA records genuinely distinct franchise
codes for related programmes, those remain separate.

## Limitations

- These are **historical outcomes across three decades**, not a forecast for any
  current franchise offering or industry.
- **Charge-off describes the loan, not the business.** A business can survive a
  charge-off, and a business can close having repaid in full.
- Era matters. Loans approved 2000–2009 charged off at roughly three times the
  rate of those approved in the 2010s, reflecting the financial crisis rather
  than anything about the borrowers.
- **Correlation is not causation.** A high charge-off rate for a brand may
  reflect the sector, the era in which it expanded, or the profile of borrowers
  it attracted, rather than the franchise model itself.

## Citation

> Finance Clearly (2026). *SBA 7(a) Charge-Off Rates by Franchise Brand,
> Industry and State*. Computed from SBA 7(a) loan-level data, FY1992–2026.
> https://github.com/Chadhauser/sba-7a-chargeoff-rates

Analysis and commentary:
https://financeclearly.com/sba-loan-charge-off-rates-by-franchise/

## Corrections

Errors are fixed and noted rather than quietly amended. If you find one, open an
issue or email info@financeclearly.com.

**2026-08-24:** Initial publication. Supersedes earlier figures which did not
normalise franchise names.
