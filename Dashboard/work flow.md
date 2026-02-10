# Day 1 – Power BI Project Workflow

- Completed Phase 1 (Power Query) data prep: sourced the cleaned international matches CSV, fixed `Margin` typos, enforced correct data types, engineered `Win_Flag`, and split `Margin` into `Margin_Value`/`Winning_Type` for numeric analysis.
- Finished Phase 2 star-schema modeling: added a calculated `DateTable`, linked it 1:M with the main fact on `Match_Date`, and validated the overall star layout for scalability.
- Wrapped Phase 3 core DAX foundations: built the `_Measures` table plus key metrics (Total Matches/Wins/Losses, Win %, Wins LY, Win % Variance with `VAR`) to enable trend tracking.

