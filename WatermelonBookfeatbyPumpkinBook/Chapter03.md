# 线性模型
## 3.1 基本形式
- linear model: a function with linear combination of features with good comprehensibility. $y = w^{T}x + b$
- non linear model: layer stuctures, high dimension projection.

## 3.2 线性回归
- linear regression
	- mean squred error -> least square method: attempts to find a line that minimizes the sum of the Euclidean distances from all samples to the line.
	- parameter estimition: find the solution of $w$ and $b$
	- multivariate linear regression: need to calculate the inverse of matrix.
	- log-linear regression: $ln_y = w^{T}x + b$,  make $e^{w^{T}x+b}$ closing to $y$.
	- generalized linear model: a link function *g()*  which is monotone and differentiable make  $y = g^{-1}(w^{T}x+b)$

## 3.3 对数几率回归
- logistic regression
	- to map the prediction from regression to classification
	- find a monitic differentiable function map from the the regresson model's preditions to lable $y$ 
	- binary classification: from continious value to {0,1}.
		- ideal: unit-step function. problem: function is not continuous, can't be $g^-()$
		- surrogate function: logistic function $y = \frac{1}{1+e^{-z}}$
		- 

## 3.4 线性判别估计 
- linear discriminant analysis

## 3.5 多分类学习 

## 3.6 类别不平衡问题

## 3.7 阅读材料
