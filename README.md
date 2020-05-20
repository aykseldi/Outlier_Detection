# Outlier Detection and Game Outcome Prediction
 In this project, we analyze the NBA (National Basketball Association) statistics data for predicting the **game outcome and detecting outliers**.
 1. **Outlier Detection**
    Our aim is finding the players which break apart from ordinary or standard ones. Our outlier dataset variables are greater than one (1) so we focus on multivariate outliers.
    A. **Analyzing Dataset**
    The dataset is formed from 5 different parts. These are;
    
        * Statistics of players in regular season (19113 records), 
        *  Statistics in playoff season (7544 records), 
        * Statistics in all-star season (1463 records), 
        * Statistics in playoff career (2055 records) and 
        * Statistic in regular season career (3760 records).
        
    In data exploration, there are 19 features in each dataset and **3 of them are nominal**. These features are **player’s id, name and last name** so these nominal features are not taken into consideration throughout analysis. The remaining features are scaled into 0 to 1 in order to standardize independent variables. 
    
     Furthermore in data preparation stage, other features in the dataset was comprised of sums of all scores so in order to **avoid  most  played player to be a natural outlier, we divide all the scores of players into match played**.
 /***    
|__Average Formula__  |     
|-------------|------------|------------|
| Number of Scores   |
| --------------------------------------|   
| Number of Games Played   
***/

In the case of dimensionality reduction on player_playoff_career data, PCA (Principal Component Analysis) is applied. Because PCA takes lower dimensional set of features from a higher dimensional dataset while capturing as much information as possible. For PCA results of Playoff career dataset is shown below.



/***
| __PCA__ | __Variance__ | __Cumulative Variance__ |
|-------------|------------|------------|
| PCA1        | 0.502874     | 50.29    |
| PCA2         | 0.192634  | 69.55      |
| PCA3    | 0.126686 | 82.22 |
| PCA4        | 0.0461349  | 86.83     |
| PCA5    | 0.0338315 | 90.21|
| PCA6         | 0.0235394  | 92.56 |
| PCA7    | 0.0223254 | 94.79 |
| PCA8         | 0.0169766 | 96.49     |
| PCA9    | 0.0149214| 97.98 |
***/

