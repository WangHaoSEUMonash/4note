# note
# 百面机器学习
## 第2章 模型评估
### 01 评估指标的局限性
#### 问题1：准确率的局限性
准确率是指分类正确的样本占总样本个数的比例。

缺陷：当不同类别的样本比例非常不均衡时，占比大的类别往往成为影响准确率的最主要因素。为了解决这个问题，可以使用更为有效的平均准确率（每个类别下的样本准确率的算术平均）作为模型评估的指标。

#### 问题2：精确率(precision)和召回率(recall)的权衡
$\color{red}{精确率}$是指分类正确的正样本个数占分类器判定为正样本的样本个数的比例。$\color{red}{召回率}$是指分类正确的正样本个数占真正的正样本个数的比例。

Precision值和Recall值是既矛盾又统一的两个指标，为了提高Precision值，分类器需要尽量在“更有把握”时才把样本预测为正样本，但此时往往会因为过于保守而漏掉很多“没有把握”的正样本，导致Recall值降低。

![avatar](.\pr.png  =300x200)

$\color{red}{F1 score}$是精准率和召回率的调和平均值，它定义为
$F1=\frac{2\times precision\times recall}{precision+recall}$

### 02 ROC曲线
#### 问题1：什么是ROC曲线

ROC曲线是Receiver Operating Characteristic Curve的简称，中文名为“受试者工作特征曲线”。ROC曲线的横坐标为$\color{red}{假阳性率}   （False Positive Rate，FPR）；纵坐标为$\color{red}{真阳性率}（True Positive Rate，TPR）。

$FPR=\frac{FP}{N}$

$TPR=\frac{TP}{P}$

TP是P个正样本中被分类器预测为正样本的个数，FP是N个负样本中被分类器预测为正样本的个数。
