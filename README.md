# Transactions-Fraud-Detection
Machine Learning Application with R (Random Forest, Decision Tree, Logistic Regression)

Executive Summary (All the tables and figures are shown in the pdf file)
[Fraud Detection Report.pdf](https://github.com/EvanaZhang/Transactions-Fraud-Detection/files/9805107/Fraud.Detection.Report.pdf)


Business Problem

Many financial institutions have seen a 35% YoY increase in transaction fraud because of the not very good economic situation since the pandemic happens. This project will include three models (a logistic regression model, a decision tree model, and a random forest model) to detect fraud between transactions, and provide with recommendations and build a profile of how different features (variables) impact the fraud happens.
According to the “Data Analysis” part, I believe that the number of days since the account was created, different email domain of the transactors, and the adjustment of USD $ value to the transaction are more likely having more fraud than other features/variables. Therefore, comparing to billing postal code variable, email domain of transaction (email_domain) is more important to detect the fraud.


Key Findings

• After analyzing all the results, email_domain is an important predictor. However, by looking at the correlation plot, it seems that there’s no significant relationship between billing postal and event_label. Therefore, billing postal could also be an essential predictor but not as important as email_domain.
• The USD $ value of the transaction will be a path to detect fraud.
• As the measure of the historic USD $ amount used to purchase goods and services increases, the more fraud will be detected. 
• On the false positive rate, when score > threshold of 6%:


Model type
(Please check detailed analysis in pdf file)


Model Performance Summary & Interpretation

This dataset has total 27 variables which includes 7 numeric variables, 20 character variables. The first step is to remove some of the variables that might not be very relevant or meaningless for further analysis. Next, transforming the target variable, “event_label” into dummy values of 1 (fraud) and 0 (legit). After that, converting the billing city code variable to a variable called “city_freq_count” and convert the email_domain variable to “domain_pct_fraud” by using frequency encoding because they both are high cardinality variables.
The final step before the partition target variable “event_label” to a factor before building the models. By comparing all the models, the random forest model has the highest accuracy and area under ROC curve (AUC)
which means the logistic regression model returns more relevant results and it is the best model for fitting the given dataset and also for prediction. (Anlaysis will be shown in the “Compare All the Models”)


Recommendation

• The financial institution should consider to implement a long-term plan to mainly focus on different features of transaction email domain to avoid a high rate of fraud happens.
• According to my model, the longer number of days since the account was created, the high rate of detecting fraud. The company should consider to start from the old users and check whether the fraud rate of old users is higher than that of new users.
• The company could also alter the limit of amount of transactions or numbers of transaction a customer can make to avoid high USD dollar value transaction causing high rate of detecting fraud.


