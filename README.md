# 2024 March Data Crunch Madness Competition

## Overview

The purpose of this project was to predict the results of the 2024 NCAA Men's Basketball Tournament using machine learning. My team, The Final Fourmulas, placed third in the 2024 March Data Crunch Madness competition, hosted by Fordham University and Deloitte.

Our team took historical data from the 2002-2023 NCAA tournaments and used various feature engineering techniques to identify the optimal features for our model. We then used a blend of supervised machine learning models and ensemble methods to predict the results of the 2024 men's tournament. While our model incorrectly predicted Arizona winning the tournament, we correctly predicted UConn as one of our Final 4 Teams.

We then created a betting model in [Excel](https://docs.google.com/spreadsheets/d/1CfeYYF0GDT1i3K5hLMs4YQoIRpfFTuJj/edit?usp=sharing&ouid=110982489184444063337&rtpof=true&sd=true) that bet on the games using our predictions and calculated the estimated payouts. Our model correctly predicted several upsets and yielded over $330 in estimated earnings based on $10 bets across all games through the Sweet 16.

Please see [here](https://github.com/kimdungeon/MDCM/blob/master/MDCM%20PPT.pdf) for our full presentation.

## Process

### Source Data

Our team took the raw csv data from the 2002-2023 tournaments as the primary inputs into our model. We used the 2024 csv data, which contains all possible matchup combinations and outcomes from the 2024 NCAA tournament, to make our predictions. The raw data files can be found [here](https://github.com/kimdungeon/MDCM/tree/master/DATA).

We also grabbed external data to find more relevant features that could help us with our predictions. The 3 features we added were:
* Betting Odds: Futures bets from all R64 games from the 2002-2023 NCAA tournaments. This was done to gauge public perception of the expected outcomes.
* Power 6 Teams: Binary variable designating whether a school was in one of the Power 6 conferences (ACC, BE, B10, B12, SEC, PAC). Due to conference realignment, this data was collected by year.
* All-Americans: The number of All-American players (first team-third team) on a team per year.

The supplemental data was aggregated and cleaned via a standalone Alteryx workflow. That file can be viewed [here](MDCM Supplemental Data_3.19.24.xlsx).

### Final Features

Using both principal component analysis (PCA) and variance inflation factor (VIF), our team determined the following as our final features:
  1. Log5 Winning Odds
  2. Seed_Tier_1
  3. Adj. Defensive Efficiency
  4. Team Season Win %
  5. Number of All-Americans
  6. Coach Career Win %
  7. Coach Sweet 16 Rate
  8. Power 6 Team
  9. Opponent Shooting %
  10. R64 Odds

### Machine Learning


### 2024 Predictions

## Conclusion


