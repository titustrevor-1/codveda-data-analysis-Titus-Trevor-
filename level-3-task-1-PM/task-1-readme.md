
## Aim

To construct and analyse models to predict if a customer is going to churn. Data should be prepared and several models investigated. The most suitable model can then be further refined using a grid search.
## Data

This relates to a phone firm and includes details for each customer including which phone plan they are on, their phone usage and the number of times they have contacted customer services.

- churn-bigml-80.csv (training set) – 2666 customers
- churn-bigml-20.csv (test set) – 667 customers

Around 14.6% of customers in the training set churned.
## Process

I imported and renamed the training and test sets.
I converted Yes/No variables to 1s and 0s.
State and area code variables were converted to 0/1 format (one hot encoding).
Numerical data was standardised using StandardScaler.
Logistic Regression, Decision Tree and Random Forest models were constructed.

These were analysed for accuracy, precision, recall and F1-score.

Grid search was used to refine the Random Forest.
The confusion matrix was analysed and key variables identified.
## Results
Model	Accuracy	Precision	Recall	F1-score
Logistic Regression	0.855	0.477	0.221	0.302
Decision Tree	0.930	0.755	0.747	0.751
Random Forest	0.940	0.982	0.589	0.737
Refined Random Forest	0.955	0.874	0.800	0.835
Optimal grid search values were: 200 trees, unlimited tree depth, minimum leaf size of 1 and balanced class weights.
Explanation of results
Accuracy – the proportion of correct predictions.
Precision – the proportion of customers predicted to churn that in fact do churn.
Recall – the proportion of actual churning customers that were correctly predicted.
F1-score – a score that combines both precision and recall.
## Graphs
Model performance
[Model comparison]
Confusion matrix for refined Random Forest
[Confusion Matrix]
Key variables
[Feature importance]
## Key results
The refined Random Forest performed best. It achieved an F1-score of 0.835 and an accuracy of 0.955.
However, a high accuracy can be deceptive. Although the Logistic Regression achieved a reasonable accuracy of 0.855, it only successfully identified around 22% (recall = 0.221) of those that actually churned. In fact, a model that predicted that no customers churned would also be correct 85% of the time.
Although the un-refined Random Forest was highly precise (0.982), it failed to recognise many churners. As a result, it only recognised 0.589 (around 4 in every 10) of actual churners.
Grid search was beneficial. It improved the F1-score (to 0.835 from 0.737) and increased recall (to 0.800 from 0.589). By increasing the weighting given to churners, the model successfully recognised significantly more of these. However, this slightly reduced the models precision (to 0.874 from 0.982).
Analysis of the refined model’s confusion matrix demonstrates that of the 95 actual churners, 76 were recognised and 19 were not. Of the 572 non-churners, just 11 were incorrectly labelled as churners.
Most key variables were number of customer service contacts, total daytime charges and total daytime minutes. The model places the greatest emphasis on these variables.
## Constraints

Only around 14.6% of customers actually churned meaning that the data is skewed.
Whilst the graph highlights key variables, it does not reveal if having more (or less) of these increases (or reduces) a customer’s likelihood to churn.
Total daytime charge and total daytime minutes contain highly similar information as charge is related to minutes.
As only one test set was analysed, results could vary slightly for different sets of new customers.
## Software

Python, pandas, scikit-learn and matplotlib.