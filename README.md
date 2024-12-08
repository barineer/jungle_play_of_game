# Step 1
## Analysis of Jungle Players' Impact on Team Success in League of Legends

My favorite position in League is Jungle. I find the idea of simultaneously fighting AI to get an advantage over human players intriguing, and I would like to dive into the data to find out what difference a good jungle player makes to a winning League of Legends team. I am looking at the 116,304 rows of the League of Legends Spring 2023 Dataset and the question I have chosen to answer is whether the highest performing jungle players correlate to the best teams. These are a few key columns I have identified for obtaining these insights:

### Player Performance (Jungle Specific)

- **participantid**: Unique identifier for the player in the game.
- **position**: The role or position the player is playing (e.g., jungle).
- **playername**: The name of the player.
- **playerid**: Unique identifier for the player.
- **champion**: The champion the player is using in the game.
- **kills**: Number of kills the player has achieved.
- **deaths**: Number of times the player has died.
- **assists**: Number of assists the player has provided.
- **doublekills**: Number of double kills (two kills in quick succession).
- **triplekills**: Number of triple kills (three kills in quick succession).
- **quadrakills**: Number of quadra kills (four kills in quick succession).
- **pentakills**: Number of penta kills (five kills in quick succession).
- **firstblood**: Indicates if the player got the first kill of the game.
- **firstbloodkill**: Indicates if the player was the first to kill an opponent.
- **firstbloodassist**: Indicates if the player assisted in the first kill.
- **firstbloodvictim**: Indicates if the player was the first to die.
- **damagetochampions**: Total damage dealt to enemy champions.
- **dpm**: Damage per minute.
- **damageshare**: Percentage of the team's total damage dealt by the player.
- **damagetakenperminute**: Damage taken per minute.
- **damagemitigatedperminute**: Damage mitigated per minute.
- **wardsplaced**: Number of wards placed by the player.
- **wpm**: Wards placed per minute.
- **wardskilled**: Number of enemy wards destroyed.
- **wcpm**: Wards cleared per minute.
- **controlwardsbought**: Number of control wards bought.
- **visionscore**: Overall vision score, combining wards placed, wards destroyed, and other vision-related actions.
- **vspm**: Vision score per minute.
- **totalgold**: Total gold earned.
- **earnedgold**: Gold earned during the game.
- **earned gpm**: Gold earned per minute.
- **earnedgoldshare**: Percentage of the team's total gold earned by the player.
- **goldspent**: Total gold spent.
- **gspd**: Gold spent per death.
- **gpr**: Gold per resource.
- **total cs**: Total creep score (minions and monsters killed).
- **minionkills**: Number of minions killed.
- **monsterkills**: Number of monsters killed.
- **monsterkillsownjungle**: Number of monsters killed in the player's own jungle.
- **monsterkillsenemyjungle**: Number of monsters killed in the enemy's jungle.
- **cspm**: Creep score per minute.

### Team Performance

- **teamname**: Name of the team.
- **teamid**: Unique identifier for the team.
- **result**: Outcome of the game (win/loss).
- **teamkills**: Total number of kills by the team.
- **teamdeaths**: Total number of deaths by the team.
- **firstdragon**: Indicates if the team secured the first dragon.
- **dragons**: Total number of dragons secured by the team.
- **opp_dragons**: Total number of dragons secured by the opposing team.
- **elementaldrakes**: Total number of elemental drakes secured.
- **opp_elementaldrakes**: Total number of elemental drakes secured by the opposing team.
- **infernals**: Number of infernal drakes secured.
- **mountains**: Number of mountain drakes secured.
- **clouds**: Number of cloud drakes secured.
- **oceans**: Number of ocean drakes secured.
- **chemtechs**: Number of chemtech drakes secured.
- **hextechs**: Number of hextech drakes secured.
- **dragons (type unknown)**: Number of dragons secured where the type is not specified.
- **elders**: Number of elder dragons secured.
- **opp_elders**: Number of elder dragons secured by the opposing team.
- **firstherald**: Indicates if the team secured the first Rift Herald.
- **heralds**: Total number of Rift Heralds secured.
- **opp_heralds**: Total number of Rift Heralds secured by the opposing team.
- **void_grubs**: Number of void grubs secured.
- **opp_void_grubs**: Number of void grubs secured by the opposing team.
- **firstbaron**: Indicates if the team secured the first Baron Nashor.
- **barons**: Total number of Baron Nashors secured.
- **opp_barons**: Total number of Baron Nashors secured by the opposing team.
- **firsttower**: Indicates if the team secured the first tower.
- **towers**: Total number of towers destroyed.
- **opp_towers**: Total number of towers destroyed by the opposing team.
- **firstmidtower**: Indicates if the team secured the first mid-lane tower.
- **firsttothreetowers**: Indicates if the team was the first to destroy three towers.
- **turretplates**: Number of turret plates destroyed.
- **opp_turretplates**: Number of turret plates destroyed by the opposing team.
- **inhibitors**: Total number of inhibitors destroyed.
- **opp_inhibitors**: Total number of inhibitors destroyed by the opposing team.

# Step 2.1
### Data Cleaning Steps

#### Replacing Missing Values
- **Step:** Replaced any missing values with `NaN` using `df.replace('', np.nan, inplace=True)`.
- **Effect:** This step ensures that any missing or empty values are properly represented as `NaN`

#### Converting Date Columns
- **Step:** Converted the 'date' column to datetime format using `pd.to_datetime(df['date'], errors='coerce')`.
- **Effect:** This step ensures that the 'date' column is in a proper datetime format, allowing for easier manipulation and extraction of date-related info

#### Creating New Columns
- **Step:** Created a new column 'year' by extracting the year from the 'date' column using `df['year'] = df['date'].dt.year`.
- **Effect:** This step adds a new column that contains the year of each match, which can be useful for understanding that all of these events happened within quick succession when compared to other studies.

# Step 2.2
### Univariate Analysis

### Distribution of Kills by Jungle Players

This plot shows how kills are distributed among jungle players, helping to identify the top-performing players in this role.

### Distribution of Total Kills by Teams

This plot shows the total kills by each team, helping to identify the best-performing teams in terms of kills.

# Step 2.3
### Bivariate Analysis

### Scatter Plot: Jungle Kills vs. Total Team Kills

This scatter plot shows the relationship between the total kills achieved by jungle players and the total kills achieved by their respective teams.

**Interpretation:** The plot reveals a positive correlation between jungle kills and total team kills. Teams with higher total kills tend to have jungle players who achieve higher kill counts. This suggests that the performance of jungle players significantly contributes to the overall success of their teams in terms of kills.

### Box Plot: Jungle Assists vs. Total Team Assists

This box plot compares the distribution of assists achieved by jungle players with the total assists achieved by their respective teams.

**Interpretation:** The plot shows that jungle players contribute a significant portion of the total assists for their teams. Teams with higher total assists tend to have jungle players who achieve higher assist counts. This indicates that the performance of jungle players in terms of assists also correlates with the overall success of their teams.

The bivariate analysis of the relationships between jungle kills and total team kills, as well as jungle assists and total team assists, suggests a strong correlation between the performance of jungle players and the overall success of their teams. Teams with higher total kills and assists tend to have jungle players who perform exceptionally well in these metrics, indicating that the best jungle players do correlate with the best-performing teams.

# Step 2.4
## Two uses for this data:
### Identifying Key Roles

This analysis helps identify which positions are most important to a team's success. For example, if jungle players consistently have high kills and assists, we can see their impact on the team's performance.

### Strategic Insights

Teams can use these insights to strategize and allocate resources effectively. Knowing which positions contribute most to kills and assists can help in training and focusing on key players.

# Step 2.5
### Imputation Technique

#### Mean Imputation for Numerical Columns
Mean imputation helps maintain the overall distribution of the data without introducing significant bias.

#### Mode Imputation for Categorical Columns
Mode imputation is suitable for categorical data as it preserves the most common category.

### Significance

Imputation ensures that missing values do not affect the analysis. It allows for a complete dataset, enabling accurate and reliable statistical analysis. And by using mean and mode imputation, we maintain the overall distribution and integrity of the data.

# Step 3
### Prediction Problem

**Type:** Regression

**Response Variable:** The response variable we are predicting is the total number of kills by a team in a match. We chose this variable because it is a key performance indicator in esports matches, reflecting the team's success.

### Evaluation Metric

**Metric:** Mean Absolute Error (MAE)

MAE is straightforward as it represents the average absolute difference between the predicted and actual values.Unlike Mean Squared Error (MSE), MAE is less sensitive to outliers. This is important in esports data, where extreme values like really high or low kill counts can occur.

**Features Used:**
- **Player Statistics:** Kills, deaths, assists, gold earned, damage dealt, damage taken, vision score, CS (creep score). These features are known at the time of prediction and directly influence the team's performance in terms of kills.
- **Team Statistics:** Total kills, deaths, assists, gold earned, damage dealt, objectives taken (towers, dragons, barons). Aggregated team statistics provide context on the team's overall performance and strategy.
- **Game Context:** Game duration, patch version, league, split, playoffs. Information such as game duration and patch version helps account for a lot of important variations that will add value to our comparisons.

**Training Data:**
- The model will be trained using historical match data, including player and team statistics from previous matches. This data is available before the prediction time and provides a comprehensive view of factors influencing team performance.
- The model will not use any information that would not be available at the time of prediction.

# Step 4
## Model Type: Linear Regression

### Features:

Kills (Quantitative)
Assists (Quantitative)
Team Name (Nominal)
Target Variable: Total Team Kills (teamkills)

### Feature Encoding
Quantitative Features: Kills and Assists will be left as-is but scaled using StandardScaler.
Nominal Features: Team Name will be encoded using OneHotEncoder.

### Steps in the Pipeline
Imputation: Handle missing values using SimpleImputer.
Scaling: Standardize numerical features using StandardScaler.
Encoding: Encode categorical features using OneHotEncoder.
Model Training: Train a Linear Regression model.

### Conclusion
In the context of predicting total team kills in esports matches, an MAE of 5.32 means that, on average, the model's predictions are off by about 5 kills, which is a lot in terms of League of Legends games where kills are usually in the 1-20 range. This means our model is not "good" in this context.

# Step 5
### New Features

- **Kill Participation (KP):** This feature represents the sum of kills and assists, normalized by the total team kills. It provides insight into a player's involvement in team fights.
- **Damage Per Minute (DPM):** This feature represents the damage dealt by a player per minute. It provides insight into a player's damage output efficiency.

### Hyperparameters to Tune

- **Alpha (Ridge Regression):** Regularization strength to prevent overfitting.
- **Max Depth (Decision Tree):** Maximum depth of the tree to control model complexity.

### Features and Their Importance

- **Kills and Assists:** Quantitative features representing direct contributions to team performance.
- **Team Name:** Nominal feature representing the team, encoded using `OneHotEncoder`.
- **Kill Participation (KP):** Quantitative feature representing player involvement in team fights.
- **Damage Per Minute (DPM):** Quantitative feature representing damage output efficiency.

These features are chosen because they provide a comprehensive view of player performance and team dynamics, which are crucial for predicting total team kills.

### Modeling Algorithm: Ridge Regression

**Reason:** Ridge regression helps prevent overfitting by adding a regularization term to the loss function.

### Hyperparameters Tuned

- **Alpha:** Regularization strength to control model complexity and prevent overfitting.

### Method for Hyperparameter Tuning: GridSearchCV

**Reason:** GridSearchCV performs an exhaustive search over a specified parameter grid, using cross-validation to evaluate model performance.

### Conclusion

Our MAE is now 4, which is lower than before. Since we have less error, we have improved on our baseline model.