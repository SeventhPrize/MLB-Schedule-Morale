# Quantifying Impact of Travel on MLB Team Performance

## Problem statement
A dense schedule with frequent travel can fatigue players. A quantitative understanding of how travel impacts player performance is valuable for team managers looking to plan game tactics, communicate with players, and anticipate season outcomes.

**We evaluate, against an established baseline, how a baseball team’s day-to-day performance is impacted by their travel in the past five days.**

## Baseline: Elo ratings
To compute a team's deviation from expected performance, we first establish a baseline for what counts as typical performance. We use [Elo ratings](https://en.wikipedia.org/wiki/Elo_rating_system), a well-known system for predicting a team's chance of winning against another team, because it gives winning chances in a game-to-game basis.

## Quantifying travel schedule
For each game, we note the teams' activity the past five days (enough time to travel to a series, play, and travel to the next location). For each of the five days, we create variables recording if
1. A home or away game was played, or if it was an off day
2. How many miles were traveled, if any, and in which east/west direction
3. If the game, if one was played, was played at night or day

## Model interpretability is critical: Logistic regression
Model interpretability is an essential quality for team managers looking to trust the model or the use the model to make impactful decisions. Therefore, we use logistic regression because of its high interpretability. We use logistic regression to predict if a team wins a given game based on their five-day history. We adjust for the baseline win expectations provided by Elo ratings. Penalization and cross-validation prevent overfitting.

## Model interpretation
We find that off-days substantially improve the next-day winning odds. For example, a team that has taken an off-day has 6.7% stronger winning odds the next day compared to a team that had just completed a home game or 7.4% stronger winning odds than a team that just completed an away game.

Travel is also impactful. A team that travels to a game expects to have 0.8% to 1.3% weaker winning odds, depending on the direction of travel. Teams that travel east tend to show a longer duration of impacted performance.
