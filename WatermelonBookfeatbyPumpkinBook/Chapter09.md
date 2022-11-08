# 聚类
## 9.1 聚类任务
- clustering: a learning task of unsupervised learning
- terminology:
	- dataset $D$contains $m$ samples: $D = \lbrace x_1, x_2, ... x_m \rbrace$ 
	- sample $x$ is $n$ dim vector: $x_i = (x_{i1}, x_{i2}, ... , x_{in})$
	- clustering algorithm devides dataset $D$ to $k$ clusters: $\lbrace C_l | l = 1, 2, ..., k\rbrace$ and these clusters are disjoint $C_{l'} \cap_{l' \neq l} C_l = \emptyset$
	- correspondingly, we have $\lambda_j$ to represent the cluster lable of $x_j$: $\lambda_j \in \lbrace 1,2,...,k \rbrace$, and $x_j \in C_{\lambda_j}$
	- the result of clustering could be represented by a vector $\mathbb{\lambda}$ of $m$ elements: $\mathbb{\lambda} = (\lambda_1, \lambda_2, ... \lambda_m)$ 

## 9.2 性能度量
- validity index
	- intra-cluster similarity VS inter-cluster similarity
		- former, higher, better; latter lower, better
	- external index VS internal index
		- external index: comparing with some reference model
		- acccording to the clustering results comparing with the reference model, we have external indexs::
			- **Jaccard Coeffcient**
			- **Fowlkes and Mallows Index (FMI)**
			- **Rand Index (RI)**
		- using the clustering results - distances between intra and intre clusters, we have internal index:
			- **Davies-Bouldin Index (DBI)**
			- **Dumn Index (DI)**
			
## 9.3 距离计算
-  attribute
	- continuous/numerical attribute
	- categorical/nominal attribute
		- ordinal attribute
		- non-ordinal attribute
- similarity measure
	- distace measure $dist(·,·)$
		- 通常满足：非负性，同一性，对称性，和直递性（三角不等式）
		- Minkowski distance: $L_p$ norm, could be used in ordinal attribute
			- Manhattan distance: $p = 0$ 
			- Euclidean distance: $p = 1$
		- weighted distance
	- non-metrix distance
		- 可以不满足直递性
	- more on **distance metric learning**
- for non-ordinal attribute:
	- **Value Difference Metrix (VDM)**
## 9.4 原型聚类
- prototype-based clustering
	- 算法先对原型进行初始化，然后对原型进行迭代更新求解
	- **k-means algorithm** 
		- EM algorithm
	![](0015.png)
	- **learning vector quantization (LVQ)**
		- lossy compression of vector -> vector quantization
		- Voronoi tessellation(剖分)
		![](0016.png)
	- Mixture of Gaussian (using probability model)
		- maximize log likelihood, EM algorithm
	![](0017.png)
## 9.5 密度聚类
- density-based clustering 
	- **DBSCAN**
		- based on neighborhood 
		- $\epsilon$-邻域
		- core object
		- directy density-reachable
		- density-reachable
		- density-connected
		![](0019.png)
		- cluster: 由密度可达关系导出的最大的密度相连样本集合
			- conectiviy 
			- maximality
		![](0020.png)
## 9.6 层次聚类
- hierarchical clustering
	- tree-shaped clustering
	- top down or bottom up division
	- **AGNES**
		- bottom up
		- treat every sample as init cluster, then merge the closet cluster pair,
		![](0021.png)
		- single-linkage: $d = d_min$
		- complete-linkage: $d = d_max$
		- average-linkage: $d = d_avg$
		
## 9.7 阅读材料
- Other validity index: F value, mutual information, average silhouette width (平均廓宽)
- k 均值算法可看作高斯混合聚类在混合成分方差相等、且每个样本仅指派给一个混合成分时的特例
- cluster ensemble
- anomaly detection based on clustering / distance computation/ isolation.