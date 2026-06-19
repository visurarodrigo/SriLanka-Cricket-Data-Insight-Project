# Sri Lanka Cricket Performance Dashboard — Report

## Project Overview

This Power BI dashboard analyzes Sri Lanka's international cricket performance from 2002 to 2026, covering **1,095 matches** across three formats (ODI, T20I, Test) and both Men's and Women's national teams. The dashboard is built around a single fact table (`Matches`) connected to a custom Date dimension table, with a centralized measures table holding all DAX calculations.

The objective was to move beyond a simple match log and surface the strategic questions a cricket analyst would actually ask: Which format does Sri Lanka perform best in? Does winning the toss matter? Which opponents and venues are historically strongest/weakest? Who are the standout players? How does the Women's team compare to the Men's team?

The report is structured across **5 pages**, each focused on a single analytical theme.

---

## Page 1 — Overview

**Purpose:** Give a viewer the complete performance picture in under 10 seconds, before they drill into anything else.

### What's on this page

A header band introduces the report, followed by a row of 5 KPI cards: **Total Matches, Wins, Losses, Win %,** and **Last 10 Matches Win %**. The last card is a rolling-form indicator — it answers "how is the team doing *right now*," not just across 24 years of history, which static totals can't show.

Below the KPI row sits a **line chart** plotting Win % by year, with a flat reference line marking the all-time average (41.9%). This lets a viewer instantly see which years Sri Lanka over- or under-performed relative to its own historical baseline, rather than just seeing raw win counts that are distorted by how many matches were played that year.

To the right, a **donut chart** breaks down all match outcomes (Win / Loss / Draw / Tie / No Result) for the full 1,095-match history.

At the bottom, a **horizontal bar chart** compares Win % at Home vs Away. This page also carries two **slicers** — Format and Team (Men's/Women's) — that filter every visual on the page, so a viewer can immediately narrow the whole story to, say, "Men's T20Is only."

### Key insight surfaced

Sri Lanka wins **45.7%** of matches played at home versus only **39.9%** away — a meaningful home-ground advantage that sets up the deeper venue analysis on Page 5.

---

## Page 2 — Format Analysis

**Purpose:** Compare Sri Lanka's performance across the three match formats and test two classic cricket strategy questions — does winning the toss matter, and does batting or fielding first matter — within each format.

### What's on this page

Three **multi-row KPI cards** — one each for ODI, T20I, and Test — show matches played and win % per format side by side. This replaces the generic, repeated KPI cards from earlier dashboard drafts with format-specific numbers that actually change the story per card.

A **horizontal bar chart** ranks the three formats by Win %, making the comparison immediate. Below it, a **clustered column chart** breaks each format down further into Home Win % vs Away Win %, showing whether the home advantage seen on Page 1 holds consistently across formats or is concentrated in just one.

A **pivot table (matrix)** cross-tabulates Win % by Year × Format with conditional color formatting — this is the densest visual on the page, acting as a heatmap that reveals not just *which* format is strongest, but *when* Sri Lanka's strength in that format peaked or declined.

Finally, two **column charts** address toss strategy directly: "Toss Outcome Effect" (Win % when SL wins the toss vs. when SL loses it) and "Decision Effect" (Win % when batting first vs. fielding first), both broken down by format. A Year slicer lets the viewer isolate any time window for all of the above.

### Key insight surfaced

ODI is Sri Lanka's strongest format at **43.4%** win rate, ahead of T20I (**41.1%**) and Test (**38.5%**). Winning the toss provides only a marginal edge (**43.0%** vs **40.8%** win rate) — suggesting the toss is a far smaller factor in Sri Lanka's results than team form or opposition strength.

---

## Page 3 — Opponent Analysis

**Purpose:** Answer "who does Sri Lanka beat, and who beats Sri Lanka?" — framed by win rate rather than raw match counts, since some opponents have been played far more often than others.

### What's on this page

The centerpiece is a **clustered column chart** of Win % by Opponent, also carrying Total Matches, Wins, and format-specific win counts (ODI/T20/Test Wins) as supporting fields — so hovering over any opponent's bar reveals the full breakdown without needing a separate visual.

A **scatter chart** plots Total Matches (x-axis) against Win % (y-axis) for every opponent, with each point labeled by country. This view separates two different ideas that a bar chart alone can't show together: *how often* Sri Lanka plays an opponent (rivalry frequency) versus *how well* they do against them (rivalry strength) — a team in the top-right is both a frequent and favorable opponent, while a team in the bottom-right is frequently played but historically dominant over Sri Lanka.

A **stacked bar chart** on the right shows the full Win/Loss/Draw/Tie/No-Result split for each opponent, giving the complete outcome distribution rather than just a single win percentage. Three slicers — Team, Home/Away, and Format — let a viewer narrow this down to, for example, "Women's ODIs played away from home against each opponent."

### Key insight surfaced

Sri Lanka's results vary dramatically by opponent: a **67.6%** win rate against Bangladesh (the most favorable major rivalry) against just **24.6%** against India — despite India being the most frequently played opponent (179 matches), making it Sri Lanka's toughest historical matchup by volume.

---

## Page 4 — Player & Gender Analysis

**Purpose:** Shift focus from team-level results to individual contribution and to a comparison that's largely invisible in match logs — how the Women's national team's results compare to the Men's.

### What's on this page

Two **multi-row KPI cards** sit side by side: Men's Team (Matches, Wins, Win %) and Women's Team (Matches, Wins, Win %), giving a direct head-to-head comparison of program-level performance. A Team slicer lets either side be isolated for the rest of the page's visuals.

A **line chart** plots Win % by Year, split by Team (Men's vs Women's), so the comparison isn't just a single snapshot number but a trend — showing whether the gap between the two programs is widening, narrowing, or stable over time.

A **horizontal bar chart** ranks the top Players of the Match by award count, also split by Team. This required a dedicated DAX measure that filters Player of Match awards to only count matches Sri Lanka actually won (since Player of the Match can be awarded to an opposing player when Sri Lanka loses), ensuring only Sri Lankan match-winners appear in the ranking.

### Key insight surfaced

The Men's team's win rate (**44.0%**) is notably higher than the Women's team's (**33.3%**), a gap worth tracking over time using the year-by-year trend line. On the player side, **KC Sangakkara (31 PoM awards)** and **TM Dilshan (29)** lead the Men's program, while **AC Jayangani (23)** is the standout for the Women's team — making her the third-highest PoM earner across the entire dataset, men's and women's combined.

---

## Page 5 — Toss & Venue Strategy

**Purpose:** A focused, strategy-oriented page answering two questions: does the coin toss actually influence outcomes, and which grounds suit Sri Lanka best?

### What's on this page

Two **KPI card pairs** restate the toss effect numbers from Page 2 (Win % Won Toss vs Lost Toss; Win % Batting First vs Fielding First) so this page can stand alone as a "strategy briefing" without requiring the viewer to flip back to Page 2.

A **clustered column chart** shows Win % by toss decision (bat/field), broken down by format — this is more granular than the Page 2 version because it isolates the decision effect specifically rather than combining it with the toss-outcome effect.

The **"Win % by Venue"** column chart is the main analytical visual on this page, also carrying Total Matches and Home/Away as supporting context. Because some venues have only hosted a handful of matches (which would produce misleading 100% or 0% win rates), this chart should be read alongside the match-count context to avoid over-interpreting small samples — grounds with very few matches are statistically unreliable.

A final wide **column chart** breaks down Win % by Tournament Category (World Cup/WT20, Asia Cup, Home Series, Away Series, Other) — answering whether Sri Lanka performs differently under the pressure of global tournaments versus bilateral series. A Year and Format slicer pair lets a viewer narrow the entire page to any specific era or format.

### Key insight surfaced

The toss decision has a modest effect — batting first yields a **42.7%** win rate versus **41.0%** when fielding first — reinforcing the Page 2 finding that toss-related factors are secondary to team form and opposition quality in determining match outcomes.

---

## Data & Modeling Notes

- **Source data:** 1,095 international matches (2002–2026), 13 original columns, extended with 7 custom Power Query columns (Match Result, SL Won Flag, SL Toss Won Flag, Tournament Category, Team, Margin Type, Era).
- **Data model:** Star schema with a dedicated Date Table (marked as the official date table) related 1-to-many to the Matches fact table, plus a separate Measures Table holding all DAX logic.
- **DAX measures:** 25+ measures covering win rates, format splits, home/away splits, toss analysis, gender splits, rolling form, and player-of-match counts — all built with explicit `DIVIDE()` zero-handling and `CALCULATE()` filter context to avoid context-bleed errors (e.g. the Player of Match count required filtering to `Winner = "Sri Lanka"` specifically, since PoM can otherwise reflect an opposing player's award).
- **Design system:** A custom Sri Lanka cricket color theme (navy `#003087`, gold `#C8A400`, maroon `#7A0020`) is applied consistently across all 5 pages so that "Win" and "Loss" always map to the same colors regardless of chart type.

---

*Dashboard: `Dashboard_SL_cricket.pbix` — 5 pages, 25+ DAX measures, 1,095 matches analyzed.*