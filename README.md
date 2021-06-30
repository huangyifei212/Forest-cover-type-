# Forest-cover-type-
![build](https://img.shields.io/badge/build-passing-success)
![build](https://img.shields.io/badge/python-v3.7-ff68b4)
![build](https://img.shields.io/badge/license-GPL-blue)

本项目来源于Kaggle上的一道赛题——Forest-cover-type，根据当地现有的生态条件来预测可能生长的不同森林类型。该项目主要任务是要根据给定的Covertype Data Set数据集，使用不同的数据分类方法，预测森林类型，并计算不同分类方法下的准确率。

本项目分为两部分。第一部分首先对数据进行处理，通过偏度分析、直方图分析、箱型图分析、计算person相关系数等方法，对数据特征提取（降维至44维度），此外又与采用传统的PCA降维方式（手动将数据降维至44维）对数据进行处理。第二部分选择KNN、决策树、随机森林的算法对上述三种数据结果进行样本训练（训练集70%，测试集30%），发现特征提取的准确率最高。第三部分，在对数据特征提取的基础上，又加入了逻辑回归、XGBoost、神经网络的算法进行准确率的计算（SVM方法运行时间过长，因此淘汰）。最终发现KNN的效果最好。第四部分是KNN的调参以期达到更好的结果，最终实现了96.86%的准确率。


## 目录
- [Foster-cover-type](#Foster-cover-type)
  - [目录](#目录)
  - [安装](#安装)
    - [赛题数据](#赛题数据)
    - [依赖](#依赖)
  - [使用](#使用)
    - [数据分析](#数据分析)
    - [特征提取 VS PAC降维](#特征提取 VS PAC降维)
    - [KNN调参](#KNN调参)
  - [项目整体结构](#项目整体结构)
  - [参考](#参考)
  - [License](#license)

## 安装
### 赛题数据
[下载](数据源:http://archive.ics.uci.edu/ml/datasets/Covertype)
或者直接从covtpye.date处下载即可。

### 依赖
- Python == 3.7
- Pandas == 0.24.2
- Numpy == 1.19.4
- scikit-learn == 0.21.3
- scipy == 1.3.1
- seaborn == 0.9.0
- matplotlib == 3.1.1
- xgboost == 1.3.1


## 使用
### 数据分析
数据分析_checkpoint.ipynb是将原始数据进行展示后又将大数据分割成几个较小的数据集进行数据可视化及分析工程，PCA降维后三种分类的准确率_cheackpoint.ipynb的前一部分是进行PCA降维代码与最终维度选取展示工程。详细内容请参考森林预测.pdf文档。

### 特征提取 VS PAC降维
首先在KNN-checkpoint.ipynb、决策树-checkpoint.ipynb、随机森林-checkpoint.ipynb三个工程里得到了未进行特征提取和特征提取后的准确率对比，同时在PCA降维后三种分类的准确率-checkpoint.ipynb工程的后半部分对以上三种算法进行了PCA降维后的准确率计算，相当于6组数据进行对比，采用特征提取后的数据进行后续运算。

### 六种算法比较
分别对提取特征后的数据再进行逻辑回归、XGBoost、神经网络、SVM进行准确率计算，对应工程在SVM 逻辑回归 XGBOOST-checkpoint.ipynb、NeuralNetworks-checkpoint.ipynb中，安装好相关依赖和数据路径即可运行。

### KNN调参
KNN调参_checkpoint是在KNN基础上对算法的参数进行调整以期达到更好的效果，通过确定k值、weight值以及P值，得到最终的准确率为96.86%

## 项目整体结构


## 参考
- GENG Li-juan, LI Xing-yi. 用于大数据分类的KNN算法研究[J]. 计算机应用研究, 2014, 31(005):1342-1344,1373.
- 周志华. 机器学习. 清华大学出版社, 2016.
- 韩家炜, 坎伯. 数据挖掘: 概念与技术. Vol. 2. No. 007. 机械工业出版社, 2012.
- 曹正凤. 随机森林算法优化研究[D]. 首都经济贸易大学.
- Chen, Tianqi, and Carlos Guestrin. "Xgboost: A scalable tree boosting system." Proceedings of the 22nd acm sigkdd international conference on knowledge discovery and data mining. ACM, 2016.
- Xgboost developers. "XGBoost Documentation."
https://xgboost.readthedocs.io/en/latest/.


## License
[GPL](https://github.com/huangyifei212/Forest-cover-type-/blob/master/LICENSE) &copy; [Yofei212](https://github.com/huangyifei212)
