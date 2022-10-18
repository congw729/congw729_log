# 决策树
## 4.1 基本流程

- divide-and-conquer
	![](0003.png)
	- end condition: （1）当前结点包含的样本都是同一个类别；（2）当前属性集为空或者所有样本属性值都一样（此时该结点的类别用后验分布）；（3）当前结点包含的样本集合为空（此时该结点的类别用先验分布）。
	
## 4.2 划分选择

The key of decision tree is Line 8 in Figure 4.2, how to select the best partition attribute $a_*$.
- information entropy: $$Ent(D) = -\sum_{k=1}^{|y|}p_k log_2{p_k}$$
	- $p_k$: the proportion of the samples belong to $k$ label in dataset $D$.
	- The bigger the entropy is, the lower purity of the dataset.
- information gain: $$Gain(D,a) = Ent(D) - \sum_{v=1}^V \frac{|D^v|}{|D|}Ent(D^v)$$
	- Arrtibute $a$  have $V$ possible values.
	- **Algorithm ID3** try to maximize information gain.
	- cons: prefer the attributes who have large number of $V$.
- gain ratio: $$Gain\_ratio(D,a) = \frac{Gain(D,a)}{IV(a)}$$ and $$IV(a) = - \sum_{v=1}^V \frac{|D^v|}{|D|} log_2 \frac{|D^v|}{|D|}$$
	- intrinsic value: $IV(a)$, the larger the $V$ is, the bigger the intrinsic value.
	- **Algorithm C4.5**: 先从候选划分属性中找出信息增益高于平均水平的属性，再从中选择增益率最高的。
- Gini index:
	- Gini: $$Gini(D)=\sum_{k=1}^{|y|} \sum_{k^\prime\neq k}p_k p_{k^\prime} = 1-\sum{k=1}{|y|}p_k^2$$
	- 从数据集D 中随机抽取两个样本，其类别标记不一致的概率
	- The bigger the Gini index is, the lower purity of the dataset.
	- Gini index : $$Gini\_index(D,a) = \sum_{v=1}^V\frac{|D^v|}{|D|}Gini(D^v)$$
	- **Algorithm CART** try to minimize the Gini index after partition.
	
## 4.3 剪枝处理
## 4.4 连续与缺失值
## 4.5 多变量决策树
## 4.6 阅读材料