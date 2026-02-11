# Sri Lanka International Cricket Performance – Power BI Dashboard

## Phase 1: Data Preparation (Power Query)

**Goal:** Build a clean, auditable, analysis-ready fact table.

1. **Data Loading (Best Practice)**
	- Loaded the Kaggle CSV through *Transform Data* instead of direct load.
	- Created two queries: `Matches_RAW` (immutable backup) and `Matches_CLEAN` (all transformations).
	- *Benefit:* Protects raw integrity and ensures traceability.

2. **Data Type Enforcement**
	- Explicitly set data types for critical columns (Match Date → Date, Match Year → Whole Number, Match Format → Text, Opponent Team → Text, Home/Away → Text, Match Winner → Text, Result → Text, Venue columns → Text, Margin Value → Whole Number).
	- *Benefit:* Avoids DAX issues, incorrect summaries, and performance regressions.

3. **Business-Friendly Column Renaming**
	- Renamed cryptic fields (e.g., `Match_Date` → Match Date, `Match_Format` → Match Format, `Opponent` → Opponent Team, `Ground` → Venue (Raw)).
	- *Benefit:* Improves readability for DAX, visuals, and stakeholder conversations.

4. **Result Derivation (Business Logic)**
	- Added Result column via conditional logic in Power Query:
	  | Match Winner | Result    |
	  |--------------|-----------|
	  | Sri Lanka    | Win       |
	  | Opponent     | Loss      |
	  | Draw         | Draw      |
	  | Tie          | Tie       |
	  | No Result    | No Result |
	- *Benefit:* Centralizes match outcome logic before modeling.

5. **Date Consistency Check**
	- Extracted Match Year from Match Date and validated against source.
	- *Benefit:* Guarantees a single source of truth for all time intelligence.

6. **Venue Preparation (Non-Destructive)**
	- Preserved original Venue (Raw) and created Venue Name with Trim + Clean only.
	- *Benefit:* Keeps future options open without premature transformations.

7. **Winning Margin Structuring**
	- Left Winning Margin (Text) untouched.
	- Added Margin Type (Runs/Wickets/Other) and Margin Value (numeric via Column From Examples).
	- *Benefit:* Enables richer analysis while retaining original narrative context.

8. **Power Query Sanity Check**
	- Confirmed no errors, only logical nulls, removed helper columns, then Close & Apply.
	- *Benefit:* Ensures downstream reliability before modeling.

**Status:** Phase 1 complete.

## Phase 2: Data Modeling (Star Schema)

9. **Fact Table Grain Definition**
	- One row per Sri Lanka international match.
	- Supports counts, results, trends, opponent/venue/Home-Away analysis without forcing player/ball granularity.

10. **Date Table Creation (DAX)**
	 - Built a dedicated Date table spanning min/max match dates with Year, Month, Quarter, Year-Month columns.
	 - Marked as the official Date table and disabled Auto Date/Time.

11. **Relationship Setup**
	 - Single active relationship Date[Date] → Matches_CLEAN[Match Date]; one-to-many, single direction.
	 - *Benefit:* Clean, predictable filter propagation for time analysis.

**Status:** Phase 2 complete.

## Phase 3: Core Measures (DAX)

12. **Base Measure**
	 - `Total Matches = COUNTROWS(Matches_CLEAN)` aligns with the defined grain.

13. **Result Measures**
	 - Built Wins, Losses, Draws, Ties, No Results, Win %, Home vs Away splits, format-specific metrics (ODI/T20I/Test), and margin averages.
	 - All measures leverage CALCULATE patterns, reuse base metrics, and avoid hard-coded filters.

14. **Measures Table (Professional Touch)**
	 - Consolidated measures inside `Measures_Table`, hid the helper column.
	 - *Benefit:* Keeps the field list tidy and scalable.

15. **Measure Validation (QA)**
	 - Created an internal `_Validation (Do Not Publish)` page with a table visual to reconcile totals, result breakdowns, and percentages.
	 - Confirmed logical consistency and absence of unexpected blanks/outliers.

**Status:** Phase 3 complete.

---

✅ Phases 1–3 delivered a trusted fact table, a clean star schema, and validated base measures—ready to move into visual design and storytelling.
