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