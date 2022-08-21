# California_Housing_Price_FY21
(project tasked by ML Professor)

## Goals / Objectives

Our California Housing dataset suggests the median housing prices for the year 1990 during which the U.S Census Bureau was responsible for housing data. In this report, we discover how well our model manages when the same data can be used to predict today’s median price for each block group. In doing so, the model can differentiate between different block groups, disseminate essential information to investors and predict concurrent datasets given the independent variables.

sklearn(Scikit Learn): to invoke the necessary libraries for complex data processing
pandas: performing basic IO operations with dataframing capabilities
NumPy: to perform complex mathematical operations on array datasets
Matplotlib: to plot visualizations for exploratory / predictive model building to define our data and build a model which can provide best accuracy to find housing prices for unseen data. The study involves the usage of regression techniques to predict continuous data from our dataset.

We will try to answer the following questions with context to our topic:
<ul>
<li>What is the inflation rate from 1990 to 2021?</li>
<li>Can we determine median housing price based on independent factors?</li>
<li>Is the change in California Housing prices following linear relationship?</li>
<li>Can we alter the data to reflect inflation costs since 1990?</li>
</ul>

## Data Description

California Housing Dataset has 20640 instances, 8 predictive attributes and the target predictor of numeric data type.

As observed in the following dataset abbreviations, these are the terminologies:
<ul>
<li>MedInc: median income in block</li>
<li>HouseAge: median house age in block</li>
<li>AveRooms: average number of rooms</li>
<li>AveBedrms: average number of bedrooms</li>
<li>Population: block population</li>
<li>AveOccup: average house occupancy</li>
<li>Latitude: house block latitude</li>
<li>Longitude: house block longitude</li>
</ul>

This dataset was derived from the 1990 U.S. census, using one row per census
block group. A block group is the smallest geographical unit for which the U.S.
Census Bureau publishes sample data (a block group typically has a population
of 600 to 3,000 people).

No missing data or NULL values found in this dataset. The target variable is the median house value for California districts.
We check for outlier data using the boxplot() by seaborn. The outlier data is the one that lies outside the lower & upper limits.
After dropping 5 records, dataset has 20635 instances
Based on the data collected in 2021, the median housing value is 791,000 or 7.91. We multiply the target values by 4.4 to fill the offset that we use to predict median housing prices in 2021.


## Proposed Model and Justification

The California Housing dataset calls for a regression model since the predictive and predictor variables are of numeric data type.
<br />	-We use StandardScaler, MinMaxScaler and RobustScaler, the scaling technique that produces the best score is used further.
<br />	-Implement Principal Component Analysis (PCA) on the scaled features to reduce dimensionality of data and prevent low scorers from feature selection. 
<br />	-Implement Polynomial Features as an alternative to PCA which will be defined in the second scenario.
<br />	-Once the features are scaled and filtered, records separated into training and testing subsets of dataset with each having their own independent and dependent  variables.
<br /> -After splitting the dataset into training and testing sets, apply the following regression techniques: Linear Regression, Lasso Regression, Ridge Regression, Decision Tree Regression, Random Forest Regression, Gradient Boost Regressor, MLP Regression.

Modelling aims has the following objectives:

<ul>
<li>Data we possess is not relevant and therefore must scale the dependent variable to reflect inflation.</li>
<li>Model should reduce dimensionality of data, prevent low scorers from feature selection, polishing record classifications with outlier data and pipelining multiple functions to reduce CPU time</li>
<ul>

<ul>
<li>Our regression model should evaluate multiple parameters in pursuit of best r2, RMSE and mean accuracy score.
<li>Datasets must be split into training and testing subsets of data with each having their own independent and dependent variables. Meanwhile, out of sample data taken from training set as validation set marks the overall scores.
</ul>


RESULTS INTERPRETATION AND IMPLICATIONS

Plots and Summary Tables

We see the results for the cumulative sum of variances of scaled features with respect to number of dimensions.

From the Explained Variance Ratio, we see that 
1st variable explains 0.83%
2nd variable explains 0.15%
3rd variable 0.01%
4th variable 0.01% of the total variance
which means that 0.01 is lost.

Best model we obtain from Prediction with PCA:

Best model Training R2 score: 57.85%
Best model Testing R2 score: 54.04%
Best RMSE score: 3.42
Best Average CV score: 0.55

Best model we obtain from Prediction with Polynomial Features:

Best model Training R2 score: 80.84%
Best model Testing R2 score: 78.42%
Best RMSE score: 2.34
Best Average CV score: 0.78

Assessment

-	The model appears valid and uses the common parameters to fit the target variable accurately. It then performs the testing predictions with good accuracy.
-	Although training r2 score is quite large for the models, testing r2 score is more valuable as it represents the dataset not fitted on.
-	Root mean square error defines the square root of the sum of squaring the difference between the actual and predicted values.
-	α parameter values define the regularization term weight associated with the model. Defining multiple parameter values increases chance of best mean accuracy score.
-	The best model can predict data for our testing set with a mean accuracy score of 65%
-	We can achieve a better score with Polynomial Features than PCA, therefore, the target variable could be defined into a polynomial function with predictive variables to a degree of 2.

OUT-OF-SAMPLE PREDICTIONS

Final Model Prediction on Out-of-Sample dataset

Our model can predict data for out-of-sample dataset with a mean accuracy score of 60%.

Training R2 score: 80.84%
Validation R2 score: 78.10%
Validation RMSE score 2.37
Average CV score: 0.79
 
## Concluding Remarks

-	Prediction: We can predict with adequate accuracy the median housing prices for year 2021
-	Outlier data: The dataset contains more outliers that caused the predictions to drop when removed
-	Insufficient data: More records are necessary achieve higher mean accuracy and reduce variance
-	Inconsistent data: Dataset used was published in 1990 and has been adjusted to reflect some inflation
