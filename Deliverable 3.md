## MSCS 634 – Data Mining Project

### Deliverable 3: Classification, Clustering, and Pattern Mining

1. Dataset Summary

The Bank Marketing Dataset is a dataset from UCI Machine Learning Repository. It includes 17 original attributes, such as customer demographics, financial data, and information about marketing campaigns, with 45,211 records. The target variable (y) shows whether a customer had taken up a term deposit. Classification, clustering and association rule mining were conducted on the dataset.

2. Classification and Hyperparameter Tuning

Decision Tree and K-Nearest Neighbors (KNN) classifiers were developed to predict term deposit subscriptions. Numerical features were standardized, categorical variables were encoded, and the dataset was divided into 80% training and 20% testing data.

GridSearchCV with three-fold cross-validation was used to optimize the Decision Tree. The best parameters were a maximum depth of 10, minimum samples split of 10, and minimum samples leaf of 1.

The original Decision Tree achieved 89.27% accuracy, an F1-score of 0.2445, and ROC AUC of 0.7055. KNN achieved 88.78% accuracy, an F1-score of 0.2985, and ROC AUC of 0.7032. The Tuned Decision Tree achieved 89.11% accuracy, an F1-score of 0.3212, and ROC AUC of 0.7215.

Best Model: The Tuned Decision Tree demonstrated the best overall performance based on F1-score and ROC AUC. However, its subscriber recall was only 22%, indicating difficulty identifying actual subscribers.

3. Clustering Analysis

Age, account balance, campaign contacts and previous contacts were used as the features for K-Means clustering. There were three clusters of customers.

The previously contacted customers in Cluster 0 were 8221, with an average age of 40.77 and an account balance of 1513.10. The younger customers who were in Cluster 1 numbered 22426 with the average age of 34.03 years and lower average balance of 905.46. Cluster 2 comprised 14,564 older customers, with an average age of 51.66 years and a higher average balance of 1980.55 and more contacts of the customers from the campaign.

The PCA visualization demonstrated partial separation of the clusters, which suggested that there were differences in the characteristics of the customers that could be used to segment them.

4. Association Rule Mining

The Apriori algorithm discovered 360 frequent itemsets with a minimum support of 0.02. The association rules were extracted with a minimum confidence of 0.50 and lift of more than 1.

The strongest association shown was between primary education and blue-collar employment and housing loans. The rule is supported by 5.86%, has a 68% confidence level, and a lift of 3.16, indicating a positive association between these attributes.

5. Challenges and Solutions

Challenge 1: Class Imbalance

The data set was imbalanced, with many more non-subscribers than subscribers, making it hard to predict the minority class.

Solution: F1-score, ROC AUC, and confusion matrices were used alongside accuracy to evaluate classification performance.

Challenge 2: Hyperparameter Selection

It was difficult to choose appropriate parameters for the Decision Tree due to the impact of the complexity of the model on prediction performance.

Solution: GridSearchCV with three-fold cross-validation was applied to identify the optimal parameter combination.

Challenge 3: Customer Segmentation

It was difficult to identify meaningful customer groups based on more than one numerical attribute.

Solution: K-Means clustering and PCA visualization were used to identify and interpret three customer segments.

6. Key Insights

After hyperparameter tuning, the Tuned Decision Tree outperformed the others in terms of classification with a higher F1-score and ROC AUC. However, it had low subscriber recall, indicating a need for further improvements.

K-Means has identified three customer segments with distinct demographic and financial attributes. Apriori identified interesting correlations and patterns between customer characteristics. Taken together, these techniques provided insights into customer behaviour and marketing trends.

7. Practical Applications

Banks may be able to use classification models to differentiate which customers are likely to sign up for a term deposit. Customer segmentation techniques using clustering might be useful to create tailored marketing approaches and relationships between customer demographics and their financial characteristics could be discerned by association rules.

This data can help inform campaign planning, customer engagement, data driven marketing decisions, etc. But the models that predict and the found connections need to be tested before they can be put into practice.

8. Conclusion

The Bank Marketing Dataset was used to perform classification, hyperparameter tuning, clustering, and association rule mining, and these were successfully implemented in Deliverable 3. The Tuned Decision Tree outperformed the other classifiers in classification, and the K-Means and Apriori classifiers uncovered customer segments and relationships among attributes.

Class balancing, more feature engineering, and further model optimization can be improved in the future to improve the accuracy of the prediction of the subscription.