聚类
## 9.1 聚类任务
- clustering: a learning task of unsupervised learning
- terminology:
	- dataset $D$contains $m$ samples: $D = \lbrace x_1, x_2, ... x_m \rbrace$ 
	- sample $x$ is $n$ dim vector: $x_i = (x_{i1}, x_{i2}, ... , x_{in})$
	- clustering algorithm divid dataset $D$ to $k$ clusters: $\lbrace C_l | l = 1, 2, ..., k\rbrace$ and thses clusters are disjoint $C_{l'} \cap_{l' \neq l} C_l = \emptyset$
	- correspondingly, we have $\lambda_j$ to represent the cluster lable of $x_j$: $\lambda_j \in \lbrace 1,2,...,k \rbrace$, and $x_j \in C_{\lambda_j}$
	- the result of clustering could be represented by a vector $\mathbf{\lambda}$ of $m$ elements: $\mathbf{\lambda} = (\lambda_1, \lambda_2, ... \lambda_m)$ 

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
	![](0015.png)
	- **learning vector quantization (LVQ)**
		- lossy compression of vector -> vector quantization
		- Voronoi tessellation(剖分)
		![](0016.png)
	- Mixture of Gaussian (using probability model)
		- maximize log likelihood, EM algorithm
	![](0017.png)
## 9.5 密度聚类

## 9.6 层次聚类

## 9.7 阅读材料