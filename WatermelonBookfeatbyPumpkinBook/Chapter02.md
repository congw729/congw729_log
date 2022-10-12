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
	将数据集分为两个互斥的集合，一个为训练集，一个为测试集。测试误差作为对泛化误差的估计。
	- stratified sampling 分层采样：保留类别比例的采样方式  -> 目的是为了保衡数据分布的一致性，避免数据划分过程中引入额外的偏差。
	- 为了得到稳定可靠的估计结果：需要进行若干次随机划分，重复进行试验评估后，取平均值。
	- 训练集和测试集的比例是一个delimma，训练集过大，评估结果不够稳定准确；训练集过小，降低了评估结果的保真性fidelity。
	- 常见的比例是2:1，4:1 。
	
2. cross validation / *k*-fold cross validation: 交叉验证法
	将数据集划分为*k*个互斥子集，每个子集从数据集中分层采样得到，尽量保持数据分布的一致性。 
	- 每次训练用*k-1*个子集训练，剩下的那个子集进行测试。训练出k个模型，一共得到k个评估结果，取均值。
	- 评估结果的稳定性和保真性很大程度上取决于k的取值，k常用取值为10。
	- 为了减少因样本划分不同而引入的差别：随机使用不同划分方法重复p次，最终取p次k折交叉验证结果的均值。
	- Leave One Out： 留一法，当k值和数据集大小相同时。该方法评估结果往往被认为比较准确，但是数据集很大时开计算开销很大。
	- No Free Lunch对实验评估方法依然适用。
	
3. bootstrapping: 自助法
	从数据集中有放回的采样，直到新构建的数据集和原始数据集相同。
	新构建的数据集用于训练，原始数据集中没有被采样到的数据作为测试（大概占原始数据集的36.8%）。
	- pros：在数据集小，难以划分训练测试集时很有用；能产生的多个数据集，对集成学习方法很有好处。
	- cons：改变了数据集的分布，会引入estimate bias
	
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


