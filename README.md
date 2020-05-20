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
