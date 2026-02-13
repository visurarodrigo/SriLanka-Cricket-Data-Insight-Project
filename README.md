## 1. Project Overview
Sri Lanka International Cricket Performance – Power BI Dashboard is a recruiter-ready BI asset designed by Visura Rodrigo, an undergraduate Data Science & Business Analytics student. The dashboard consolidates 20+ years of Sri Lanka’s international cricket results into three audience-friendly pages to highlight match performance patterns, contextual storytelling, and practical BI craftsmanship suitable for internship and junior analyst interviews.

## 2. Dataset Description
- Source: This project uses a custom dataset created and published by me on Kaggle.
- Kaggle link: https://www.kaggle.com/datasets/visurarodrigo/sri-lanka-international-cricket-matches-2000pre
- Grain: One row represents a single Sri Lanka international match between 2000 and the present.
- Coverage: ODI, T20I, and Test fixtures with match metadata, opponent, venue, and result fields optimized for BI consumption.
- Preparation: Match-level scorecards were collected from Cricsheet, standardized in Python, structured for BI, and refreshed via Power Query.

## 3. Tools & Technologies
- Power BI Desktop for modeling, DAX, and dashboard design.
- Power Query for ETL, validation, and venue-based Home/Away corrections.
- DAX for reusable KPIs such as Win %, Run Rate, Top-N opponent breakdowns, and dynamic slicer reactions.
- GitHub for version control and portfolio presentation.

## 4. Data Modeling & Preparation
- Star-schema mindset with Fact Matches linked to dimension tables (Date, Opponent, Venue, Format).
- Dedicated Date table ensures reliable time intelligence calculations.
- Measures stored centrally in a Measures table for governance and reuse.
- Power Query steps handle schema enforcement, numeric typing, and venue-driven Home vs Away flag corrections to resolve supplier data gaps.
- Python preprocessing established consistent team names and primary keys before ingestion.

## 5. Dashboard Pages & Insights
### Overview
- Macro-level view of Win %, match volume, and run-rate trends segmented by year, format, and location to support executive briefs.

### Format Analysis
- Deep dive into ODI, T20I, and Test splits with format-specific DAX metrics, highlighting momentum swings, batting vs bowling impact, and head-to-head success rates.

### Opponent & Venue Analysis
- Top-N visuals isolate most frequent opponents and venues, layering Home/Away context, crowd leverage, and slicer-driven insights for pre-tour planning.

### Overview Page
![Overview Page](Dashboard/Screenshots/Overview%20Page.jpg)
Professional summary of Sri Lanka’s overall performance, Win %, and recent form, with locked interactions to protect narrative flow.

### Format Analysis Page
![Format Analysis Page](Dashboard/Screenshots/Format%20Analysis%20Page.jpg)
Comparative visuals showing how Sri Lanka fares across formats, including DAX-driven metrics per opponent and season for analyst briefings.

### Opponent & Venue Analysis Page
![Opponent & Venue Analysis Page](Dashboard/Screenshots/Opponent%20%26%20Venue%20Analysis.jpg)
Focuses on high-impact venues and rivalries, combining Top-N analysis and slicers so decision-makers can quickly evaluate touring priorities.

## 6. Key BI Skills Demonstrated
- Clean, auditable data preparation pipelines using Power Query.
- Correct BI modeling with dedicated Date and Measures tables and a star-schema-ready mindset.
- Robust DAX practices covering Win %, Home vs Away logic, and Top-N opponent/venue calculations.
- Interaction-locked dashboards that balance slicer control with guided storytelling.
- Business-focused insight framing suited for leadership reviews and interviews.

## 7. Repository Structure
- README.md – Project documentation and usage guide.
- Dashboard/Power BI/ – Power BI Desktop artifacts (PBIX, templates, export files).
- Dashboard/Screenshots/ – PNG captures used in this README for recruiters.
- Dataset/ – Cleaned CSV published on Kaggle plus supplementary metadata.

## 8. How to Use This Project
1. Clone the repository and open the Power BI Desktop file inside Dashboard/Power BI/.
2. Place the dataset CSV (Dataset/sri_lanka_international_cricket_matches_2000_present_clean.csv) in the same folder or update the data source path.
3. Refresh the model to trigger Power Query steps, ensuring venue-based Home/Away corrections run before DAX evaluates Win %.
4. Explore the three dashboard pages using slicers; interactions are intentionally locked to preserve analytical narratives.

## 9. Author & Contact
- Author: Visura Rodrigo
- Role: Undergraduate Data Science & Business Analytics student building industry-focused BI portfolios.
- Contact: visurarodrigo@gmail.com | https://www.linkedin.com/in/visura-rodrigo
