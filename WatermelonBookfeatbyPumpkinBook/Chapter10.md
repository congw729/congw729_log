# 降维与度量学习
## 10.1 $k$ 近邻学习
- $k$-Nearst Neighbor (KNN): Given test samples, finding k nearst neighbors in training set based on distance metric, and using the infromation from those neighbours to do prediction.
	- voting for classification; averaging for regression; could using weighted strategy.
	- no explicit learning procedure, a represent of lazy learning ( training cost is zero, which is contrast to eager learning)
	- (provement using probabiltiy) generalization error is no more than the twice of bayesian optimal classification.

## 10.2 低纬嵌入
knn的假设：有dense sample，然而现实中很难满足，因为数据维度会很大。而数据维度很大的时候，距离计算也变的十分困难 -> 高纬情况下的样本洗漱，计算困难  the curse of dimensionality
- dimension reduction
	- high dim -> subspace: an embedding in low dim
		-multiple dimensional scaling (MDS) : the distance between samples in original space still remains the same in subspace

## 10.3 主成分分析
从高维空间到低维空间的线性映射
- Principal component analysis (PCA)

## 10.4 核化线性降维
非线性映射
- Kernalized PCA

## 10.5 流形学习
拓扑流行概念的降维方法，“流形”是在局部与欧氏空间同胚的空间。
- manifold learning
	- isometric mapping (Isomap)
	- locally linear embedding (LLE)
## 10.6 度量学习
降维的目的是找到可以学习的更好的空间，每个空间对应了样本属性上定义的一个距离度量。寻找合适的空间就是寻找一个合适的距离度量。
- metric learning

## 10.7 阅读材料
