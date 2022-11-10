# Predicting-patient-stay-length
Predicting length of Stay of patients in hospitals as a part of Kaggle competition using Ensemble models like Random Forest and XGBoost 

The world has succumbed to the strain COVID-19 pandemic has had on healthcare, such has shortage of beds and hospital resources. Incorporating latest data mining technologies into the healthcare system will exponentially mitigate these concerns. This paper presents the key methodologies used to predict the Length of Stay (LOS) of each patient, on a case-by-case basis that supports multiple applications in the medical field. The comparison of different models and analysis of the accuracy and precision obtained using each of these models concluded K-Nearest Neighbors as the most optimal model for the dataset used. The dataset introduction, key predicting models and challenges faced in implementation are introduced in detail.

## Exploratory Data Analysis

![image](https://user-images.githubusercontent.com/89947247/200999409-bc29f45b-c294-48ba-8122-cf3352a511e0.png)

The descriptor in the dataset gives the details of the patients admitted to the hospital. The challenge to tackle is to apply regression on non-numerical values of the descriptors. Therefore, we convert this value to an absolute numerical value. To do that, firstly we find the upper and lower bound these descriptors in our dataset. Then we convert the categorical data to numeric value.

Then we perform an analysis on all the numerical data to check the skewness of the data and based on the histogram generated, many columns were found to be right skewed (Fig.3.1.2). By this we can know which columns are not normally distributed. The skewness value can be either of these: positive, negative or undefined. When the skewness is 0, data is perfectly symmetrical. If the skewness is less than -1 or greater than 1, the graph is found to be highly skewed. If the skewness identified is anywhere between -1 and -0.5 or between 0.5 and 1, the graph is moderately skewed. And if the skewness is between -0.5 and 0.5, the graph is said to be symmetric. So, these columns must be transformed into normal distributions (Fig.3.1.3).

![image](https://user-images.githubusercontent.com/89947247/200999743-74660b5c-ac67-4aa9-a037-450bb7b6b790.png)

![image](https://user-images.githubusercontent.com/89947247/200999821-edf33114-b748-4fe1-a68e-2a985aef0442.png)

## Data Pre-processing

(1) Handling missing data:
In the dataset used, there are few descriptors which has null values. To handle and solve this challenge data imputing is done. Since the data is skewed, we consider the mode value to replace these missing values and drop the ones which exist initially.

(2) Removing outliers and handling the skewness:
When working on datasets, one of the crucial steps is to deal with outliers as they can significantly distort a statistical model. Some values in the dataset may have values that are distinguishably varying from most of the other values which are called the outliers. It is usually an anomaly that can adversely affect the accuracy of a model. One of the simplest ways to identify outliers is by visualizing them using boxplots. We perform log transformations on columns which are highly right skewed (Fig.3.2.1) and remove the outliers on the train and test dataset.

(3) Standardizing the dataset:
The data is standardized when one or more attributes are rescaled such that their mean value is 0 and standard deviation is 1.

## Feature Selection
In the process of data cleaning, feature selection plays an important role by reducing the dimensionality of the predictive model. By reducing the number of features, we yield a model with high performance and low computational cost. We drop some unused columns which are redundant with similar information and are corelated to one another, thus obtain a dataset which is linearly independent using the Variable Importance Plots (VIP) and cross verified with Random Forest feature selection. The graph below depicts the most contributing features in the dataset.

![image](https://user-images.githubusercontent.com/89947247/201000076-31153874-057c-43a0-8266-3ef5d593184c.png)

## Methodologies:
For our dataset we applied all these models after cleaning the data and selecting important features for training the model. For linear regression, Random Forest, K-Nearest Neighbors, Bagged Decision Trees, Gradient Boosting and AdaBoost we achieved accuracy of about 30.14%, 41.11%, 58.09%, 35.7%, 40.91% and 37.28% respectively, for predicting the length of stay of a particular patient in the hospital.

## Results:
After implementing Linear Regression, Random Forest, Adaptive boosting, Bagged Decision Tree, Gradient boosting, and K-Nearest Neighbors algorithms, the highest accuracy is obtained for K-Nearest Neighbors (KNN) algorithm with an accuracy of 58.09%.

![image](https://user-images.githubusercontent.com/89947247/201000286-04c9ab7a-2e80-44c6-8b0b-3aebc56c0ea2.png)

## Conclusion:
By performing the exploratory data analysis, we can get a better understanding of the variables in the data and the trends. By imputing the mode values, the null values are handled, and the skewness is fixed by removing the outliers. Data is then wrangled to find the importance of each feature. Finally, by selecting the important features, the data is trained against multiple machine learning algorithms and the model built using KNN algorithm is the most optimal model obtained to accurately predict the Length of Stay of patients in the hospital.

There is no pre-defined way to perform data pre-processing. Data imputation is one among the various ways to handle missing data and removing outliers is one among the numerous methods to deal the skewness in data. Thus, by opting different methods lead to different prediction results, especially when the data is highly skewed as in our case, and when there are too many null values which remains a major challenge.
