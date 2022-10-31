# **贝叶斯分类器**
## 7.1 贝叶斯决策论
- Bayesian decision theory: 对分类任务来说，在所有相关概率都已知的理想情形下，贝叶斯决策论考虑如何基于这些概率和误判损失来选择最优的类别标记。
- Bayes decision rule: 为最小化总体风险，只需在每个样本上选择那个能使条件风险$R(c|x)$最小的类别标记。
	- $R(c|x)$: the conditional risk / expected loss for sample $x$
	- Problem: Need to get posterior probability $P(c|x)$. Two strategies:
		1. discriminative models: given $x$, building model $P(c|x)$, then predict class$c$.
		2. generative models: building model of joint probability distribution, then get $P(c|x)$.
			- $P(c|x) = \frac{P(c)P(x|c)}{P(x)}$
			- $P(c)$: class prior probbility
			- $P(x|c)$: class conditional probability / likelihoood
			- $P(x)$: evidence
## 7.2 最大似然估计
- the training procedure of probability model is **parameter estimation procedure**, two solutions: 
	1. Frequentist -> maximum likelihood estimation (MLE), parameters are unknown but are exist fixed value.
	2. Bayesian -> assume the parameters obey a prior distribution, calculate the posterior distribution based on observed data.

- Maximum likelihood Estimation:
	- Log-likelihood: to avoid underflow caused by continuous multiplication.
```
这种参数化的方法虽能使类条件概率估计变得相对简单，但 估计结果的准确性严重依赖于所假设的概率分布形式是否符合潜在的真实数 据分布.在现实应用中，欲做出能较好地接近潜在真实分布的假设,往往需在一 定程度上利用关于应用任务本身的经验知识，否则若仅凭“猜测”来假设概率 分布形式，很可能产生误导性的结果.
```

## 7.3 朴素贝叶斯分类器 
- naive Bayes classifer: attribute conditional independence assumption -> to avoid the problem that it is hard to get class conditional probability from finite training samples.
	- Laplacian correction: do smoothing, add 1 , avoid get zero value probability.
-Lazy learning: do probability assumtion only when received the predict request
## 7.4 半朴素贝叶斯分类器 
## 7.5 贝叶斯网
## 7.6 EM算法
- Expectation-Maximization Algorithm

## 7.7 阅读材料

