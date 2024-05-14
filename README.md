# 2024 March Data Crunch Madness Competition

## Overview

The purpose of this project was to predict the results of the 2024 NCAA Men's Basketball Tournament using machine learning. My team, The Final Fourmulas, placed third in the 2024 March Data Crunch Madness competition, hosted by Fordham University and Deloitte.

Our team took historical data from the 2002-2023 NCAA tournaments and used various feature engineering techniques to identify the optimal features for our model. We then used a blend of supervised machine learning models and ensemble methods to predict the results of the 2024 men's tournament. While our model incorrectly predicted Arizona winning the tournament, we correctly predicted UConn as one of our Final 4 Teams.

We then created a betting model in [Excel](https://docs.google.com/spreadsheets/d/1CfeYYF0GDT1i3K5hLMs4YQoIRpfFTuJj/edit?usp=sharing&ouid=110982489184444063337&rtpof=true&sd=true) that bet on the games using our predictions and calculated the estimated payouts. Our model correctly predicted several upsets and yielded over $330 in estimated earnings based on $10 bets across all games through the Sweet 16.

Please see [here](https://github.com/kimdungeon/MDCM/blob/master/MDCM%20PPT.pdf) for our full presentation.

## Data Preparation

### Data Collection

Our team took the raw csv data from the 2002-2023 tournaments as the primary inputs into our model. We used the 2024 csv data, which contains all possible matchup combinations and outcomes from the 2024 NCAA tournament, to make our predictions. Our goal was to predict the winning probabilities for 'Team1', which is the winning team in a matchup.

The raw data files can be found [here](https://github.com/kimdungeon/MDCM/tree/master/DATA).

We also grabbed external data to find more relevant features that could help us with our predictions. The 3 features we added were:
* Betting Odds: Futures bets from all R64 games from the 2002-2023 NCAA tournaments. This was done to gauge public perception of the expected outcomes.
* Power 6 Teams: Binary variable designating whether a school was in one of the Power 6 conferences (ACC, BE, B10, B12, SEC, PAC). Due to conference realignment, this data was collected by year.
* All-Americans: The number of All-American players (first team-third team) on a team per year.

The supplemental data was aggregated and cleaned via a standalone Alteryx workflow. The output from the workflow was then merged with the csv data.

The supplemental file can be viewed [here](https://github.com/kimdungeon/MDCM/blob/master/MDCM%20Supplemental%20Data_3.19.24.xlsx).

### Feature Selection

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

Definitions for each feature can be found in the Appendix in our presentation.

## Model Results

### Initial Predictions

Our models were trained on all years from 2002-2023 except 2019, which was used as the testing/validation data. Among various models used, the Random Forest classifier yielded the best results over the testing data:


<img width="1220" alt="Screenshot 2024-05-13 at 5 33 37 PM" src="https://github.com/kimdungeon/MDCM/assets/147112213/e622fe2c-ac6a-477a-972a-80bf4b857a8c">


### 2024 Predictions & Betting Model

We used our Random Forest model to create the [Final Fourmulas.csv](https://github.com/kimdungeon/MDCM/blob/master/Final%20Fourmulas.csv) output file, which contains the winning probabilities for all possible matchups in the 2024 tournament. We predicted the following teams would make the Final 4:

  1. **UConn Huskies** (#1 Seed, East)
  2. **Arizona Wildcats** (#2 Seed, West) - **NATIONAL CHAMPION**
  3. **Gonzaga Bulldogs** (#5 Seed, Midwest)
  4. **Colorado Buffaloes** (#10 Seed, South)

We then ran the 2024 predictions through another Alteryx workflow that gave us the final set of predicted outcomes for each tournament game. This file was used to populate the Excel Betting Model mentioned above and can be reviewed [here](https://github.com/kimdungeon/MDCM/blob/master/Predictions_Alteryx.csv).

Our model correctly predicted 4 upsets (including 2 #12 seeds beating #5 seeds) and resulted in positive net earnings of over $330!

## Conclusion

While we ultimately didn't win the competition, I thoroughly enjoyed my experience! This project was an opportunity to apply data science & machine learning to a topic I am extremely passionate about, and we were able to present our findings in innovative and meaningful ways to the audience. I hope that as I develop my skills, I can continue to build upon the success of this model and take on other new, exciting projects as well. Thank you for following me on my journey to becoming a data scientist!
