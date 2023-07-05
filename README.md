# Bank-Marketing-Campaign-Classification
---
## Business Problem Understanding
**`Context`**

Bank A is a financial institution that provides various financial products and services. One financial product that is well known to the public is a time deposit. The mechanism of a time deposit is that the customer deposits a certain amount of money in a bank or financial institution, and the money can only be taken after a certain period of time. As compensation, the customer will be given a fixed interest rate according to the amount of money deposited.

However, as a business entity that has its own financial products and customers, banks still have to compete in order not to lose customers. One way to do this is through marketing campaigns.

**`Problem Statement`**

Marketing campaigns can be wasteful of time and resources if the bank targets all customers without filtering them out. This is because if the marketing campaign is targeted to all customers, the time and money will be wasted if the customers will not deposit. 

With this, the bank's marketing team wants to improve the efficiency of the marketing campaign by knowing which customers have a high chance of depositing so that the time and resources used can be more efficient.

**`Goals`**

Among many bank customers, it would take a lot of time and money to manually select customers who have a high potential to deposit. Therefore, the bank's marketing team would like to have the ability to predict the possibility that a customer will deposit or not to make the marketing campaign run more efficiently.

In addition, they also want to know what factors make customers want to deposit or not. By doing so, they can plan a much better way to approach these customers.

**`Analytic Approach`**

Based on the problem, we will analyze the data to find patterns that distinguish customers who will deposit and those who will not.

We will then create a classification model that will help banks predict the probability that a customer will deposit or not.

The purpose of this classification is basically to help banks optimize their marketing efforts in a more effective way.

The specific objectives of doing this classification include the following.

1. `Identify potential target markets`</p>
    By analyzing existing customer data, classification can help identify groups of customers who have a high propensity to make deposits. This allows banks to focus on target markets that have high potential to generate more revenue.

1. `Development of an appropriate marketing strategyt`</p>
    By understanding the characteristics and needs of customers who are likely to make deposits, companies can develop more appropriate and relevant marketing strategies. For example, they can customize their marketing messages, communication channels or product offerings to suit the needs and preferences of potential customers.

1. `More efficient resource management`</p>
    With good classification, banks can allocate their resources more efficiently. They can reduce unnecessary costs and effort in marketing their products or services to customers who have a low propensity to deposit. Instead, they can focus their marketing efforts on customers who are more likely to deposit, generating better results using the minimum available resources.

**`Metric Evaluation`**

Target :
* 0 : Customer `not deposit`
* 1 : Customer `deposit`

Type Error:
* FP (False Positive) : Customer was predicted to deposit but did not</p>
    FP Consequences: Time and resources spent on the customer will be wasted.

* FN (False Negative) : Customer was predicted not to deposit but did deposit</p>
    FN Consequences: The bank will lose the opportunity to be able to benefit from customers who can actually deposit

Consequently, recall and precision are important in this case so we will use F-Score metrics. Note that the main goal of the bank's marketing campaign is to attract more customers to deposit. Therefore, we will build a model that can predict as many true positive classes as possible and as few false positive and false negative predictions as possible.

Then, our priority will be aimed at reducing False Negative so that the bank does not lose the opportunity to get depositing customers. Since False Negative is the priority, the recall of the model will be prioritized to be improved. Therefore, the F-Score `metrics` used is `F2-Score`.

---
## Conclusion

1. With an accuracy of 60.3%, the model is still not good when used to predict both classes (deposit and non-deposit customers). This happens because of the trade-off between recall and precision. Because we focus on increasing the correct predictions for customers who will deposit, the correct predictions for customers who do not deposit will decrease. The error rate on the model used is 39.7%.

1. With a Sensitivity of around 89.9%, the model created is fairly good if used to predict the positive class (depositing customers).

1. With Specificity around 31.7%, the model is very bad if it is used to predict the negative class (customers who will not deposit).

1. With an F2-Score of about 80.2%, the model created is fairly good if used to predict customers who will deposit and not deposit by prioritizing the positive class (customers who make deposits).

The most important feature in the classification of customers who will deposit and who will not deposit is the contact_other feature (the last type of communication made to the customer other than celullar and telephone) followed by the poutcome_success feature (the result of the customer's last successful marketing campaign). 

In addition, according to [thefinancialbrand.com](https://thefinancialbrand.com/news/bank-marketing/bank-marketing-budgets-advertising-roi-strategy-88835/), if the cost of a bank's marketing campaign is $1 and the total time spent on marketing per customer is 5 minutes then : 
1. Without using machine learning model (all customers are assumed to be interested in depositing)

    Based on the confusion matrix, if all customers are assumed to be interested then there are 1465 total customers and there are only 718 people who are interested in depositing, then:
    * Total cost spent: 1465 x $1 = $1465
    * Loss of : (1465 - 718) x $1 = $747
    * Total time spent: 1465 x 5 = 7325 minutes or approximately 122.08 hours
  
2. Using machine learning model (based on confusion matrix: 646 predicted correct deposit and 510 predicted deposit but not deposit)

    Based on the confusion matrix, if there are 1156 customers who are predicted to deposit and there are only 646 people who are predicted to deposit correctly, then:
    * Total cost spent: 1156 x $1 = $1156
    * Loss of : (1156 - 646) x $1 = $510
    * Total time spent: 1156 x 5 = 5780 minutes or approximately 96.33 hours

Therefore, the bank has saved approximately (747 - 510) = $237 in marketing costs or in other words, reduced marketing losses by 31.7%. In addition, the bank can also save about (122.08 - 96.33) = 25.75 hours or reduce the time used to contact each customer by about 21.09%.

---
## Recommendation

Things that can be done to develop the project and model to make it better in the future are as follows.
* Other data on feature contact should be made more specific. By making the data from the contact feature more specific besides cellular and telephone (for example: email, whatsapp, facebook, or other platforms) so that the information that can be obtained for the most important features in the classification of determining whether a customer will deposit or not can be clearer and better.
* Adding new data/features such as marketing costs for each customer and the profit earned from marketing by each customer. With this we can do further analysis regarding the efficiency of marketing done to customers. We can also use this data to calculate profits if we use the model that has been created. 
* Increase the data from the bank itself so that the predictions made can be better.
* Using a wider hyperparameter space to find the best hyperparameter if we still use the Adaboost model.
---
PPT Slide link can be accessed [here](https://www.canva.com/design/DAFly_7VLhY/hkq7xcELBnH5rbi84fYocA/view?utm_content=DAFly_7VLhY&utm_campaign=designshare&utm_medium=link&utm_source=publishsharelink)
