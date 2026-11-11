NFL 2024 Offense Dashboard: Team Efficiency by Week

An interactive Tableau Public dashboard that shows how each NFL team's offense performed in the 2024 regular season, how it changed week by week, and how passing and running compare for every team.

Live dashboard: https://public.tableau.com/app/profile/sagar.nibandhe1824/viz/NFL2024OffenseDashboard/Dashboard1

Question

How did each team's offense perform in 2024, and how did it change over the season?

Data

NFL 2024 play by play data from nflverse (play_by_play_2024.csv, the same file as my Projects 1 and 2). I kept run and pass plays that have an EPA value: 35,050 plays across 32 teams.

EPA (expected points added) measures how much a play changes the offense's expected points. A higher value is better.

The raw file is about 100 MB, so it is not included in this repo. Download the 2024 play by play data from nflverse and set the file path in the notebook.

Method
Loaded only the 7 columns needed and kept run and pass plays
Built a table with one row per team per week (570 rows): plays, yards per play, success rate and EPA per play
Built a second table with one row per team: mean EPA on pass plays, mean EPA on run plays, and the gap between them
Exported both tables as CSV files
Built three charts in Tableau Public and combined them in one dashboard
Dashboard
Average EPA per play by team, regular season: all 32 teams ranked, colored from orange (negative) to blue (positive)
Pass EPA against run EPA by team: each dot is a team. The top right is good at both, and the bottom left is weak at both
Weekly EPA per play for the selected team: a trend line with a team filter
Findings
Baltimore had the best offense by EPA per play, followed by Buffalo and Detroit. Cleveland, Las Vegas and Tennessee were at the bottom.
Baltimore was strong at both passing and running. Miami and Las Vegas had the weakest running games, and Cleveland had the weakest passing.
A big gap between pass EPA and run EPA does not mean a team passes well. Miami's gap is large because its run game was poor, while Baltimore's pass EPA was the best of the large gap teams.
Baltimore's best week was week 7 and its worst was week 11.
Limitations
Each team's bar is the average of its weekly averages, so a week with fewer plays counts as much as a week with more.
The dashboard covers the regular season only. Playoff weeks have too few teams for stable averages.
EPA shows how efficient a team was, not how often it chose to pass or run.
The team filter changes only the weekly trend chart.
One season only.
Tools

Python, pandas, Jupyter, Tableau Public

Files
Project3-NFLDashboard.ipynb: data preparation notebook (rename to match your notebook)
team_week.csv: one row per team per week
team_style.csv: one row per team with pass EPA and run EPA
dashboard.png: screenshot of the dashboard
README.md: this file