# March Madness: Predicting Round 1

This was my favourite project that I did during my Data Science bootcamp at General Assembly Bitmaker. It combined my new obsession with data science, with my greatest obsession, anything sports related. In particular, I have been watching March Madness since before I can remember. Being able to learn so much about data manipulation and machine learning, on an area that I consider myself an expert (basketball), was extremely challenging, but also, quite fun! 

For this project, I attempted to predict the first round outcomes of March Madness by looking at statistics from 2003-2017. There are 4 datasets that I will be using:

      -Regular Season (Statistics for all regular season games)
      -March Madness (Outcomes for the tournament each year)
      -March Madness Seeds (The teams and seeding for every year)
      -Team Information (Team id numbers, team names, and conference information).

# Data Prep

A large part of the work is located in the notebook 'data_prep'. As the statistics were scraped from the web (by my Data Science Teacher, Max Humber), they existed in a format that needed to be reorganized in order to start modeling. Information for regular season games were listed with the winner and loser of each game in the same row, with the scores also in the same row. It took some creative maneuvering to place this data in a useable format. Also in the data_prep notebook, I organized and cleaned regular season data and created columns/variables for the following stats per team: 

            -Wins (number of wins per season)
            -Plus Minus (accumulation of plus and minus over the entire season)
            -Three Point Average (Average of 3 point percentage per game)
            -Free Throw Attempts (Average of free throw attempts per game)
            -Offensive Rebounds (Average of offensive rebounds per game)
            -Turnovers per Game (Average of turnovers per game)
            -Field Goals Average (Average of field goals percentage per game)

These would then be used in the march_madness notebook for modeling.

# Modeling

The best model ended up being a logistic regresstion, using the Recursive Feature Elimination tool. With this method, the process of dropping features and model building was repeated until only 3 elements were left: 'seed', 'plus/minus', and 'wins * plus/minus'. It can be seen from looking at most of the data and the modeling that seeding remains the most important predictor. Our first naive model (based solely on tournment seeding) scored .746 on the training data and .755 on the test data. The second model, which incorporated conferences with seeds, the training data scored .743 and the test data .76. The final model using Recursive Feature Elimination only slightly outscored the second model. This is all to say, that as is mentioned throughout the notebooks, most of the teams that are seeded between 5-12 have similar season statistics so predicting who will win these games is extremely challenging. Every team that qualifies for the March Madness tournament has impecable records, so to qualify above 12, means that your team most likely only lost a handfull of times, and is extremely competitive.

# Final Remarks 

Although I failed to make a model that could make amazing predictions (and make some money in the process), I am not completely shocked by this. The NCAA seedings are highly reflective of regular season stats, and the conferences that they occurred in. It would be shocking to me if incorporating those statistics could out predict NCAA's own analysis of each team's worth by any LARGE margin (I was hopeful for an .8 though!).

# Taking it further  ...

When I continue working on this project, I would like to consider the following:
        
I would solely focus on teams seeded between 5 and 12. These are the interesting match ups that are hard to predict.
        
I would also like to incorporate the performance of the team during the previous tournament. If teams did well in the previous year and have returning players, this type of experience is significant.
        
I would look in to more information on non-regular season games, including which teams won their conferences, and which teams played eachother in early season tournaments. Teams from different conferences often play eachother in early season tournaments, and those outcomes could aid in predicting first round matchups, and in attempting to measure the strengths of different conferences.
