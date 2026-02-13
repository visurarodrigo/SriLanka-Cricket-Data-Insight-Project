# Sri Lanka International Cricket Performance – Power BI Dashboard
Industry-ready Power BI case study by Visura Rodrigo combining custom cricket data, disciplined modeling, and interview-focused storytelling.

## 1. Project Overview
Sri Lanka International Cricket Performance – Power BI Dashboard encapsulates over two decades of match history into an accessible, decision-focused experience. Built specifically to showcase internship and junior analyst capabilities, the solution emphasizes transparent metrics, governed slicer experiences, and concise narratives that hiring managers can review in minutes.

## 2. Dataset Description
- Source: This project uses a custom dataset created and published by me on Kaggle.
- Kaggle link: https://www.kaggle.com/datasets/visurarodrigo/sri-lanka-international-cricket-matches-2000pre
- Grain: One row = one Sri Lanka international match (2000–present) spanning ODI, T20I, and Test formats.
- Preparation flow: Raw Cricsheet scorecards → Python cleaning & standardization → BI-ready schema design → Power Query refresh pipeline.
- Notes: Venue metadata was enriched to support dependable Home/Away logic and downstream Win % calculations.

## 3. Tools & Technologies
- Power BI Desktop for modeling, page design, and delivery.
- Power Query for ETL, column typing, venue-based Home/Away corrections, and quality gates.
- DAX for standardized KPIs (Win %, Run Rate, Top-N insights, slicer-aware measures, interaction locks).
- GitHub for version control, documentation, and recruiter sharing.

## 4. Data Modeling & Preparation
- Fact Matches table linked to Date, Opponent, Venue, and Format dimensions to maintain a star-schema discipline.
- Dedicated Date table unlocks time intelligence (rolling Win %, YoY deltas, seasonality diagnostics).
- Central Measures table stores all calculations, improving discoverability and reuse during new page builds.
- Power Query handles schema enforcement, numeric coercion, and venue-driven Home/Away overrides to resolve supplier inconsistencies.
- Python preprocessing ensures consistent opponent naming, match IDs, and field selections before ingestion into Power BI.

## 5. Dashboard Pages & Insights
### Overview
- Executive-ready snapshot of Win %, match volume, and run-rate trends segmented by year, format, and geography to frame Sri Lanka’s long-term trajectory.

### Format Analysis
- Drill-down into ODI, T20I, and Test performance with reusable format-specific measures surfacing momentum swings, batting vs bowling splits, and head-to-head comparison points.

### Opponent & Venue Analysis
- Top-N visuals spotlight priority opponents and venues, layering Home/Away splits, crowd leverage, and slicer-driven diagnostics to inform tour preparation.

### Overview Page
![Overview Page](Dashboard/Screenshots/Overview%20Page.jpg)
Curated executive summary with locked interactions, spotlighting Win %, match pace, and recent form across formats without overwhelming stakeholders.

### Format Analysis Page
![Format Analysis Page](Dashboard/Screenshots/Format%20Analysis%20Page.jpg)
Side-by-side format narratives combining DAX-driven KPIs, seasonal context, and comparative cards to evidence analytical depth.

### Opponent & Venue Analysis Page
![Opponent & Venue Analysis Page](Dashboard/Screenshots/Opponent%20%26%20Venue%20Analysis.jpg)
Top-N opponent and venue breakdown with adjustable slicers, highlighting where Sri Lanka extracts the most advantage and where strategies must adapt.

## 6. Key BI Skills Demonstrated
- Power Query-based data remediation, including venue-driven Home/Away corrections and auditable refresh logic.
- Star-schema modeling with a dedicated Date table and governed Measures table.
- DAX craftsmanship covering Win %, Run Rate, Top-N selections, and interaction-aware calculations for locked narratives.
- Insightful storytelling that guides viewers through slicer-driven yet controlled experiences.
- Portfolio-friendly documentation and Git-based project packaging.

## 7. Repository Structure
- README.md – Project documentation and recruiter briefing (this file).
- Dashboard/Power BI/ – PBIX and supporting Power BI assets.
- Dashboard/Screenshots/ – JPEG captures referenced in the Dashboard Pages section.
- Dataset/ – Clean CSV published on Kaggle plus supporting metadata.
- LICENSE – MIT License granting usage rights.

## 8. How to Use This Project
1. Clone the repository and open the PBIX file inside Dashboard/Power BI/.
2. Ensure Dataset/sri_lanka_international_cricket_matches_2000_present_clean.csv is accessible (adjust the data source path if necessary).
3. Refresh the model so Power Query runs venue-based corrections and schema validations before DAX evaluates Win % and Run Rate measures.
4. Navigate the three dashboard pages; slicer interactions are intentionally locked to keep the story coherent during demos.

## 9. Author & Contact
- Author: Visura Rodrigo
- Role: Undergraduate Data Science & Business Analytics student developing industry-focused BI portfolios.
- Contact: visurarodrigo@gmail.com | https://www.linkedin.com/in/visura-rodrigo
- License: MIT License (see LICENSE for terms).
