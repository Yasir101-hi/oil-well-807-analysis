# Analysis Methodology and Limitations

## Workflow

1. Load the cleaned daily dataset from `data/well_807_production_data.csv`.
2. Parse ISO dates and verify column names and data types.
3. Check missing values, invalid ranges, and zero-production observations.
4. Create derived time fields, gas-oil ratio, water-oil ratio, and cumulative production.
5. Aggregate daily observations to monthly and annual views.
6. Evaluate oil-rate, water-cut, pressure, working-hours, and gas behavior.
7. Fit screening-level decline models and compare their behavior.
8. Translate technical signals into bounded operational recommendations.

## Dataset Fields

| Field | Unit | Analytical role |
|---|---:|---|
| Date | date | Time-series index |
| Oil volume | m³/day | Primary production indicator |
| Liquid volume | m³/day | Total produced-fluid indicator |
| Gas volume | m³/day | Gas behavior and GOR input |
| Water volume | m³/day | Water burden and WOR input |
| Water cut | % | Produced-water share |
| Working hours | hours/day | Operating-availability indicator |
| Dynamic level | m | Well-performance context |
| Reservoir pressure | atm | Reservoir-energy indicator |

## Data Preparation

- Header line breaks and surrounding spaces were removed.
- Excel serial dates were converted to ISO `YYYY-MM-DD` dates.
- The cleaned public file contains 2,939 rows and nine source fields.
- The notebook uses a relative path so it can run after cloning the repository.
- Saved notebook outputs were cleared; charts and tables can be reproduced locally.

## Evidence Boundaries

The dataset supports observations about production, water cut, gas, pressure, dynamic level, and working hours. It does not directly contain:

- intervention or workover records;
- failure or shutdown reason codes;
- oil prices or operating costs;
- water-disposal and lifting costs;
- reservoir-fluid or rock properties;
- field-wide injection and offset-well response;
- abandonment liability.

Therefore:

- The cause of the 2020-05-11 interruption is not assigned.
- Economic viability is presented as a recommended analysis, not a concluded result.
- EOR options are screening candidates, not approved interventions.
- Decline and reserves calculations are illustrative and require engineering validation.

## Recommended Next Technical Steps

1. Add intervention and downtime-reason records.
2. Perform segmented decline-curve fitting after removing documented downtime.
3. Add operating-cost and price assumptions for economic-limit analysis.
4. Compare Well #807 with offset wells and field pressure-support history.
5. Validate any EOR candidate against reservoir properties and field-scale simulation.
