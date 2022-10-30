# 贝叶斯分类器
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
## 7.3 朴素贝叶斯分类器 
## 7.4 半朴素贝叶斯分类器 
## 7.5 贝叶斯网
## 7.6 EM算法
- Expectation-Maximization Algorithm

## 7.7 阅读材料

