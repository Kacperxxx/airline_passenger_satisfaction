# Airline passenger satisfaction

## Project description

The purpose of this project is to predict whether a passenger is satisfied or not with the airline service. 
To predict the satisfaction of the passenger, we use the following machine learning algorithms:
- Logistic Regression
- K-Nearest Neighbors
- Decision Tree Classifier
- Naive Bayes Classifier
- Neural Network

The prediction are done using the following steps:

- Data Preprocessing
- Data Visualization
- Feature Selection
- Model Building
- Model Evaluation
- Model Comparison

The following features are used:

- gender
- customer type
- age
- type of travel
- class of travel
- flight distance
- inflight Wi-Fi service
- departure/arrival time convenient
- ease of online booking
- gate location
- food and drink quality
- online boarding possibility
- seat comfort
- inflight entertainment
- onboard service quality
- check-in service quality
- baggage handling quality
- cleanliness
- departure delays
- arrival delays


## Dataset description
The dataset is taken from Kaggle. 
The dataset contains 129880 examples.
It is divided into two parts: training set and test set in the ratio 80:20 respectively.

link to the dataset: https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction


### Data Preprocessing

The following steps are performed in the data preprocessing phase:
- In 'Arrival Delay in Minutes' column was 393 values with NaN. These values were replaced with the median of the column.
- Changed 'satifaction' column values from 'neutral or dissatisfied' to 0 and from 'satisfied' to 1.
- 'Gender' column also changed to 0 and 1 for Male and Female respectively.
- 'Customer Type' column changed to 0 and 1 for Loyal Customer and disloyal Customer respectively.
- 'Type of Travel' column changed to 0 and 1 for Personal Travel and Business Travel respectively.
- 'Class' column changed to 0, 1 and 2 for Eco Plus, Business and Eco respectively.
- 'satisfaction' column moved to the last column of the dataset.


### Data Visualization

The following plots are used for data visualization:
- Countplot - to show the number of satisfied and dissatisfied passengers by gender, seat comfort, inflight Wi-Fi service,
            Departure/Arrival time convenient, on-board service, ease of online booking, food and drink, inflight service,
            cleanliness, inflight entertainment, leg room service, baggage handling, checkin service
- Countplot - to show the number of satisfied and dissatisfied passengers by type of travel.
            We can see 69% is Business travellers and they are much more satisfied with the flight than the personal travellers.
- Countplot - to show the number of satisfied and dissatisfied passengers by class of travel.
            Business class travellers make up 47 % of the total and they are the most satisfied. But most of Eco Class travellers are very dissatisfied
- Bar plot - to show the number of satisfied and dissatisfied passengers by average age.
- We have also plotted the correlation matrix to see the correlation between the features. 
        From the plots we see that Age and gate location do not affect customer satisfaction so we also drop them.
- In the scatter plot we can see that the most satisfied passengers are those who decide on long distance flights which
        are not delayed.

### Model Building

Before building the models, we use StandardScaler to scale the data.

#### Logistic Regression
Using Logistic Regression we get the following results:
    - Accuracy: 0.87384
    - Precision: 0.87344
    - Recall: 0.86951
    - F1 score: 0.87118

#### K-Nearest Neighbors
To find the best value for K we use GridSearchCV. The best value for K is 5.
Using K-Nearest Neighbors we get the following results:
    - Accuracy: 0.92785
    - Precision: 0.93137
    - Recall: 0.92266
    - F1 score: 0.92602

#### Decision Tree Classifier
Using Decision Tree Classifier we get the following results:
    - Accuracy: 0.94248
    - Precision: 0.94147
    - Recall: 0.94166
    - F1 score: 0.94157

#### Naive Bayes Classifier
Using Naive Bayes Classifier we get the following results:
    - Accuracy: 0.86629
    - Precision: 0.86635
    - Recall: 0.861162
    - F1 score: 0.86325

#### Neural Network
Using Neural Network we get the following results:
    - Accuracy: 0.95357
    - Precision: 0.95527
    - Recall: 0.95055
    - F1 score: 0.95259


### Conclusion
The best results in terms of F1-score were obtained using a neural network. 
The naive Bayesian classifier is the worst in this respect, 
with an F1-score of approximately 0.86; two-class logistic regression is also close to this result, 
with an F1-score of approximately 0.87. It is worth noting that both accuracy, 
precision, recall and F1-score in the neural network do not have a result below 0.95 in any of these metrics.
