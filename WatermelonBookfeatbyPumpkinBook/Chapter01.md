# 第一章：绪论

## 1.1
一些high level的关于机器学习的介绍：
经验以data的方式存在，从data中学到的结果即model，从data中得到model使用的方法即 **learning algorithm**。
- 计算机科学：研究algorithm
- 机器学习：研究learning algorithm


## 1.2
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
- regression: prediction is continusous


- generalization: albility of model that suits new samples.
- iid: independent and identically distributed, we assume our samples are independently collected from a data distribution.

## 1.3
- induction: 归纳, a generalization from special to general. Learning from samples is **inductive learning**.
- deduction: 演绎, a specialization from general to special

- version space: machtes with the training set.

## 1.4
- inductive bias: 归纳偏好, feature selection based on training data analysis or special knowledge.
- Occam's razor: chosse the samplest/smoothest hypothesis which matches the observation.
- No Free Lunch Theorem: the expetations of two learning algorithms for uniform distribution dara are same. 

```
脱离具体问题，空切谈论什么学习方法更好，毫无意义。
如果要考虑所有潜在问题，则所有的学习算法一样好。
如果要谈算法的相对优劣，就需要针对具体的学习问题。
在一些问题上表现的好的learning algorithm，在另一些问题上可能并不好，learning algotithm自身的inductive bias与问题是否匹配，起到了决定性作用。
```

