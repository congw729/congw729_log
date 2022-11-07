
# 集成学习
## 8.1 个体与集成
- ensemble learning / multi-classifer system/ committe-based learning
	- firstly generate a bunch of **individual learners**, then orgnazie them in some stagedy.
	- homogeneouse  VS heterogenous :
		- homogeneouse: individual learners are the same type, one individual learner in homogeneouse is **base learner.**
		- heterogenous: different types of individual learners, eg. decision tree and nn. One individual learner in heterogenous is component learner.
	- better generalization ability than weak learner.
	- how to have better performance than the best individual learner -> learners should have good performance and ensure diversity 
	- two types of ensemble learning:
		1.  sequential, dependent -> Boosting
		2. paralization -> Bagging, Random Forest
## 8.2 Boosting 
- Boosting:
	- 先从初始训练集训练出一个基学习器，再根据基学习器的表现对训练样本分布进行调整，使得先前基学习器做错的训练样本在后续受到更多关注，然后基于调整后的样本分布来训练下一个基学习器; 如此重复进行，直至基学习器数目达到事先指定的值T ,最终将这T个基学习器进行加权结合。
	- **AdaBoost**
		- additive model, linear combination of base learner$H(x) = \sum_{t=1}^T a_t h_t(x)$ to minimize the exponential loss function
	- re-weighting & re-sampling:
		- re-weighting: re-weight the training sample according to the sample distribution in each training epoch
		- re-sampling: re-sample the training set according to sample distribution
	- bias-viarance:
		- boosting more concentrate on decreasing the bias
## 8.3 Bagging 与随机森林
- want to get independent learners
	- sampling subsets from dataset -> train different learners
	- want learner also have good performance -> consider sampling with overlapp
- Bagging:
	- repesentitive of parallel ensemble sampling
	- based on **bootstraping sampling** in Chapter02
	- 采样出T个含m个训练样本的采样集，然后基于每个采样集训练出一个基学习器，再将这些基学习器进行结合
	- how to get output: simple voting method for classification task; simple averaging method for regression task; if we have same votes, then we just random choose one or consider the confidence for learners.
	- 训练一个Bagging集成与直接使用基学习算法训练一个学习器的复杂度同阶
	- 与标准AdaBoost只适用于二分类任务不同，Bagging能不经修改地用于多分类、回归等任务
	- out-of-bag estimation: 使用没有被采样到的样本作为验证集进对泛化性能进行包外估计
	- bias-viarance:
		- more concentrate on decreasing the virance
		- effects on learners who sensible to samples pertubation ( unpruning decision tree, nn)
- Random Forest
	- an extended variant of Bagging
	- RF在以决策树为基学习器构建Bagging集成的基础上，进一步在决策树的训练过程中引入了随机属性选择
	- 随机属性选择：传统决策树，从d个属性中选择1个最优属性用于划分；随机属性选择，从d个属性中随机选择k个属性作为子集，从k中选择1个最优属性用划分； 一般推荐 $k = log_2d$
	- “代表集成学习技术水平的方法”
		- simple, easy to implement, cost cheap, perform well in many real tasks
		- diversity not only from sample pertubation, but also from attribute pertubation -> 最终集成的泛化性能可通过个体学习器之间差异度的增加而进一步提升.
		- 随机森林的训练效率常优于Bagging,因为在个体决策树的构建过程中，Bagging 使用的是“确定型”决策树，在选择划分属性时要对结点的所有属性进行考察, 而随机森林使用的“随机型”决策树则只需考察一个属性子集.
		- ![](0014.png)
## 8.4 结合策略
- 学习器结合的好处：
	1. 统计角度：由于学习任务的假设空间往往很大，可能有多个假设在训练集上达到同等性能，此时若使用单学习器可能因误选而导致泛化性能不佳，结合多 个学习器则会减小这一风险
	2. 计算角度：学习算法往往会陷入局部极小，有的局部极小点所对应的泛化性能可能很糟糕，而通过多次运行之后进行结合，可降低陷入糟糕局部极小点的风险
	3. 表示角度：某些学习任务的真实假设可能不在当前学习算法所考虑的假设空间中，此时若使用单学习器则肯定无效，而通过结合多个学习器，由于相应的假设空间有所扩大，有可能学得更好的近似
- averaging: for numerical output
	- simple averaging
	- weighted averaging
	- 一般而言，在个体学习器性能相差较大时宜使用加权平均法，而在个体学习器性能相近时宜使用简单平均法.
- voting: for classification
	- majority voting: predict one lable if its votes larger than half, otherwise reject.
	- plurality voting: predict the label who have the most votes. If there are some same votes, then random select one.
	- weighted voting
	- soft voting VS hard voting: class probability prediction VS class label prediction
		- different types learner can't use soft voting
- learning:
	- meta-lerner: combination of the individual learners(primary learners)
	- Stacking: the output of primary learners are input for meta learner
		- k cross-validation, using untrained samples (for primary learners) to train meta learner
		- Learning algorithm for meta-leaners: Multi-response Linear Regression
	- Bayes Model Averaging (BMA): assigh weights for models based on posterior models 
		-  in real tasks, stacking performs well in general.
## 8.5 多样性
- error-ambiguity decomposition
	- individual learner accuracy ⬆️ and diversity ⬆️ -> ensemble performance ⬆️
- diversity measure:
	- **disagreement measure**
	- **correlation coefficient**
	- **$Q$-statistic**
	- **$k$-statistic**
- 多样性增强
	- 数据样本扰动: sutable for unstable base learner (decision tree, nn)
	- 输入属性扰动
		- random subspace algorithm
	- 输出表示扰动
		- flipping output algorithm:对训练样本的类标记稍作变动
		- output smearing algorithm: 将分类输出转化为回归输出后构建个体学习器
		- ECOC algorithm: 将原任务拆解为多个可同时求解的子任务
	- 算法参数扰动
		- 随机设置不同初始化参数
			- negative correlation algorithm
			
## 8.6 阅读材料
- Boosting derivatives: gradient boosting, LPBosst,
	- can't explain why AdaBoost does't have overfitting
- other Combination methods: 基于D-S证据理论的方 法、动态分类器选择、混合专家(mixture of experts), 本章只介绍了成对型多样性度量
- ensemble pruning 
- ensemble learning  is widely used.
- ensemble learning is black box
	- twice-learning
	
Book:
Zhou, Z.-H. (2012). *Ensemble Methods: Foundations and Algorithms.*
