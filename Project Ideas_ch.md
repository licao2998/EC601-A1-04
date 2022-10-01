# Project Ideas

## 数据集获取与数据压缩

**数据集简介**

The dataset is downloaded from kaggle.

The data is splitted into test data(32G) and train data16G (Hold-Out). 

- train_data.csv - 每个 customer_ID 具有多个日期的训练数据
- train_labels.csv - 每个 customer_ID 的目标标签
- test_data.csv - 对应的测试数据；您的目标是预测每个 customer_ID 的目标标签
- sample_submission.csv - 格式正确的示例提交文件

**数据压缩**

由于数据集原始数据集文件较大（50GB左右），直接进行读取并进行分析并不可取。在进行送入模型进行之前可以考虑对数据值进行压缩，具体的压缩方法包括

- 将数据集中的类别字段，使用Pandas的category进行代替；
- 将数据集中的数值字段，使用flaoat16和float32代替原始的float64；
- 将数据集使用feather或者parquet格式进行存储；

[https://www.kaggle.com/code/abdellatifsassioui/create-pickeld-data-from-50-gb-to-6gb](https://www.kaggle.com/code/abdellatifsassioui/create-pickeld-data-from-50-gb-to-6gb)

Parquet是一种与语言无关的列式存储文件类型，可以适配多种计算框架。Parquet是一种二进制文件，其中包含了各种针对其内容的元数据。在无需读取与解析文件内容的情况下，可以仅依靠元数据来确定文件中的列名称、压缩/编码方式、数据类型、乃至一些基本的统计类信息。经过转换的数据可以直接下载，压缩之后文件大小11GB左右。

[Amex Competition Data in Parquet Format](https://www.kaggle.com/datasets/odins0n/amex-parquet)

**可以将数据集压缩到总共5GB左右**

[create pickeld data (from 50 gb to 6gb)](https://www.kaggle.com/code/abdellatifsassioui/create-pickeld-data-from-50-gb-to-6gb)

## 数据预处理（Data reprocessing）和特征工程（feature engineering）：

数据集的每列有csutomer_ID, date, 各种features, 我们要根据这些得出每个customer_ID未来还款的概率。特征确实很多而且进行了脱敏处理(Data masking)，不太能通过现实的想法进行特征组合。特征工程（Feature Engineering）是将原始数据转化成更好的表达问题本质的特征的过程，使得将这些特征运用到预测模型中能提高对不可见数据的模型预测精度。

特征工程简单讲就是发现对因变量y有明显影响作用的特征，通常称自变量x为特征，特征工程的目的是发现重要特征。 feature engineering is manually designing what the input x’s should be. you have to turn your inputs into things the algorithm can understand.如何能够分解和聚合原始数据，以更好的表达问题的本质？这是做特征工程的目的。特征工程是数据挖掘模型开发中最耗时、最重要的一步。

处理数据缺失值（Data leakage）

标签分布中违约用户占比较少，类别分布比较均衡

![Untitled](Project%20Ideas%20e85b0031d2b54d35b260d0d36850e809/Untitled.png)

[https://cloud.tencent.com/developer/article/2042296](https://cloud.tencent.com/developer/article/2042296)

**按照业务意义来分**，可以分成5类，拖欠的变量，支出的变量，付款的变量，平衡的变量，以及风险变量，**可以进行分类后的变量的可视化(Data visulization)**

- D_* = Delinquency variables
- S_* = Spend variables
- P_* = Payment variables
- B_* = Balance variables
- R_* = Risk variables

![Untitled](Project%20Ideas%20e85b0031d2b54d35b260d0d36850e809/Untitled%201.png)

[https://cloud.tencent.com/developer/article/2042296](https://cloud.tencent.com/developer/article/2042296)

**按照变量属性来分**，可以分成三类，**ID类型(1个)，数值型(178)，类别型(11个)**, 总共190个特征。对于ID类型的特征，无法训练模型，数值型特征可以做一些聚合特征，或者特征衍生，类别型特征需要做label encoding。按照category变量对numerical变量做聚集形成新变量，使用用户历史时序数据进行特征抽取。

![Untitled](Project%20Ideas%20e85b0031d2b54d35b260d0d36850e809/Untitled%202.png)

Figure from daishu, [https://www.kaggle.com/competitions/amex-default-prediction/discussion/348111](https://www.kaggle.com/competitions/amex-default-prediction/discussion/348111)

## 模型建立与参数调整

评估指标 𝑀 是排名排序的两个度量的平均值：归一化基尼系数 𝐺 和 4% 的违约率 𝐷组成：

![Untitled](Project%20Ideas%20e85b0031d2b54d35b260d0d36850e809/Untitled%203.png)

[https://www.kaggle.com/code/inversion/amex-competition-metric-python](https://www.kaggle.com/code/inversion/amex-competition-metric-python)

### 模型选择

**树模型（LGBM, XGBoost, Catboost ...)**

****深度学习(CNN，transformer)****

主要需要调整网络结构

[[Kaggle参赛经验|数据分析|机器学习] American Express - Default Prediction比赛经历--预测信用卡违约概率](https://www.cnblogs.com/xiayee/p/16625071.html)

上面这篇里面有讲模型的建立

**调参**

几乎所有的机器学习算法都包括一些超参数，也叫做调整参数。这些参数和常规参数不同，它们不是模型的一部分，不会在模型拟合中被自动调整。它们是在另外的步骤中被调整的。一些超参数的例子，包括在岭回归和lasso回归中的正则项lambda、支持向量机中的C项、基于树的算法中树的数量（如，随机森林、梯度提升机）。

1、网格搜索 

2、随机搜索 

3、基于梯度的优化 

4、贝叶斯优化

[Kaggle大赛：债务违约预测冠军作品解析](https://cloud.tencent.com/developer/article/1135401?from=article.detail.2042296)

## 模型集成：

基于oof进行数据的集成（ensemble）
