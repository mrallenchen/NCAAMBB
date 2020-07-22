## Background
College Basketball is notoriously hard to predict. There's a reason why the annual tournament is most widely known as March Madness.

Yet there is still tremendous interest in predicting the outcome of games. From sports betting to office pools, many avenues for people to make their own predictions of the outcome.

## Goal
While there are many models out there, I would also like to try to build my own version to predict basketball outcomes. Specifically, I will develop a model to predict the point differential (or spread) for college basketball game.

## Methodology

1. Data
Data was collected from basketball-reference.com.
    - Through webscraping, pulled season gamelogs for each school

2. Data cleaning and feature engineering
Data needed to be cleaned before use
    - Data manipulation to obtain other needed stats, such as:
        - Spread between teams for each game
        - Running totals of team's history to have snapshot of prior history for each game played
        - aligning both teams' information for each single game
        - removing duplicate games, so only one game shows up

3. Modeling
    - Linear Regression was used to develop the model
    - See presentation for a summary of results, as well as the appendix for a review of LR assumptions


## Deliverables
- [Presentation](NCAA_MBB_final.pdf)
- [Jupyter Notebook for Data Collection](Data_Collection.ipynb)
- [Jupyter Notebook for Data Cleaning](Data_Cleaning.ipynb)
- [Jupyter Notebook for Regression](Regression.ipynb)
- [Glossary of Basketball Statistics](Glossary.md)




## Technologies Used
- Jupyter Notebook
- Python
- Libraries
    - Pandas
    - Numpy
    - Matplotlib
    - Seaborn
    - Beautiful Soup


4. Future Work
- Cross Validation with various seasons
- SOS Adjusted Stats
    - Don't need to include a SOS if I can create SOS-adjusted stats that go into the model...

        https://medium.com/analyzing-ncaa-college-basketball-with-gcp/fitting-it-in-adjusting-team-metrics-for-schedule-strength-4e8239be0530

        This would require, 
        adding in Team and Opponent as one hot variables... 
        running a linear regression after every single day to generate the adjusted metrics to be used for the next day...
        This is because to truly account for this in a predictive model, would need to create SOS adjusted stats for every stat and done so for historical data prior to each game
- Add recency bias
    - Calculate stats using more recent games (maybe restricted to last 10 or 5 or some kind of weighted average)
- Refine Advanced Stats and % stats
    - Used simple averages to calculate the running stats for the advanced stats and % stats. This could be further refined and more technically accurate by recalculating these numbers based on actual formulas.
    - Most obvious for % calculations.
    (For example, if one game has perfect free throw percentage on only 10 free throws, but next game goes 0/20. Then true FT% is 10/30 or 30%, whereas i have calculated 50% because it is average of 0% and 100%.) 
    - Leaving this for now but can come back to update this later. 
- Compare my predictions to the line from other models
    - http://www.thepredictiontracker.com/
    - I have not quite reconciled how to match up games with the data pulled from predictiontracker, issue is with Neutral games and how they are designated as home, and then matching it up correctly
- Create interaction of pace and ORtg/DRtg
- More interactions - difference between the teams playing?
- Time Series effect?
- Run a correlation matrix on the variables to group them so that just one can be picked
- PCA for understanding like features
- Distance to Court (proxy for fan support/away games being more difficult)
- run model again without standardized variables so that coefficients are more interpretable
