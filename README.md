# Does a Team's Top Scorer Drive Winning? NBA 2021-22 Regression Analysis

Multiple regression analysis in Microsoft Excel of how each NBA team's leading scorer and team scoring relate to team win percentage (N = 30 teams). Course project for ECON 317, December 2021.

**Full paper:** [`outputs/ECON317_QUEEN_QADIR.pdf`](outputs/ECON317_QUEEN_QADIR.pdf) | **Data:** `data/`

## Question

Does having a high-scoring star lead to more team wins, or does winning depend more on how much the whole team scores?

## Data

- Top scorer for each of the 30 teams: points, field goal, three-point and free throw stats, from NBA.com.
- Team win percentage, wins, and team points per game, from NBA.com standings.
- Snapshot taken December 2, 2021, roughly 20 games into the 2021-22 season (about a quarter of the schedule). Results are early-season and based on a small sample.

## Method

Regressions run with Excel's Data Analysis ToolPak, with the specification revised after the first attempt:

**Model 1:** win % on the star's share of team points, plus the star's FG%, 3P% and FT%.
**Model 2:** win % on the star's points per game and team points per game.

I moved from Model 1 to Model 2 because Model 1 used overlapping variables and fit poorly.

## Results

| | Model 1 | Model 2 |
|---|---|---|
| R-squared | 0.34 | 0.67 |
| Adjusted R-squared | 0.23 | 0.64 |
| Observations | 30 | 30 |
| Star PPG | | 2.08 (p = 0.003) |
| Team PPG | | 2.35 (p < 0.001) |

Model 2 (win % measured in percentage points): `win% = -249.46 + 2.083 (star PPG) + 2.352 (team PPG)`

Single-variable fits: team PPG alone explains about 53% of the variation in win percentage, and the top scorer's PPG alone about 40%.

**Takeaways**

- Team scoring matters more than one player's scoring, though both are statistically significant together.
- Holding team scoring constant, each extra point per game from the top scorer is associated with about 2 more percentage points of win percentage.
- Scoring is not destiny: Brooklyn's Kevin Durant (28.6 PPG) led a lower win percentage than Phoenix's Devin Booker (23.2 PPG), 71.4% to 85.7%.

## Limitations

- Only 30 observations, early in the season, so estimates are noisy.
- The star's points are part of team points, so the two predictors overlap by construction.
- Only offense is measured. Defense, injuries and strength of schedule are omitted, so these are associations, not causal effects.
- I did not run formal diagnostic tests such as heteroskedasticity or normality checks on these models. [Add them if you do.]

## Tools

Microsoft Excel: Data Analysis ToolPak (regression, descriptive statistics), charts.
