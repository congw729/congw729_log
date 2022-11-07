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

## 9.3 距离计算

## 9.4 原型聚类

## 9.5 密度聚类

## 9.6 层次聚类

## 9.7 阅读材料