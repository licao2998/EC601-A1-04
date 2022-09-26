# American Express

[American Express - Default Prediction](https://www.kaggle.com/competitions/amex-default-prediction)

# Sprint 1

- Define your product mission
- Define your users
- Comprehensive literature review (build on project 1)
- Define User Stories
- Define MVP and MVP user stories
- Technologies to evaluate and reason for choosing them
- Setup of development environment
- Next Sprint goals

## Product mission

Credit cards are very important in people's daily lives because of their convenience and low interest rates. With the increase in credit card users, credit card risk control has become challenging for banks and financial institutions like American Express. They need to weigh the benefits and risks brought by the credit card business, and the task of predicting credit card defaults, consumption and repayment of users has become one of the effective ways to monitor credit card risks. For banks, if they can determine in advance that customers will default and take adequate measures to remind customers to make timely repayments, such as taking personalized email or message reminders to urge customers to make repayments, they can reduce the default ratio of customers and promote the development of the bank's credit card business. In contrast, banks can analyze the characteristics of credit card default users and pay more careful attention to customers with these characteristics. The bank can analyze the characteristics of credit card defaulters, pay more careful attention to customers with these characteristics, restrict the credit card limit or even freeze their credit card spending when necessary.

Currently, the traditional method of credit card default prediction is to manually define the relevant rules and directly classify the data for prediction, which has the advantages of simplicity and strong interpretation. However, such methods have the following shortcomings: first, they require a large amount of expert domain knowledge, which is costly in terms of human resources and highly dependent on the correctness of domain knowledge, and highly subjective. Secondly, the generalization ability is weak, as the rules are domain-specific, and the rules between different domains are generally not applicable to each other.

Therefore, the prediction can be combined with machine learning techniques to overcome the shortcomings of strong reliance on manual labour. **In this project, the basic idea of machine learning-based default prediction is to adjust the parameters using different models in machine learning to improve the model's prediction effect and generalization ability.** The prediction is a classification task. It uses various data related to a user's credit card history as data set features, such as spending amount and repayment amount in different months, to predict whether a user will default in a future period. 

## Users

Banks

(Insurance company)

Credit cards users

## User Stories

## MVP and MVP user stories

- Technologies to evaluate and reason for choosing them
- Setup of development environment
- Next Sprint goals

## Literature Review

User credit card default prediction tasks include credit card spending prediction, payment prediction, and other tasks. Many scholars did research on the machine learning approach to credit card default research is to build a credit scoring model to predict whether a user will default in the future based on past credit history, personal information and whether the user has defaulted. As early as 1999, Brause et al. proposed combining association rules and neural networks to predict credit card fraud [1]. In 2018, Mohamad Jeragh and Mousa Alsulaimi investigated a novel unsupervised learning model based on a combination of autoencoder and support vector machine (OSVM), which also improved the results [2]. Florentin Butare et al. based on Logistic Regression, Decision Tree and Random Forest for predicting user credit card data from different banks and concluded that different machine learning models are suitable for different banks' credit card default prediction tasks [3]. Jianping Cai et al. proposed a differential privacy-based weighted SVM algorithm for predicting credit card repayments and defaults, while the algorithm can fully protect the user's privacy [4].

## References

[1] Brause R, Langsdorf T, Hepp M. Neural data mining for credit card fraud detection. Tools with Artificial Intelligence, 1999. Proceedings. 11th IEEE International Conference on 1999：103-106.

[2] Jeragh M, Alsulaimi M. Combining Auto Encoders and One Class Support Vectors Machine for Fraudulent Credit Card Transactions Detection. 2018 Second World Conference on Smart Trends in Systems, Security and Sustainability (WorldS4), London, England：2018: 178-184.

[3] Butaru F, Chen Q, Clark B, et al. Risk and risk management in the credit card industry [J]. Journal of

Banking & Finance, 2016,72:218-239.

[4] Cai J, Liu X, Wu Y. SVM Learning for default prediction of credit card under differential Privacy. PPML, 2020: 51-53.
