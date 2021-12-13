# The Beautiful Game. Investigating European Football Database

## Abstract:
This football dataset is obtained from Kaggle. The data contains more than 25,000 matches, +10,000 players, 11 European countries, team squad formation with (X, Y) coordinates, detailed match events; for example, goal types, possessions, fouls, cards and many more. The dataset spans from 2008 to 2016 seasons and it comes in SQLite database format with 7 tables (Country, League, Match, Player, Player_Attributes, Team, and Team_Attributes). In addition, there are 199 columns combined in this database. We will extract what serves our purpose of analysis and try answer some questions; for instance, what team improved over the period of time? which teams had scored the most number of goals? what attributes that leads the team to most victories? and also dig in to explore players distinctions that dominates the game.

All thanks to [Hugo Mathien](https://www.kaggle.com/hugomathien) for dedicating the time and effort to make this possbile. Further reading and ways to improve the project can be found in Hugo's github repo [here](https://github.com/hugomathien/football-data-collection).

Credit goes to **Mr. Abdulelah Alnajem** from Ministry of Sport for pointing out the anomaly in this question. It turns out the "Penalties" column reference to the attribute of players fetched from FIFA game API; therefore, no sufficient information we can pull to answer this question. As a result, changing the question is necessary.

## Research Questions:
Our base research questions are limited to three. Since Exploratory Data Analysis (EDA) is a continuous cycle, redefining our base is inevitable and thus adding more questions is certain. Our scope in framing questions is to hopefully help sports analysts to extract useful information, technical team managers to fully utilize their best potentials, and the novice to better understand the game. Questions goes as follows:

- Which team had scored the most goals from 2008 to 2016?
- What team improved the most over the time period?
- ~~Which player had the most penalties?~~
- Which league had the maximum number of goals?
    

## Data Description:
Our data is in the form of SQLite database. This database was created by Hugo Mathien on 09/07/2016 and uploaded to Kaggle under Database Contents License (DbCL) v1.0 by Open Data Commons. 

There are more than 25,000 matches, 10,000 player details spanning from 2008 to 2016 seasons. Detailed match events (goal types, possession, corner, cross, fouls, cards, etc...) as well as players and team attributes are also present.

The dataset is relational and includes 7 tables (199 columns in total) with heavy emphasis on boolean values. Our goal here is to consolidate tables we need to conduct our exploration.

Key mentioned attributes

| Variable | Description |
| -   | - |
| home_team_api_id | identifier for home team fetched from FIFA api |
| away_team_api_id | identifier for away team fetched from FIFA api |
| league_id | identifier for league id |
| date | date of the match |
| home_team_goal | number of home team goals |
| away_team_goal | number of away team goals |
| buildUpPlaySpeedClass | classification of team build up play speed; 3 values: <ul><li>Balanced</li><li>Fast</li><li>Slow</li></ul> |
| buildUpPlayPassingClass | classification of team passing style; 3 values: <ul><li>Short</li><li>Long</li><li>Mixed</li></ul> |
| player_name| name of the player | 
| overall_rating | player overall rating based on FIFA game |
| preferred_foot | player's favorite foot, right or left |


## Tools:
The analysis is going to be developed on an IPython notebook. The tools to be used in order to perform our tasks are:

- Python 3.7
- SQLite3 -- This will allow us to establish a database connection
- Pandas
- Numpy
- Matplotlib
- Seaborn
- Pandas Profiling -- generates detailed report with an overview of the dataset, variable properties, interactions, correlations and missing values

