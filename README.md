# Oil Well #807 Production Performance Analysis

An evidence-based Python analysis of daily oil production, water cut, reservoir pressure, gas behavior, operating hours, decline trends, and intervention-screening signals from 2013 to 2021.

![Well 807 production performance](images/production_trend.png)

## Executive Snapshot

| KPI | Verified result |
|---|---:|
| Analysis period | **2013-01-01 to 2021-01-18** |
| Daily observations | **2,939** |
| Oil rate | **49 → 5 m³/day** |
| Oil-rate decline | **89.8%** |
| Average oil rate | **17.62 m³/day** |
| Water cut | **29% → 70%** |
| Average water cut | **70.69%** |
| Reservoir pressure | **214 → 100 atm** |
| Pressure decline | **53.3%** |
| Zero-oil observations | **1 day** |

## Technical Decision Context

Mature wells require a combined view of production decline, water burden, reservoir energy, and operating availability. This project evaluates:

- How quickly did the oil rate decline?
- How did water cut change across the well life?
- Does reservoir-pressure depletion align with production deterioration?
- Where do working-hour or zero-rate observations indicate operational disruption?
- Which optimization, water-control, or EOR questions deserve further engineering study?
- What additional data is required before making an economic-limit or abandonment decision?

## Dataset

The published dataset contains **2,939 daily records** and nine source fields:

- Date
- Oil volume
- Total liquid volume
- Gas volume
- Water volume
- Water cut
- Working hours
- Dynamic level
- Reservoir pressure

The cleaned file is available at [data/well_807_production_data.csv](data/well_807_production_data.csv). Excel serial dates were converted to ISO dates and header formatting was normalized.

## Analytical Workflow

1. Validate dates, data types, ranges, and missing values.
2. Examine daily, monthly, and yearly production behavior.
3. Calculate gas-oil ratio, water-oil ratio, and cumulative observed production.
4. Review oil-rate decline, water-cut progression, pressure depletion, and operating hours.
5. Identify production phases and anomalous observations.
6. Fit screening-level decline models.
7. Evaluate operational and intervention questions within explicit evidence limits.

The reproducible [Jupyter notebook](well_807_analysis.ipynb) uses a repository-relative path and contains no saved outputs; run it locally to recreate the analysis.

## Verified Findings

### Production decline

- The recorded oil rate declined from **49 m³/day** on the first observation to **5 m³/day** on the last.
- This represents an **89.8% reduction** across the observed period.
- Average daily oil rate across the dataset was **17.62 m³/day**.
- The annual average fell from **36.63 m³/day in 2013** to **7.59 m³/day in 2020**. The 2021 record is partial and covers only 18 days.

### Water burden

- Water cut increased from **29%** to **70%** between the first and final records.
- Average water cut across all observations was **70.69%**.
- From 2016 onward, **90.7% of daily observations** recorded water cut at or above 70%.
- The sustained water burden strengthens the case for water-handling, conformance, and operating-cost review.

### Reservoir pressure

- Reservoir pressure declined from **214 atm** to **100 atm**.
- The observed reduction was **53.3%**, consistent with material reservoir-energy depletion.
- Pressure decline and oil-rate deterioration should be interpreted together with intervention and artificial-lift history, which are not included in the dataset.

### Operational interruption

- Oil production reached **0 m³/day on 2020-05-11**, while eight working hours were recorded.
- The dataset confirms the event but does **not** identify its cause.
- Maintenance, operating constraints, shutdown activity, or external events require supporting operational records before attribution.

## Visual Analysis

### Production Performance

![Oil Production Trend](images/production_trend.png)

### Annual Oil Extraction

![Oil Extraction Per Year](images/oil_extraction_per_year.png)

### Water Cut

![Water Cut Trend](images/watercut_trend.png)

### Decline Analysis

![Decline Curve Analysis](images/decline_curve.png)

### Intervention Screening

![EOR Analysis](images/eor_analysis.png)

## Engineering Interpretation

The history is consistent with a mature, depleted well with a high produced-water burden. The evidence supports a structured technical and economic review; it does not independently prove that the well should be abandoned or that a particular EOR method will succeed.

Screening candidates include:

1. Artificial-lift and pumping-parameter optimization.
2. Water-source diagnosis and conformance-control review.
3. Workover feasibility assessment using intervention history.
4. Economic-limit analysis including water handling and disposal.
5. Field-level pressure-support or EOR screening using offset-well and reservoir data.
6. Abandonment comparison only after estimating remaining value and liability.

## Recommended Next Analysis

- Add failure, shutdown, workover, and intervention records.
- Separate natural decline from documented downtime.
- Add price, lifting cost, water-disposal cost, and intervention cost.
- Test decline models on engineering-selected stable-production periods.
- Compare the well with field injection and offset-well response.
- Validate any EOR candidate against rock, fluid, pressure, and simulation data.

## KPI and Methodology Documentation

- [KPI reference](docs/kpi-reference.md)
- [Methodology and limitations](docs/methodology-and-limitations.md)

These files document calculations, evidence boundaries, and the distinction between observed results and screening assumptions.

## Tools and Skills Demonstrated

- Python and Pandas
- Matplotlib and Seaborn
- Time-series analysis
- Data cleaning and validation
- Production-performance analysis
- Decline-curve screening
- Water-cut and pressure analysis
- Petroleum-engineering interpretation
- Evidence-based technical communication

## Repository Structure

```text
oil-well-807-analysis/
├── README.md
├── well_807_analysis.ipynb
├── data/
│   └── well_807_production_data.csv
├── docs/
│   ├── kpi-reference.md
│   └── methodology-and-limitations.md
└── images/
    ├── production_trend.png
    ├── oil_extraction_per_year.png
    ├── watercut_trend.png
    ├── decline_curve.png
    └── eor_analysis.png
```

## How to Run

1. Clone the repository.
2. Create a Python environment with Pandas, NumPy, Matplotlib, Seaborn, SciPy, Plotly, and Jupyter.
3. Start Jupyter from the repository root.
4. Open `well_807_analysis.ipynb`.
5. Run the notebook cells to reproduce the tables and charts.

## Validation Note

All exact figures in this README were recomputed from the published CSV. Decline fits, reserves estimates, economic limits, and EOR suitability remain screening-level outputs until supported by complete engineering and economic data.

## Author

**Yasir Awad**  
Data Analyst | Business Intelligence | Energy & Operations Analytics

- [GitHub](https://github.com/Yasir101-hi)
- [LinkedIn](https://www.linkedin.com/in/yasirawad)
- Email: [yasir.petro.analytics@outlook.com](mailto:yasir.petro.analytics@outlook.com)

## Project Status

Completed and reproducible. Future development should focus on intervention history, economic-limit modeling, and field-level reservoir context.
