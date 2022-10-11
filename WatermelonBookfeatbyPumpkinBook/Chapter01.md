# 第一章：绪论

## 1.1 引言
一些high level的关于机器学习的介绍：
经验以data的方式存在，从data中学到的结果即model，从data中得到model使用的方法即 **learning algorithm**。
- 计算机科学：研究algorithm
- 机器学习：研究learning algorithm


## 1.2 基本术语
**Terminology**:
- dataset: set of instances/samples
- sample: fixed collection of feature/attirubute with their values.
- sample/attribute space: space used to describe a sample, and each attribute represents each axis.
- feature vector: one sample which represented in sample space

training/learning object: learn an hypothesis which close to ground-truth.

此处切瓜的举例是supervised learning，数据需要label。
- label -> lable space

**Task types:**

Samples whether have lables or not:
- supervised learning: classification, regression etc.
- unsupervised learning: clustering etc.

Prediction values' types:
- classification: prediction is discrete
	- binary classification: positive and negative class
	- multi-calss classification
- regression: prediction is continuous


- generalization: albility of model that suits new samples.
- iid: independent and identically distributed, we assume our samples are independently collected from a data distribution.

## 1.3 假设空间
- induction: 归纳, a generalization from special to general. Learning from samples is **inductive learning**.
- deduction: 演绎, a specialization from general to special
- 广义的归纳学习：从样例中学习
- 狭义的归纳学习：从训练数据中学得concept，又称概念学习
- version space: hypothesis space matches with the training set.

## 1.4 归纳偏好
- inductive bias: 归纳偏好, feature selection based on training data analysis or special knowledge.
- Occam's razor: 奥卡姆剃刀原则，chosse the samplest/smoothest hypothesis which matches the observation.
- No Free Lunch Theorem: the expetations of two learning algorithms for uniform distribution dara are same. 

```
脱离具体问题，空切谈论什么学习方法更好，毫无意义。
如果要考虑所有潜在问题，则所有的学习算法一样好。
如果要谈算法的相对优劣，就需要针对具体的学习问题。
在一些问题上表现的好的learning algorithm，在另一些问题上可能并不好，learning algotithm自身的inductive bias与问题是否匹配，起到了决定性作用。
```

## 1.5 发展历程
1950~70 years: Given logic inductive ablity to machine: Logic Theroist, General Problem Solving,

1970 years mid: Given knowledge to machine

1980 years: Let machine be able to learn knowledge. IWML(ICML now)

1983 将机器学习划分为很多类，到目前被研究最多应用最广的是**从样例中学习/广义的归纳学习**，其中又有几大流派：
1. 符号主义学习：（第四章）
	1. 决策树：信息论为基础，信息熵最小化为目标，模拟人类对概念判定的树形流程
	2. 基于逻辑的学习：著名代表为Inductive Logic Programming(ILP): too much powerful on representation -> 假设空间太大，复杂度太高
2. 基于神经网络的连接主义学习：（第五章）
	最大的局限性是“试错性”，学习过程涉及大量参数，参数设置缺乏理论指导，参数调节对学习结果影响巨大。
	现在卷土重来，”深度学习“热潮，因为现在的数据量大，计算能力强了。
	当年八十年代走红，也与计算能力内存，访问效率提高有关
3. 统计学习：（第六章）
	代表技术： 支持向量机(Support Vector Machine)， 核方法(Kernel methods)


 ## 1.6 应用现状

用的地方很多嗯嗯。

理论+实验 -> 理论+实验+计算
2006， CMU第一个机器学习系，机器学习奠基人之一T. Mitchell是系主任。

机器学习，数据库，和数据挖掘的关系：
机器学习和数据库是数据挖掘data mining的两大支撑，机器学习和统计学为data mining提供数据分析技术，数据库领域研究为data mining提供数据管理技术。

搜索引擎，自动驾驶，政治竞选，牛。

除了作为数据分析技术的创新源泉，机器学习还有另一个不可忽视的意义：通过建立一些关于学习的计算，**促进我们理解“人类如何学习”**，即理解自我本识。

人类的好奇心：宇宙本源，万物本质，生命本性，自我本识。

假设选择原则中，除了Occam's razor，还有priciple of muliple explanations：即保留与经验观察一致的所有假设。这与集成学习ensemble learning相似。

机器学习领域
- Conferences: ICML, NIPS, COLT, ECML, ACML.
- Journals：*Journal of Machine Learning Research*， *Machine Learning*

人工智能领域
- Conferences: IJCAI, AAAI
- Journals: *Artificial Intelligence* *Journal of Artificial Intelligence Research*

数据挖掘领域：
- Conferences: KDD, ICDM
- Journals: *ACM Transactions on Knowledge Discovery from Data*,  *Data Mining and Knowledge Discovery*

计算机视觉及模式识别：
- Conferences: CVPR
- Journals: *IEEE Transactions ON Pattern Analysis and Machine Intelligence*

神经网络领域：
- Journals: *Neural Computation*, *IEEE Transactions on Neural Networks and Learning Systems*

统计学领域：
- Journals: *Annals of Statistic*

