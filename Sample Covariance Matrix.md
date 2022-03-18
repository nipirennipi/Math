## 样本协方差矩阵（Sample Covariance Matrix）

#### 样本协方差

​		**定义：设 $\boldsymbol{x_i} \in \mathbb{R}^{K\times 1}(i=1,\dots,N)$ 是来自总体的样本，$x_{ij}$ 是 $\boldsymbol{x_i}$ 在第 $j$ 个随机变量上的观测值，那么第 $l$ 个随机变量与第 $k$ 个随机变量的样本协方差为：**
$$
q_{lk} = \frac{1}{N-1} 
\sum_{i=1}^N(x_{il}-\bar{x}_{l})(x_{ik}-\bar{x}_{k})
$$
**其中 $\bar{x}_{j}$ 为第 $j$ 个随机变量的样本均值。**

​		**性质：样本协方差 $q_{jk}$ 为总体协方差 $Cov[j,k]$ 的无偏估计。**

#### 样本协方差矩阵

​		**定义：协方差矩阵 $\boldsymbol{Q}=[q_{lk}]$ 是一个 $K \times K$ 矩阵。**
$$
\boldsymbol{Q} = \frac{1}{N-1}
\sum_{i=1}^N(\boldsymbol{x_i}-\boldsymbol{\bar{x}})
(\boldsymbol{x_i}-\boldsymbol{\bar{x}})^T
$$
**其中 $\boldsymbol{\bar{x}}$ 为样本均值**
$$
\boldsymbol{\bar{x}} = \frac{1}{N}\sum_{i=1}^N \boldsymbol{x_i}
$$
​		**推论：样本协方差矩阵是对协方差矩阵的无偏估计**

#### 计算样本协方差矩阵

​		直接使用其定义可以得出样本协方差矩阵，但是为了减小计算代价，可以先对样本进行中心化，使得 $\sum_{i} \boldsymbol{x_i} = \boldsymbol{0}$，即 $\boldsymbol{\bar{x}} = \boldsymbol{0}$，样本协方差矩阵为
$$
\boldsymbol{Q} = \frac{1}{N-1}
\sum_{i=1}^N\boldsymbol{x_i}\boldsymbol{x_i}^T
$$
注意上式中的 $\boldsymbol{x_i}$ 为中心化之后的样本。

​		在机器学习中，样本经常被表示为 $N\times K$ 矩阵 $\boldsymbol{X} = \begin{bmatrix} 
\boldsymbol{x_1}^T \\ \boldsymbol{x_2}^T \\ \vdots \\ \boldsymbol{x_N}^T\end{bmatrix}$，对样本进行中心化后，则样本协方差矩阵为
$$
\boldsymbol{Q} = \frac{1}{N-1} \boldsymbol{X}^T\boldsymbol{X}
$$

#### 参考文献

- [1] [Sample mean and covariance#Definition of sample covariance - Wikipedia](https://en.wikipedia.org/wiki/Sample_mean_and_covariance)
- [2] [Covariance matrix#Estimation - Wikipedia](https://en.wikipedia.org/wiki/Covariance_matrix#Estimation)

