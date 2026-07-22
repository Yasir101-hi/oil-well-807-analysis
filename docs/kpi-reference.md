# Well #807 KPI Reference

## Verified Dataset Scope

| KPI | Definition | Verified result |
|---|---|---:|
| Observation period | Minimum to maximum date | 2013-01-01 to 2021-01-18 |
| Daily observations | Number of dataset rows | 2,939 |
| Starting oil rate | First recorded daily oil volume | 49 m³/day |
| Ending oil rate | Last recorded daily oil volume | 5 m³/day |
| Oil-rate decline | 1 − ending rate / starting rate | 89.8% |
| Average oil rate | Mean daily oil volume | 17.62 m³/day |
| Starting water cut | First recorded water-cut value | 29% |
| Ending water cut | Last recorded water-cut value | 70% |
| Average water cut | Mean daily water cut | 70.69% |
| High-water-cut frequency after 2016 | Days with water cut ≥70% / days from 2016 onward | 90.7% |
| Starting reservoir pressure | First recorded pressure | 214 atm |
| Ending reservoir pressure | Last recorded pressure | 100 atm |
| Pressure decline | 1 − ending pressure / starting pressure | 53.3% |
| Zero-oil observations | Days with oil rate equal to zero | 1 |
| Zero-oil date | Date of the zero-rate observation | 2020-05-11 |

## Operational Measures

| Measure | Calculation | Use |
|---|---|---|
| Monthly average oil rate | Mean daily oil rate by calendar month | Smooth short-term volatility |
| Annual average oil rate | Mean daily oil rate by calendar year | Compare operating phases |
| Cumulative observed oil | Sum of daily oil-volume values | Historical production proxy |
| Gas-oil ratio | Gas volume divided by oil volume | Track gas behavior |
| Water-oil ratio | Water volume divided by oil volume | Track water burden |
| Pressure depletion | Change in reservoir pressure over time | Assess energy depletion |
| Working-hours utilization | Recorded working hours relative to 24 hours/day | Identify operating constraints |

## Interpretation Rules

- A production interruption is an observed event; its cause must not be assigned without operational evidence.
- High water cut is a screening signal, not proof that a specific EOR technique will succeed.
- A fitted decline curve is sensitive to the selected period and model.
- Remaining-reserves estimates in the notebook are illustrative and must not be treated as booked reserves.
- Economic-limit decisions require oil price, operating cost, water-disposal cost, intervention cost, and abandonment liability.

## Reproducibility

The public notebook loads `data/well_807_production_data.csv` using a repository-relative path. Its saved outputs are cleared so reviewers can execute the workflow against the published dataset.
