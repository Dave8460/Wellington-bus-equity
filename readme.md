# Wellington Bus Equity: Reliability and Service Supply by Deprivation

**Summary:** Are bus stops in more deprived New Zealand meshblocks less punctual and less frequently served than stops in less deprived areas? This project starts with Wellington and is designed to extend to Auckland.

## Research questions

1. **Reliability:** Do bus stops in more deprived meshblocks have a lower share of on-time arrivals than stops in less deprived meshblocks?
2. **Supply:** Do stops in more deprived meshblocks have fewer scheduled buses per hour than stops in less deprived meshblocks?

Each question will be broken down by:
- Time of day (peak vs off-peak)
- Weekday vs weekend
- Route, to identify which routes contribute most to any gap

## Definitions

- **On time:** A bus arrives at or departs a stop between 1 minute early and 5 minutes late, following Metlink's definition.
- **Share on time:** Number of on-time observations divided by total observations for a group (stop, route, time band or deprivation group).
- **Scheduled buses per hour:** Number of scheduled trips serving a stop in a given hour, taken from the GTFS static timetable.
- **Deprivation group:** NZDep2023 deciles grouped into bands, to be defined before analysis.

## Data sources

| Source | Use | Access | Date downloaded |
|---|---|---|---|
| Metlink GTFS static timetable | Scheduled stop times and service pattern | `static.opendata.metlink.org.nz/v1/gtfs/full.zip` | _to fill_ |
| Metlink GTFS realtime feed | Live vehicle and trip updates, collected from start date | Metlink Developer Portal (free key) | Collection start: _to fill_ |
| NZDep2023 meshblock data | Area-level deprivation scores | University of Otago, Wellington | _to fill_ |
| Stats NZ meshblock boundaries (2023) | Links stops to meshblocks | Stats NZ Geographic Data Service | _to fill_ |

## Scope

**In scope:** Scheduled service levels and punctuality for Metlink bus services in the Wellington region, compared across area-level deprivation.

**Out of scope:** Ridership and passenger numbers (not in the feed), individual-level outcomes, and any claim about the causes of delay.

## Limitations

- **Deprivation is area-level.** Findings describe stops and areas, not the people who ride the buses.
- **Realtime history starts from the collection date.** Data collected before this project began is not available.
- **Realtime data is predictive.** Measuring actual lateness requires matching predictions to observed passes, and some records will be missing.
- **Meshblock codes change over time.** The deprivation and boundary files must use the same meshblock year.

## What would change our conclusion

If the reliability gap disappears once time of day is controlled for, the finding is about service timing, not area. If the supply gap disappears once route type is controlled for, the finding is about route design, not deprivation.

## Planned phases

1. **Phase 1 (Wellington):** Collect data, build the pipeline, answer both research questions, and publish a case study.
2. **Phase 2 (Auckland):** Repeat the same pipeline using Auckland Transport data, and compare results across the two cities.

## Project structure

```
wellington-bus-equity/
├── data/
│   ├── raw/          (downloaded files, never edited)
│   └── processed/    (cleaned files)
├── sql/              (transformation scripts)
├── notebooks/        (exploration and analysis)
├── dashboard/        (Power BI file)
└── README.md
```

## Status

- [x] Project setup and data access
- [ ] Realtime collection running
- [ ] Cleaning and joins
- [ ] Analysis
- [ ] Dashboard and case study