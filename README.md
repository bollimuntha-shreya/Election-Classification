# ELECTION - CLASSIFICATION
Precog - Elections Recruitment Task
The dataset is from the url: https://lokdhaba.ashoka.edu.in/browse-data?et=GE&st=all&an=16


## Directory Structure

```text

├── README.md
├── Paper Reading Task
     ├── readme.md 
├── All_States_GE.csv           # CSV file - dataset
├── Elections_Analysis.ipynb
├── Elections_Binary_Classification.ipynb              
|── Elections_Multiclass_Classification.ipynb                       
```



## About the Code

The code is written in Python on a Jupyter Notebook, and it uses the following libraries:

- `pandas`: To form the dataframe and perform operations on them
- `numpy`: To execute mathematical operations on the data
- `sklearn`: To implement the various classification models and their evaluation metrics
- `matplotlib`: To plot the graphs and visualise the data.

Run the jupyter notebook.

## Analysis

### Data Preprocessing

The following steps are performed to preprocess the data:

- Remove irrelevant columns
- Drop rows with Candidates named "NOTA"
- Drop the duplicate rows
- Considering the data of only Lok Sabha General Elections - Year 2019


### Insight 1 : Gender Distribution
It is observed that majority of the candidates are males. This shows unequal representation of the country.

### Insight 2 : Party Type
Most of the candidates contesting do not belong to any party. They are independent contestants.
Further, the local party contestants are more in the general elections as compared to the National or State Based parties.

### Insight 3 : Education Level
- 50% of the candidates are either 10th pass, 12 pass or Graduates.
- Almost 50% of the candidates have an education level of Graduates or greater.

## Binary Classification


### Data Preprocessing

The following steps are performed to preprocess the data:

- Remove irrelevant columns.
- Drop rows with Candidates named "NOTA".
- Drop the duplicate rows.
- Specific columns are considered 'State_Name', 'Constituency_Type', 'Year', 'Turnout_Percentage', 'Party_Type_TCPD', 'Vote_Share_Percentage','Sex','Position','Constituency_No'.
- The strings (State Names and Constituency Type) are mapped to integers.

### Correlation Matrix
 The correlation matrix provides us with a correlation between the featuers of the data which help us set a classification problem.

### Classification
Classification Problem:  Predicting the Election Winner's Gender

#### Data Split
Using sklearn train test split  of the data was done in 80 : 20 ratio

#### 1. Logistic Regression
Accuracy of logistic regression classifier on test set: 0.95

#### 2. Naive Bayes
Accuracy of naive bayes classifier on test set: 0.91

#### 3.k-Nearest Neighbors
Accuracy of knn classifier on test set:0.94

#### 4.Decision Tree
Accuracy of decision tree classifier on test set: 0.90

#### 5.Random Forest
Accuracy of random forest classifier on test set: 0.94

It is seen that all the ML models have nearly the same accuracy. However, Logistic Regression has consistently performed better.

### Insight 1 : Gender Representation Over Time
* By analyzing the data from multiple elections, we can determine the overall trend of gender representation in politics over the years. We can plot the percentage of male and female candidates who contested in each election and observe how it changes with time. This insight provides us valuable information about the progress of gender equality in politics and whether there are any noticeable shifts in the participation and winning of female candidates.

### Insight 2 : Impact of Constituency Type on Gender Representation
* Different constituencies are classified as General, Scheduled Castes (SC), or Scheduled Tribes (ST). We can examine whether there are any significant variations in the gender representation of winning candidates across these different constituency types. It is possible that certain constituencies may have a higher or lower representation of female candidates, and understanding these patterns can shed light on the factors influencing gender diversity in politics.

## Multiclass Classification
Classification Problem : Predicting the Winning Party in General Elections
### Data Preprocessing

The following steps are performed to preprocess the data:

- Remove irrelevant columns.
- Drop rows with Candidates named "NOTA".
- Drop the duplicate rows.
- Specific columns are considered 'State_Name', 'Constituency_No', 'Year', 'Turnout_Percentage', 'Party_Type_TCPD', 'Vote_Share_Percentage'.
- The strings (State Names and Constituency Type) are mapped to integers.

### Correlation Matrix
 The correlation matrix provides us with a correlation between the featuers of the data which help us set a classification problem.

### Classification
Classification Problem:  Predicting the Election Winner's Gender

#### Data Split
Using sklearn train test split  of the data was done in 80 : 20 ratio


#### 1. Logistic Regression
Accuracy of logistic regression classifier on test set: 0.62

#### 2. Naive Bayes
Accuracy of naive bayes classifier on test set: 0.65

#### 3. k-Nearest Neighbors
Accuracy of knn classifier on test set:0.64 

#### 4.Decision Tree
Accuracy of decision tree classifier on test set: 0.74

It is seen that the accuracy of Decision Tree is far better than the rest.

### Insight 1 : Winning Party Predictions
* Using historical data of general elections conducted since 1962 till 2019, the classification problem predicts the winning party in a given constituency. The Graph for the winning party (Actual vs predicted) across all constituencies is given.

### Insight 2 : Swing Regions
* The misclassified instances in the classification problem can provide insights into swing regions, where the winning party is not as predictable.Identifying such regions can be essential for political strategists and parties to focus their campaign efforts and resources more effectively.

### Insight 3 : Party Dominance
* The classification model can reveal which political parties have been consistently dominant in specific regions or constituencies over time. 
* This insight can be crucial for understanding the political landscape and identifying strongholds of particular parties.

