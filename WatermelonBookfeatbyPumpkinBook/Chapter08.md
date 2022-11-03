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
	- 先从初始训练集训练出一个基学习器，再根据基学习器的表现对训练 样本分布进行调整，使得先前基学习器做错的训练样本在后续受到更多关注, 然后基于调整后的样本分布来训练下一个基学习器; 如此重复进行，直至基学习器数目达到事先指定的值T ,最终将这T 个基学习器进行加权结合。
	- **AdaBoost**
	- re-weighting & re-sampling:
		- re-weighting: re-weight the training sample according to the sample distribution in each training epoch
		- re-sampling: re-sample the training set according to sample distribution
	- bias-viarance:
		- boosting more concentrate on decreasing the bias
## 8.3 Bagging 与随机森林
## 8.4 结合策略
## 8.5 多样性
## 8.6 阅读材料

