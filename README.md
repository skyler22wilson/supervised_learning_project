# machine_learning_project-supervised-learning

## Project Goal
My goal for this project was to gain a better undertstanding of the end-to-end process of developing an accurate machine learning model to make predictions on real life data. Additionally I wanted to get a better grasp on hyperparameter tuning and transforming featurs to enhance my models
### Challenges:
I decided to use two machine leanring models that are computationally expensive, so using GridSearchCV to find the optimal model took an extremly long time. Additionally, I noticed that the data used was right-skewed heavily, while i was able to transform a couple features, some i was unable to transform properly
### Project Workflow:
1. Performed EDA on the data set, this inluded:
    - checked the mean values between the two outcomes to see if there were meaningful differences
    - Dealing with values that did not make empiracl sense such as an insulin level of 0, I decided to split the data by outcomes and then use imputation with means rather than applyying the mean of the whole dataset so that i could capture even subtly differences between the two groups
    - before using imputation to more accurately reflect the data
    - Creating a heatmap to see if there was any correlation between the independant variables
    - Plotting the histogram for each feature to assess their distribution
    - Plotting boxplots for each feature to see if there were a lot of outliers in the data
    - Creating a pairplot to see if there were any interactions between the dependant variables
    - Compared the distributions of the dependent variables given the two different outcomes
2. Performed preprocessing, this included:
    - Used Z-scoring to filter outliers out of the data set. Outliers were considered to be 2.5 standard deviations from the mean
    - used square root transformation on DiabetesPedigreeFunction, Insulin, and Skinthickness to help fix right skewedness
    - Attempted other transformations of Age and pregnencies such as reciprocal and logorithmic but found that the results were subpar
    - Used StandardScaler to scale the data from -1, 1 
3. Created an initial Model and tuned the hyperparameters
    - Created an initial RandomForestClassifier and XGBoostClassifier model
    - Used a StratifiedKFold to cross-validate the hyperparameters
    - Used GridSearchCV to discover the optimal hyperparameters that yeild the most accurate model
    - Re-implemented the models with the optimal hyperparameters
4. Assessed the relative quality of the Models:
    - Used model assesment techniques such as accuracy score, recall, percision, F1 score, and a confusion matrix
    - Also used a classification report to put all of the results in a nice format
    - plotted the AUC score for each model as well
## Results: 
- I used accuracy_score, percision_score, recall_score, roc_auc_score, confusion_matrix and a classification_report to measure the quality of the perdictions in my model
- The Random Forest classifier performed slightly better with a higher accuracy and percision but the XGBoost algorithm had a better recal which is more important in the context of the dataset which is health related
