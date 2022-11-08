# **贝叶斯分类器**
## 7.1 贝叶斯决策论
- Bayesian decision theory: 对分类任务来说，在所有相关概率都已知的理想情形下，贝叶斯决策论考虑如何基于这些概率和误判损失来选择最优的类别标记。
- Bayes decision rule: 为最小化总体风险，只需在每个样本上选择那个能使条件风险$R(c|x)$最小的类别标记。
	- $R(c|x)$: the conditional risk / expected loss for sample $x$
	- Problem: Need to get posterior probability $P(c|x)$. Two strategies:
		1. discriminative models: given $x$, building model $P(c|x)$, then predict class$c$.
		2. generative models: building model of joint probability distribution, then get $P(c|x)$.
			- $P(c|x) = \frac{P(c)P(x|c)}{P(x)}$
			- $P(c)$: class prior probability
			- $P(x|c)$: class conditional probability / likelihoood
			- $P(x)$: evidence
## 7.2 最大似然估计
- the training procedure of probability model is **parameter estimation procedure**, two solutions: 
	1. Frequentist -> maximum likelihood estimation (MLE), parameters are unknown but are exist fixed value.
	2. Bayesian -> assume the parameters obey a prior distribution, calculate the posterior distribution based on observed data.

- Maximum likelihood Estimation:
	- Log-likelihood: to avoid underflow caused by continuous multiplication.

这种参数化的方法虽能使类条件概率估计变得相对简单，但估计结果的准确性严重依赖于所假设的概率分布形式是否符合潜在的真实数据分布.在现实应用中，欲做出能较好地接近潜在真实分布的假设,往往需在一 定程度上利用关于应用任务本身的经验知识，否则若仅凭“猜测”来假设概率分布形式，很可能产生误导性的结果.


## 7.3 朴素贝叶斯分类器 
- naive Bayes classifer: attribute conditional independence assumption -> to avoid the problem that it is hard to get class conditional probability from finite training samples ($P(x|c)$ is joint probability for all classes).
	- Laplacian correction: do smoothing, add 1 , avoid get zero value probability.
- Lazy learning: do probability assumtion only when received the predict request
## 7.4 半朴素贝叶斯分类器 
- semi-naive Bayes classifier:
	- attribute independence assumption hardly holds water in real life 
	- relaxation on attribute independence assumption 
	- One-Dependent Estimator (ODE): each attribute is rely on one attribute at most.
		- super parent (SPODE): one super parent
		- Tree Augmented naice Bayes (TAN):  simplified maximum weighted spanning tree, only keep the dependency between strong related attributes
		- averaged (AODE): based on ensemble learning, build SPODE for each attribute that with sufficient training data as  super parent
	- ODE to kDE?
		- k increases, training samples need tobe increased exponentially
## 7.5 贝叶斯网
- Bayesian network / belief network
	- Directed Acyclic Graph (DAG) -> describe the dependency between attributes, $D$
 	- Conditional Probability Table (CPT) -> describe the joint probability distribution of attributes  $\Theta$ 
	- $B = <G, \Theta>$
	- types of dependency:
		1. common parent (conditional independence, when the parent is known.)
		2. V structure (marginal independence, two parent attributes are independence when the child attribute is unknown; not independence when the child attribute is known. )
		3. sequence structure (conditional independence, when the central vertex is known )
	- to analyse conditional dependency, we could use D- separation, and transfrom directed to indirected
		- find all V structure,  add an edge between two parents
		- change all directed edge to indirected edge
		- called 'moral graph', the process of step 1 is 'moralization'
	- learning procedure of bayesian network
		- simple, just count appearances,
		- problem: we don't know the network's structure in real life
		- solution: first priority is train the dataset to find the most appropriate bayesian network
			- **score search**: define a score function, then find depending on the scores 常用评分函数通常基于信息论准则，此类准则将学习问题看作一个数据压缩任务
			- minimal description length (MDL): 学习的目标是找到一个能以最短编码长度描述训练数据的模型，此时编码的长度包括了描述模型自身所需的字节长度和使用该模型描述数据所需的字节长度.  学习任务就转化为一个优化任务，即寻找一个贝叶斯网B使评分函数 $s(B|D)$最小: 
					- $s(B|D) = f(\theta)|B| - LL(B|D)$ 
					- $f(\theta)$ : the size needed for discirbe each param $\theta$
					- $LL(B|D)$: the log-likelihood of network $B$				
				- Akaike Information Criterion (AIC): when $f(\theta) = 1$
				- Bayesian Information Criterion (BIC): when $f(\theta) = \frac{1}{2}log_m$
			- minimize score function -> maximize likelihood of parameter $\Theta$
				- 只需对网络结构进行搜索，而候选结构的最优参数可直接在训练集上计算得到 -> NP problem
				- Solutions: 贪心算法 or 添加约束削减搜索空间
	- inference: the process that query unknown variables based on observed variables (evidence).
		- ideal: joint probability distribution to get posterior probability -> NP hard
		- 近似推断: **Gibbs sampling**, 一种随机采样方法, Markov chain

## 7.6 EM算法
Former discusion assumed: all attribute variabls are observed, which means the training set is complete which is unrealistic. 
- latent variables:
	- unobserved variables
	- calculate the marginal likelihood of latent variables
	$$LL(\Theta|X) = lnP(X|\Theta) = ln\sum_Z P(X,Z|\Theta)$$
	- 或者通过梯度下降优化算法，但是计算量会随着隐变量的树木指数级上升。
- Expectation-Maximization Algorithm: 
	- 它是一种迭代式的方法，其基本想法是: 若参数$\Theta$已知, 则可根据训练数据推断出最优隐变量$Z$的值(E步); 反之，若$Z$的值已知，则可方便地对参数$\Theta$做极大似然估计(M 步).
	- E: 期望(E)步，利用当前估计的参数值来计算对数似然的期望值
	- M: 最大化(M)步，寻找能使E步产生的似然期望最大化的参数值

## 7.7 阅读材料
- 为避免贝叶斯定理求解时面临的组合爆炸、样本稀疏问题，朴素贝叶斯分类器引入了属性条件独立性假设。这个假设在现实应用中往往很难成立，但有趣的是，朴素贝叶斯分类器在很多情形下都能获得相当好的性能。

- 根据对属性间依赖的涉及程度，贝叶斯分类器形成了一个“谱”:朴素贝 叶斯分类器不考虑属性间依赖性，贝叶斯网能表示任意属性间的依赖性，二者分别位于 “谱 ”的两端；介于两者之间的则是一系列半朴素贝叶斯分类器，它们基于各种假设和约束来对属性间的部分依赖性进行建模

- 贝叶斯分类器(Bayes Classifier)与一般意义上的“贝叶斯学习"(Bayesian Learning)有显著区别，前者是通过最大后验概率进行单点估计，后者则是进行分布估计.

- EM算法也用于学习Gaussian mixture model的参数

