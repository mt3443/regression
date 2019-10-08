## EECS 731 Project 4: Regression by Matthew Taylor

### Overview

This project is meant to be an introduction to regression. Information about NFL games will be used to predict how many points each team scored. Like classification, regression is a type of supervised learning.

### Approach

I began by downloading [this dataset](https://github.com/fivethirtyeight/nfl-elo-game/tree/master/data). The 'initial_elos' file provided a list of all teams, which was  used to encode team names. The other file, 'nfl_games', contained all of the information required to model training and testing. Features in this table include teams in the game, the ELO rating of each team, the date the game was played, the final scores, and more. Once I was aware of everything I had at my disposal, I replaced the team names with integer IDs, and split the date column into three separate columns. Now that all of the data was in an appropriate form, I performed and 80-20 train-test split. Then, I created two linear regression models. I had to create two models to predict the scores of each team, since each model can only predict one value. After training was finished, I scored the performance of each linear regression model. Finally, I trained and tested a random forest regressor in a similar way, so I could compare the performance of each model.

### How to Run

This project was written in a Jupyter Notebook running Python 3.7.2. This project relies on a small number of modules, which can be installed by running this command:
```
pip3 install -r requirements.txt
```

Once the requirements are installed, each of the cells in the Jupyter Notebook can be executed. However, this is not required as each cell has already been executed and the results are shown.

### Results

This project successfully demonstrated how quickly and easily regression models can be used to solve real-world problems. Both models trained rather quickly, in just about a minute. The linear regression model had a test accuracy of about 36%, while the random forest had a test accuracy of about 38%. While these figures may not seem outstanding, it's important to remember they're not predicting which team won, but rather how many points each team scored. I had a sneaking suspicion the model's simply predicted a team scored zero points every time, which was a roadblock I've faced in the past. Thankfully, however, less than 10% of the games in the dataset ended with one team with a score of zero. With this in mind, it's rather impressive that these models are able to predict the exact final score of the games about 37% of the time.

### Future Work and Optimizations

Possible optimizations include tweaking model parameters. There likely exists some combination of settings that would increase the performance of these models. Future work might also include utilizing many more regression models to see exactly which one performs the best. Neural networks are said to have state-of-the-art performance, so it may be interesting to see how they perform relative to these two models.
