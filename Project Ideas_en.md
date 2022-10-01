# Project Ideas

## Dataset Acquisition and Data Compression

**Intoduction to dataset**

The dataset is downloaded from kaggle.

The data is splitted into test data(32G) and train data16G (Hold-Out). 

- train_data.csv - the train data for every customer_ID
- train_labels.csv - labels of evrery customer_ID
- test_data.csv - test data, the target is to predict the label of every customer_ID
- sample_submission.csv - submission format

**Data Compression**

Due to the large file size of the original dataset (around 50 GB), it is not advisable to read and analyze the data directly. Compression of the data values can be considered before feeding into the model, and specific compression methods include

- Replacing the category field in the dataset with category from Pandas.
- Taking the numeric fields in the dataset and using flaoat16 and float32 instead of the original float64.
- storing the dataset using feather or parquet format.

[https://www.kaggle.com/code/abdellatifsassioui/create-pickeld-data-from-50-gb-to-6gb](https://www.kaggle.com/code/abdellatifsassioui/create-pickeld-data-from-50-gb-to-6gb)

Parquet is a language-independent columnar storage file type that can be adapted to a variety of computational frameworks, and is a binary file that contains various metadata about its contents. The metadata alone can be used to determine the column names, compression/encoding methods, data types, and even some basic statistical information in the file without having to read and parse the contents. The converted data can be downloaded directly, and the compressed file size is about 11GB.

[Amex Competition Data in Parquet Format](https://www.kaggle.com/datasets/odins0n/amex-parquet)

The dataset can be compressed to about 6GB

[create pickeld data (from 50 gb to 6gb)](https://www.kaggle.com/code/abdellatifsassioui/create-pickeld-data-from-50-gb-to-6gb)

## Data Preprocessing and Feature Engineering）：

Each column of the dataset has csutomer_ID, date, various features, and we want to derive the probability of future repayment for each customer_ID based on these. The features are really large and desensitized (Data masking), and it is not quite possible to combine features by realistic ideas. Feature Engineering is the process of transforming raw data into features that better express the nature of the problem, allowing the application of these features to predictive models to improve the accuracy of model predictions on invisible data.

Feature engineering is simply the discovery of features that have a significant effect on the dependent variable y, usually referred to as the independent variable x. The purpose of feature engineering is to discover important features. feature engineering is manually designing what the input x's should be. you have to turn your inputs into things the algorithm can understand. How can you decompose and aggregate raw data to better represent the nature of the problem? This is the purpose of doing feature engineering. Feature engineering is the most time consuming and important step in data mining model development.

Label distribution has a small percentage of defaulting users and a relatively balanced category distribution

![Untitled](Project%20Ideas%2085d62f64f9b5443280f3b110095bee19/Untitled.png)

[https://cloud.tencent.com/developer/article/2042296](https://cloud.tencent.com/developer/article/2042296)

**According to the business meaning**, it can be divided into 5 categories: variables of arrears, variables of expenses, variables of payments, variables of balance, and variables of risk, and the **data visualization of the classified variables can be performed.**

- D_* = Delinquency variables
- S_* = Spend variables
- P_* = Payment variables
- B_* = Balance variables
- R_* = Risk variables

![Untitled](Project%20Ideas%2085d62f64f9b5443280f3b110095bee19/Untitled%201.png)

[https://cloud.tencent.com/developer/article/2042296](https://cloud.tencent.com/developer/article/2042296)

**According to the attributes of the variables,** they can be divided into three categories, **ID type (1), numerical type (178), and category type (11), totaling 190 features.** For ID type features, it is impossible to train the model, numerical features can do some aggregation features, or feature derivation, and category type features need to do label encoding.

![Untitled](Project%20Ideas%2085d62f64f9b5443280f3b110095bee19/Untitled%202.png)

Figure from daishu, [https://www.kaggle.com/competitions/amex-default-prediction/discussion/348111](https://www.kaggle.com/competitions/amex-default-prediction/discussion/348111)

## Model Building and Parameter Adjustment

The assessment metric 𝑀 is the average of two metrics ranked in order: the normalized Gini coefficient 𝐺 and the 4% default rate 𝐷 consisting of.

![Untitled](Project%20Ideas%2085d62f64f9b5443280f3b110095bee19/Untitled%203.png)

[https://www.kaggle.com/code/inversion/amex-competition-metric-python](https://www.kaggle.com/code/inversion/amex-competition-metric-python)

### Choosing the Classification Model

**Tree Model（LGBM, XGBoost, Catboost ...)**

****Deep Learning(CNN，transformer)****

Adjust the grid structure

[[Kaggle参赛经验|数据分析|机器学习] American Express - Default Prediction比赛经历--预测信用卡违约概率](https://www.cnblogs.com/xiayee/p/16625071.html)

The building of the model is introduced above, but it is in Chinese 😅

**Parameter Adjustment**

Almost all machine learning algorithms include some hyperparameters, also called tuning parameters. These parameters are different from the regular parameters in that they are not part of the model and are not automatically tuned in the model fitting. They are adjusted in a separate step. Some examples of hyperparameters include the regular term lambda in ridge regression and lasso regression, the C term in support vector machines, and the number of trees in tree-based algorithms (e.g., random forests, gradient boosters).

1, grid search

2、Random search

3、Gradient-based optimization

4、Bayesian optimization

[Kaggle大赛：债务违约预测冠军作品解析](https://cloud.tencent.com/developer/article/1135401?from=article.detail.2042296)

## Model integration.

Integration of data based on oof (ensemble)
