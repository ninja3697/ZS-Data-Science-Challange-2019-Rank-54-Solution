# ZS-Data-Science-Challange-2019-Rank-54-Solution
Competition Link: https://www.interviewbit.com/contest/zs-yds-2019/

- **Problem Description** :

The task was to predict whether the shot taken by Cristiano Ronaldo would end up in goal or not. The dataset of Ronaldo&#39;s attempts on the goal.

- **Data Files:** Data.csv

- **Evaluation Metric** :

  Score= 1 / (1 + MAE) where MAE = Mean Absolute Error

- **Data Prep:**
  - Quality checks performed / Errors found:

    I looked for missing values and outliers (through descriptive stats and univariate analysis). There were many missing in all columns except match\_id and team\_id columns. Some features do not contribute to the predictions, so they are removed. These are: Match\_event\_id, team\_name, date\_of\_game, lat/lng and team\_id.
    
    - The missing values in shot\_id\_number are filled by interpolation.
    - The missing values in distance\_of\_shot are filled by the medians of classes of feature  shot\_basics and range\_of\_shot in the respective record.
    - The missing values in location\_x and location\_y is filled by the medians of the corresponding classes of feature &#39;area\_of\_shot&#39;
    - The missing values in  power\_of\_shot is filled by the medians of the corresponding classes of features &#39;type\_of\_shot&#39; and &#39;type\_of\_combined\_shot&#39;
    - Other missing values are filled by mapping their other features values to get similar row and pick the value from there.
  
  - Data preprocessing steps:
    The feature &#39;distance\_of\_shot&#39; is transformed on log scale to remove possible outliers.

- **EDA:**
  - Feature generation:

  The features I generated are as follows:

  &#39;Home&#39;, &#39;1996-97&#39;, &#39;1997-98&#39;, &#39;1998-99&#39;, &#39;1999-00&#39;, &#39;2000-01&#39;, &#39;2001-02&#39;, &#39;2002-03&#39;,  &#39;2003-04&#39;, &#39;2004-05&#39;, &#39;2005-06&#39;, &#39;2006-07&#39;, &#39;2007-08&#39;, &#39;2008-09&#39;, &#39;2009-10&#39;, &#39;2010-11&#39;, &#39;2011-12&#39;, &#39;2012-13&#39;, &#39;2013-14&#39;, &#39;2014-15&#39;, &#39;2015-16&#39;, &#39;Goal Area&#39;, &#39;Goal Line&#39;, &#39;Left Corner&#39;, &#39;Mid Ground Line&#39;, &#39;Mid Range&#39;, &#39;Penalty Spot&#39;, &#39;Right Corner&#39;, &#39;shot - 0&#39;, &#39;shot - 1&#39;, &#39;shot - 10&#39;, &#39;shot - 11&#39;, &#39;shot - 12&#39;, &#39;shot - 13&#39;, &#39;shot - 14&#39;, &#39;shot - 15&#39;, &#39;shot - 16&#39;, &#39;shot - 17&#39;, &#39;shot - 18&#39;, &#39;shot - 19&#39;, &#39;shot - 2&#39;, &#39;shot - 20&#39;, &#39;shot - 21&#39;, &#39;shot - 22&#39;, &#39;shot - 23&#39;, &#39;shot - 24&#39;, &#39;shot - 25&#39;, &#39;shot - 26&#39;, &#39;shot - 27&#39;, &#39;shot - 28&#39;, &#39;shot - 29&#39;, &#39;shot - 3&#39;, &#39;shot - 30&#39;, &#39;shot - 31&#39;, &#39;shot - 32&#39;, &#39;shot - 33&#39;, &#39;shot - 34&#39;, &#39;shot - 35&#39;, &#39;shot - 36&#39;, &#39;shot - 37&#39;, &#39;shot - 38&#39;, &#39;shot - 39&#39;, &#39;shot - 4&#39;, &#39;shot - 40&#39;, &#39;shot - 41&#39;, &#39;shot - 42&#39;, &#39;shot - 43&#39;, &#39;shot - 44&#39;, &#39;shot - 45&#39;, &#39;shot - 46&#39;, &#39;shot - 47&#39;, &#39;shot - 48&#39;, &#39;shot - 49&#39;, &#39;shot - 5&#39;, &#39;shot - 50&#39;, &#39;shot - 51&#39;, &#39;shot - 52&#39;, &#39;shot - 53&#39;, &#39;shot - 54&#39;, &#39;shot - 55&#39;,&#39;shot - 56&#39;, &#39;shot - 6&#39;, &#39;shot - 7&#39;, &#39;shot - 8&#39;, &#39;shot - 9&#39;, &#39;c\_shot - 0&#39;, &#39;c\_shot - 1&#39;, &#39;c\_shot - 2&#39;, &#39;c\_shot - 3&#39;, &#39;c\_shot - 4&#39; and &#39;c\_shot - 5&#39;.

  All the above features are generated to represent the categorical variables in the dataset into numerical variables. This is required because the model used by me do not accept categorical variables.

- **Model building** :
  - Model Choice: I started with Logistic Regression model for this problem because the given problem is a binary classification problem with many features (more than 20) and each feature is contributing to the final prediction.

- **Conclusion** :
  - For this problem and similar binary classification problems, the Logistic Regression model predict a good result without much complexity and taking many factors in account. Always process the data, fill missing values and remove outliers and make the data suitable for logit and you will be good to go.
