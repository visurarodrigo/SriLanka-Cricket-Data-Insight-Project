# Sri Lanka International Cricket Performance – Power BI Dashboard

**Snapshot:** Clean match-level fact table, disciplined star model, validated DAX core, and a locked executive overview page ready for storytelling.

## Phase 1 · Data Preparation (Power Query)
- Enforced data types, renamed columns for business readability, derived the Result column, and validated Match Year vs Match Date.
- Preserved Venue (Raw), added trimmed Venue Name, structured winning margins, and cleared helper artifacts before Close & Apply.

## Phase 2 · Data Modeling (Star Schema)
- Defined the fact grain as one row per Sri Lanka international match.
- Built and marked a dedicated Date table (Year, Month, Quarter, Year-Month) and disabled Auto Date/Time.
- Created the single active Date[Date] → Matches_CLEAN[Match Date] relationship to govern all time filters.

## Phase 3 · Core Measures (DAX)
- Established `Total Matches` plus reusable result splits (Wins, Losses, Draws, Ties, No Results), Win %, home/away, format splits, and margin averages.
- Organized everything inside `Measures_Table` and hid scaffolding fields for a tidy model tree.
- Validated on a `_Validation (Do Not Publish)` tab to reconcile totals, breakdowns, and percentages.

## Phase 4 · Dashboard Design (Overview Page)
- Executive landing page pairs KPI cards (Total Matches, Wins, Losses, Win %) with a single Match Format slicer.
- Wins-over-time line, result donut, and home/away columns share consistent color semantics (green win, red loss, neutral draw/tie/NR) and dynamic titles.
- Blue-white theme (#EEF4FA canvas, white cards, soft borders) plus disabled cross-filtering keeps the narrative stable; captured insight: Sri Lanka wins more at home than away.
