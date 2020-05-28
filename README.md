# OUTLIER DETECTION and Game Outcome Prediction
 In this project, we analyze the NBA (National Basketball Association) statistics data for predicting the **game outcome and detecting outliers**.
 1. **Outlier Detection**
 
    Our aim is finding the players which break apart from ordinary or standard ones. Our outlier dataset variables are greater than one (1) so we focus on multivariate outliers.
    
    A. **Analyzing Dataset**
    
    The dataset is formed from 5 different parts. These are;
    
        * Statistics of players in regular season (19113 records), 
        * Statistics in playoff season (7544 records), 
        * Statistics in all-star season (1463 records), 
        * Statistics in playoff career (2055 records) and 
        * Statistic in regular season career (3760 records).
        
    In data exploration, there are 19 features in each dataset and **3 of them are nominal**. These features are **player’s id, name and last name** so these nominal features are not taken into consideration throughout analysis. The remaining features are scaled into 0 to 1 in order to standardize independent variables. 
    
     Furthermore in data preparation stage, other features in the dataset was comprised of sums of all scores so in order to **avoid  most  played player to be a natural outlier, we divide all the scores of players into match played**.
 
In the case of dimensionality reduction on player_playoff_career data, PCA (Principal Component Analysis) is applied. Because PCA takes lower dimensional set of features from a higher dimensional dataset while capturing as much information as possible. For PCA results of Playoff career dataset is shown below.




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


*First 7 principle components captures nearly 95% of variance in dataset*.

  B.**Outlier Detection Alghorithms**
  
  Different outlier detection algorithms are used, these are;
 
  |  |Algorithm  Name |
------------ | -------------
 | 1. | Feature Bagging Outlier Detection|
 | 2. | Isolation Forest|
 | 3. | k-Nearest Neighbors Detector|
 | 4. | Cluster-based Local Outlier Detection|
 | 5. | Average K-NN |
 
 
   **Feature Bagging Detector**
      
   It fits a number of base detectors. It uses base estimator as Local Outlier Factor as default but other estimators such as k-NN or Angle Based Outlier Detector could be user.
   
   In playoff career dataset, there are 20 outliers and 2036 Inliers. Threshold value is **-0.7118109714421073**.
   
   In playoff season dataset, there are 33 outliers and 4430 inliers. Threshold value is **-6231948.694033984**.
   
   ![Feature Bagging](https://github.com/aykseldi/Outlier_Detection/tree/master/ML_Project/2.png?raw=true)
   
   **Isolation Forest**
   This method makes data partitioning by using a set of trees. It calculates an anomaly score examining how much isolated the point in the structure. The anomaly score is then used to identify outliers from normal observations. 
   
   In playoff career dataset there are 21 outliers and 2034 inliers. Threshold value is -0.14277197028200625.
   
   In playoff season  dataset there are 45 outliers and 4418 inliers. Threshold value is - - -0.1391610505888.
   
   ![Isolation Forest](https://github.com/aykseldi/Outlier_Detection/tree/master/ML_Project/isforest.png?raw=true)

   **K-Nearest Neighbors**
   
   The distance to its kth nearest neighbor could be viewed as the outlying score.
   
   In playoff career dataset, there are 16 outliers and 2039 inliers. Threshold value is -0.07808484312452174.
   
   In playoff season dataset there are 34 outliers and 4429 inliers. Threshold value is -0.05731006134932328.

   ![K-Nearest Neighbors](https://github.com/aykseldi/Outlier_Detection/tree/master/ML_Project/knn.png?raw=true)
   
   **Clustering Based Local Outlier**
   
   It classifies the data into small clusters and large clusters. The anomaly score is then calculated based on the size of the cluster the point belongs to, as well as the distance to the nearest large cluster. 
   
   In playoff career dataset, there are 21 outliers and 2034 inliers. Threshold value is -0.6599293211770738.
   
   In playoff season dataset, there are 45 outliers and 4418 inliers. Threshold value is -0.6953386755417442.

   ![K-Nearest Neighbors](https://github.com/aykseldi/Outlier_Detection/tree/master/ML_Project/1.png?raw=true)
   
   **Average K-NN**
   
   It uses the average of all k neighbors as the outlier score.
   
   In playoff career dataset, there are 10 outliers and 2045 inliers. Threshold value is -0.04585606196467415.
   
   In playoff season dataset, there are 7 outliers and 4456 inliers. Threshold value is -0.04706805441399679.
   
   ![Average K-NN](https://github.com/aykseldi/Outlier_Detection/tree/master/ML_Project/avg_knn.png?raw=true)
   
   We considered a comparison should be made with NBA official website data against our results and methods. In unsupervised learning there is no ground truth for the comparison of results. In order to tackle the issue, we decided to get Most Valued Players of year 2004 from NBA official website. These players are detected with the help of votes from fans, critical assessment of players’ performance on important matches and other factor like fair player and discipline on matches.It is showed in table below. 
