# Forest-cover-type-
杭电/数据挖掘/森林预测/Kaggle
![build](https://img.shields.io/badge/build-passing-success)
![build](https://img.shields.io/badge/python-v3.7-ff68b4)
![build](https://img.shields.io/badge/django-v3.0.4-blueviolet)
![build](https://img.shields.io/badge/license-GPL-blue)

本项目来源于Kaggle上的一道赛题——Forest-cover-type，根据当地现有的生态条件来预测可能生长的不同森林类型。该项目主要任务是要根据给定的Covertype Data Set数据集，使用不同的数据分类方法，预测森林类型，并计算不同分类方法下的准确率。

本项目分为两部分。第一部分首先对数据进行处理，通过偏度分析、直方图分析、箱型图分析、计算person相关系数等方法，对数据特征提取（降维至44维度），此外又与采用传统的PCA降维方式（手动将数据降维至44维）对数据进行处理。第二部分选择KNN、决策树、随机森林的算法对上述三种数据结果进行样本训练（训练集70%，测试集30%），发现特征提取的准确率最高。第三部分，在对数据特征提取的基础上，又加入了逻辑回归、XGBoost、神经网络的算法进行准确率的计算（SVM方法运行时间过长，因此淘汰）。最终发现KNN的效果最好。第四部分是KNN的调参以期达到更好的结果，最终实现了96.86%的准确率。

![首页](homepage.png)
![可视化分析](visualize.png)

## 目录
- [易企|僵尸企业分类系统](#易企僵尸企业分类系统)
  - [目录](#目录)
  - [安装](#安装)
    - [赛题数据](#赛题数据)
    - [依赖](#依赖)
  - [使用](#使用)
    - [机器学习部分](#机器学习部分)
    - [Web端](#web端)
  - [项目整体结构](#项目整体结构)
  - [参考](#参考)
  - [License](#license)

## 安装
### 赛题数据
[下载](http://www.fwwb.org.cn/attached/file/20200103/20200103095031_187.rar)

### 依赖
- Python >= 3.7
- Pandas >= 1.0.0
- Numpy >= 1.17.0
- joblib >= 0.14.1
- Scikit-learn >= 0.22.1
- matplotlib >= 3.1.2
- xgboost >= 1.0.2
- Django >= 3.0.4
- PyEcharts >= 1.7.1

## 使用
### 机器学习部分
data_merge.ipynb是将企业提供的训练集和验证集合并以重新划分，data_process.ipynb是数据预处理与特征工程，data_train.ipynb包含了网格搜索参数调优与多模型加权投票融合，遗传算法确定权重，data_iter.ipynb是数据融合，CompanyClassifier.ipynb包含了最终封装好的企业分类模型。详细内容请参考项目技术文档。

### Web端
进入webclassifier目录下，命令行运行：
```shell
python manage.py runserver
```
访问localhost:8000即可。

## 项目整体结构


## 参考
- 2020年第十一届中国大学生服务外包创新创业大赛：http://www.fwwb.org.cn/news/show/278
- 邹蕴涵. 我国僵尸企业的判别, 影响及对策建议[J]. 中国物价, 2016 (7): 80-82.
- 李霄阳, 瞿强. 中国僵尸企业: 识别与分类[J]. 国际金融研究, 2017, 364(8): 3-13.
- 黄少卿, 陈彦. 中国僵尸企业的分布特征与分类处置[J]. 中国工业经济, 2017, 3: 24-43.
- 周琎, 冼国明, 明秀南. 僵尸企业的识别与预警—来自中国上市公司的证据[J]. 财经研究, 2018, 44(4): 130-142.
- 栾甫贵, 刘梅. 僵尸企业僵尸指数的构建及应用研究[J]. 经济与管理研究, 2018 (6): 12.

## License
[GPL](https://github.com/huangyifei212/Forest-cover-type-/blob/master/LICENSE) &copy; [Yofei212](https://github.com/huangyifei212)
