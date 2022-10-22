# 神经网络
## 5.1 神经元模型
- neural networks:  defination from Kohonen,1988:
```
“神经网络是由具有适应性的 简单单元组成的广泛并行互连的网络，它的组织能够模拟生物神经系统对真实 世界物体所作出的交互反应" 
```
- neuron/unit : basic component of neurual networks. gets excited -> exceeds threshold/bias -> influnce neighbours 
- M-P neural model:
![](0006.png)
- activation function:
	- ideal: $sng(x) = \{0, 1\}$, but it is not differentiable.
	- sigmoid: eg, logitstic function, see Chapter3.3. Squashing input values into (0,1).
## 5.2 感知机与多层网络
- Perceptron: two layers, input layer -> output layer (M-P neuron/threshold logic unit)
	- coud represent: and, or, not
	- and, or, not -> these problems are linearly separable -> there is a hyperplane could seperate positives and negatives. -> learning procedure could converge, find a solution of $w$
	-  xor -> not linearly separable -> learning procedure could functuation, cant find a solution of $w$ -> using multi-layer neural network
	- Learning procudure: $$w_i \leftarrow w_i + \Delta w_i$$ $$\Delta w_i = \eta (y -\bar y)x_i$$ $\eta$ learning rate.
- multi-layer feedforward neural network:  input layer-> hidden layer(s) -> output layer
	- feedforward: there is no circle or loop in the topology of network.
- 神经网络的学习过程，就是根据训练数据来调整神经元之间的 “连接权”(connection weight)以及每个功能神经元的阈值; 换言之，神经网络 “学”到的东西，蕴涵在连接权与阈值中.

## 5.3 误差逆传播方法
- error backpropagation (BP)/ 反向传播算法 
![](0007.png)
	- $dq + ql + q + l$ parameters: dq+ql weights, q+l bias.
	- gradient descent (GD):
		- mean squared error for sample$(x_k, y_k)$: $E_k = \frac{1}{2}\sum_{y=1}^l(\hat y_j^k - y_j^k)$
		- $\Delta$:  
			- $\Delta w_{hj}= -\eta \frac{\partial E_k}{\partial \hat y_k^j}\frac{\partial \hat y_k^j}{\partial \beta_j} \frac{\partial \beta_j}{w_hj}$
			- $\Delta\theta_j, \Delta v_{dh}, \Delta \gamma_h$
	- ![[0008.png]]
	- goal: minimize the Error $E$ among training data D.
		- error BP & accumulated BP. Diffs like stochastic GD& GD.
		- one epoch/round: reading whole training data one time
	- The number of hidden NN: trial-by-error
	- Avoid overfitting of NN:
		- early stopping: stopping when error increases on test set while decreases on training set.
		- regularization: add extra term to objective function, describe the complixity of network, controlled by $\lambda$ (estimited by cross-validation)
		
## 5.4 全局最小与局部最小
## 5.5 其他常见神经网络
## 5.6 深度学习
## 5.7 阅读材料