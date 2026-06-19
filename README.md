# Sri Lanka Cricket Performance Dashboard

Power BI dashboard and supporting report for analyzing Sri Lanka's international cricket performance from 2002 to 2026 across ODI, T20I, and Test formats.

## Project Snapshot
- 1,095 matches analyzed across men's and women's international cricket.
- Built with a star-schema model centered on a `Matches` fact table and a dedicated Date dimension.
- Uses a centralized Measures table for reusable DAX logic covering win rate, rolling form, toss impact, venue performance, opponent comparison, and player-of-the-match counts.
- Includes five report pages: Overview, Format Analysis, Opponent Analysis, Player & Gender Analysis, and Toss & Venue Strategy.

## Dataset
- Source: a custom dataset created and published by Visura Rodrigo on Kaggle.
- Kaggle link: https://www.kaggle.com/datasets/visurarodrigo/sri-lanka-international-cricket-matches-2000pre
- Grain: one row per Sri Lanka international match.
- Coverage: ODI, T20I, and Test matches from 2002 to 2026.
- Preparation flow: Cricsheet scorecards -> Python cleaning and standardization -> BI-ready schema design -> Power Query refresh pipeline.
- Venue metadata was enriched to support consistent Home/Away logic and reliable win-rate calculations.

## Tools & Method
- Power BI Desktop for modeling, report design, and delivery.
- Power Query for ETL, type enforcement, and Home/Away corrections.
- DAX for KPIs, slicer-aware measures, rolling metrics, and Top-N analysis.
- Python for preprocessing and standardizing match data before Power BI ingestion.
- GitHub for version control and project packaging.

## Data Model
- `Matches` connects to Date, Opponent, Venue, Format, and Team dimensions.
- The Date table is marked as the official date table to support time intelligence.
- The Measures table keeps calculations organized and reusable across pages.
- Power Query handles schema enforcement, numeric coercion, and venue-based overrides.
- The model is designed to keep report interactions consistent and audit-friendly.

## Dashboard Pages

### Overview
High-level summary of total matches, wins, losses, win rate, recent form, and yearly performance trends.

![Overview Page Preview](Dashboard/Screenshots/Overview%20.jpg)

### Format Analysis
Compares ODI, T20I, and Test performance, including format-specific win rates, home/away splits, toss effects, and batting-first versus fielding-first outcomes.

![Format Analysis Page Preview](Dashboard/Screenshots/Format%20.jpg)

### Opponent Analysis
Shows which opponents Sri Lanka performs best and worst against, combining win rate, match volume, and outcome distribution.

![Opponent Analysis Page Preview](Dashboard/Screenshots/Opponent%20.jpg)

### Player & Gender Analysis
Compares men's and women's team performance and highlights leading Player of the Match contributors.

![Player & Gender Analysis Page Preview](Dashboard/Screenshots/Player%20%26%20Gender.jpg)

### Toss & Venue Strategy
Focuses on toss impact, batting-first versus fielding-first results, venue win rate, and tournament-category performance.

![Toss & Venue Strategy Page Preview](Dashboard/Screenshots/Toss%20%26%20Venue.jpg)

## Key Insights
- Sri Lanka's strongest format in this dataset is ODI, with T20I close behind and Test results trailing.
- Home results are stronger than away results, which makes venue analysis especially important.
- Toss outcomes have a smaller effect on results than overall team form and opposition quality.
- Performance varies sharply by opponent, making matchup-specific analysis valuable.
- Men's and women's team trends differ enough to justify separate performance tracking.

## Repository Structure
- README.md - project overview and report summary.
- Full Report.md - detailed analytical write-up for the dashboard.
- Dashboard/Power BI/ - Power BI PBIX file and related assets.
- Dashboard/Screenshots/ - screenshot previews used in this README.
- Dataset/ - cleaned CSV dataset used for the dashboard.
- LICENSE - MIT License.

## How to Use
1. Open [Dashboard/Power BI/Dashboard SL cricket.pbix](Dashboard/Power%20BI/Dashboard%20SL%20cricket.pbix) in Power BI Desktop.
2. Ensure [Dataset/sri_lanka_international_cricket_matches_2000_present_clean.csv](Dataset/sri_lanka_international_cricket_matches_2000_present_clean.csv) is available if you need to refresh the model locally.
3. Refresh the report so Power Query can apply the data checks and transformations before DAX measures recalculate.
4. Browse the five report pages using the screenshot previews above as a guide.

## Author
- Visura Rodrigo
- visurarodrigo@gmail.com
- https://www.linkedin.com/in/visura-rodrigo

## License
MIT License. See [LICENSE](LICENSE) for details.
