# 第二章：模型评估与选择
## 2.1 经验误差与过拟合
*m* samples, *a* samples are wrongly classified.
- error rate: E = a/m
- accuracy: acc = 1 - E
- training/empirical error: error of learner in training samples
- generalization error: error of learner in new samples

**Overfitting and Underfitting**
- Overfitting: learner was trained too good to facing new samples.
- Underfitting: learner basiclly learned nothing.

**Model selection problem**
Ideally, evaluating the generalization error of models which is not possible.

## 2.2 评估方法

Using testing set to mock new samples, then get simulated generalization error. Ways to generate test set/evaluating generalizability:
1. hold-out: 留出法
2. cross validation: 交叉验证法
3. bootstrapping: 自助法
4. parameter tunning: 调参

## 2.3 性能度量
- performance measure: the metric to evaluate the generalizability of models.
- measures for regression task: 
	1. mean squared error (MSE)
	2. MSE constructed by distribution and probability density function
- measures for classification task:
	1. error rate & accurancy 
		extra represntations constructed by distribution and probability density function)
	2. precision & recall   查准率与查全率
		confusion matrix here 
		- precision = TP/(TP+FP)
		- recall = TP/(TP+FN)
		- PR Curve: precision is  y axis, recall is x and the area is bigger the better. 
			- Break-Event Point(BEP): the value when precision == recall. The bigger the better
			- **F1** = 2 \* precision \* recall / (precision + recall)
			- F_\beta: using \beta to control the weight of precision and recall. \beta > 1, recall matters more. \beta < 1, precision matters more.
			- macro-P, micro-R and micro-F1: when when have multiple binary classification confusion matrix
	3. ROC & AUC 
		For classification task, there is a thershold for logits results. 
		- ROC: receiver operating characteristic. TPR is y axis, FPR is x.
		- TPR = TP/(TP+FN)
		- FPR = FP/(FP+TN)
		- AUC: area under curve, the bigger the better
	4. 代价敏感错误率与代价曲线
		- unequal cost: for evaluateing the various cost due to various type of false prediction.

## 2.4 比较检验
Problem - Hard to do the evaluation:
- gap betwee generalization error and test error
- various test results due to test set selection (size, contained samples)
- various test results due to the stochastic of learning algorithms

Solutions:
1. hypothesis test:假设检验，如果我们观察到a比b好，那么a的泛化性能是否在统计意义上优于b，以及我们对于这个结论的把握有多大。
	- binomial test
	- t-test
2. 交叉验证t检验
3. McNemar检验
4. Friedman检验与Nemenyi后续检验

## 2.5 偏差与方差
- bias: 偏差，the difference between prediction and ground truth
- variance: 方差，the difference of predictions due to different training set
- noise: the difference of label and ground truth
- generalization error: could be seen as the composition of bias, variance and noise.

