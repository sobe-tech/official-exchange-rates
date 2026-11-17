# Official exchange rates and parallel-market gaps

Central-bank official exchange rates for 25+ countries, each with the bank's own publication date, and — for ten countries
with a parallel (street) market — the gap between an observed real-life indicator and the official rate, rounded in steps.

Published by **SOBE OÜ** (Tallinn, Estonia; Estonian Business Register 16119708), the makers of the
[Currency by SOBE](https://fx.sobeinvest.com/) app. Live pages: <https://fx.sobeinvest.com/for/>.
Methodology: <https://fx.sobeinvest.com/for/method/>.

## Files

| File | What it is |
|---|---|
| [`data/official-rates.csv`](data/official-rates.csv) | One row per country page: official rate, bank, bank date, cross label, rounded gap and its source. Refreshed weekly (Mondays) from <https://fx.sobeinvest.com/for/data/official-rates.csv>, which updates every hour. |

## Columns

| Column | Meaning |
|---|---|
| `page` | The country page the row belongs to |
| `base`, `code` | Currency pair: `rate` is units of `code` per 1 `base` |
| `rate` | Official rate published by the central bank of `code` |
| `rate_kind` | `official` — the bank's own figure; `cross_of_two_banks` / `calculated_cross` — computed from two central banks' rates |
| `bank` | Central bank that publishes the rate |
| `bank_date` | Date the bank's figure applies to |
| `base_bank_date` | For crosses: date of the other bank's figure |
| `own_usd` | `yes` if the bank publishes its own US-dollar rate |
| `gap_pct` | Gap between the real-life indicator and the official rate, in per cent, rounded in steps (5 points up to 50 %, 10 points up to 200 %, 50 above); empty if there is no indicator |
| `gap_source` | Indicator source: elTOQUE (Cuba), DolarApi (Argentina), Yadio USDT P2P median (Venezuela, Nigeria, Libya, Iraq, Ethiopia, Malawi, Algeria), usdmvr.com (Maldives), EuroDZ (Algeria, fallback) |
| `gap_day` | Day the indicator was observed |
| `gap_fallback` | `yes` if a fallback source was used |
| `snapshot_utc` | Time the file was generated |

The gap is an indicator, not a rate for a transaction. USDT P2P offers are a proxy: cash rates may differ.
The real-life rate itself is not published here.

## Licence and citation

Data: [CC BY 4.0](LICENSE). Credit: “Currency by SOBE (fx.sobeinvest.com), SOBE OÜ”. See [`CITATION.cff`](CITATION.cff).
Central-bank figures remain the publications of the respective banks; indicator sources are credited in `gap_source`.

Corrections: fx@sobeinvest.com.
