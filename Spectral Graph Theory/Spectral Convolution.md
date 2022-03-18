## 谱卷积（Spectral Convolution）

#### 图傅里叶变换（Graph Fourier Transform）

​		给定图 $G=(V,E)$，$|V|=n$ 为节点集，$E$ 为边集，函数 $f:V\to \mathbb{R}^{n\times 1}$ 定义了图中每个节点上的信号量，$f_i$ 表示节点 $v_i$ 上的信号量，图 $G$ 的拉普拉斯矩阵记为 $L_G$，进行特征值分解
$$
L_G = U^T\Lambda U =
\begin{bmatrix} u_1^T \\ u_2^T \\ \vdots \\ u_n^T \end{bmatrix}
\begin{bmatrix}
\lambda_1 & & & \\
& \lambda_2 & &  \\
& & \ddots & \\
& & & \lambda_n \\
\end{bmatrix}
\begin{bmatrix} u_1 & u_2 & \cdots & u_n \end{bmatrix}
$$
其特征值 $\lambda_1 \leqslant \lambda_2 \leqslant \cdots \leqslant \lambda_n$ 所退对应的特征向量分别为 $u_1,u_2,\cdots,u_n$。

​		**定义：图 $G$ 中结点的信号量 $f$ 的图傅里叶变换为**
$$
\mathcal{F}[f] = \hat{f}(\lambda) = \hat{f} = U^Tf
$$
其中 $\hat{f} \in \mathbb{R}^{n\times 1}$，$\hat{f}(\lambda)$ 表示 $\hat{f}$ 为特征值的函数，$\hat{f}(\lambda_i) = \hat{f_i} = u_i^T f \quad(i=1,2,\cdots,n)$。

​		因为 $L_G$ 是实对称矩阵，所以 $U^TU=I$，即特征向量 $u_1,u_2,\cdots,u_n$ 形成一个正交基，所以可以定义逆图傅里叶变换（Inverse Graph Fourier Transform）为
$$
\mathcal{F}^{-1}[\hat{f}] = f = U\hat{f}
$$
对应于经典傅里叶变换中的时域与频域，图傅里叶变换中也定义了节点域（Vertex domain）与谱域（Spectral domain）。图的傅里叶变换并不是唯一确定的，因为它取决于拉普拉斯矩阵的特征向量，一般使用归一化的拉普拉斯矩阵的特征向量来定义图傅里叶变换。

#### 谱卷积（Spectral Convolution）

​		类比于卷积定理（Convolution Theorem），下面给出图上的谱卷积操作：
$$
\begin{aligned}
g_{\theta}*f 
&= \mathcal{F}^{-1}\left[\mathcal{F}\left[g_{\theta}\right] \odot \mathcal{F}\left[f\right] \right] \\
&= U \left(\hat{g_\theta} \odot U^Tf \right) \\
&= U \left(\hat{g_\theta}(\Lambda) U^Tf \right) \\
&= U \hat{g_\theta}(\Lambda) U^Tf  \\
&= \hat{g_\theta}(U\Lambda U^T) f \\
&= \hat{g_\theta}(L_G) f \\
\end{aligned}
\qquad \qquad \text{where }\ 
\begin{aligned}
	\hat{g_\theta} =
	\begin{bmatrix}
		\hat{g_\theta}(\lambda_1) \\ \hat{g_\theta}(\lambda_2) \\ \vdots \\ \hat{g_\theta}(\lambda_n) \\
	\end{bmatrix}
\end{aligned}
\quad 
\begin{aligned}
	\hat{g_\theta}(\Lambda) =
	\begin{bmatrix}
		\hat{g_\theta}(\lambda_1) & & &\\ 
		& \hat{g_\theta}(\lambda_2) & &\\ 
		& & \ddots &\\ 
		& & &\hat{g_\theta}(\lambda_n) \\
	\end{bmatrix}
\end{aligned}
$$
其中 $\hat{g_\theta}(\Lambda)$ 作为谱卷积核（Spectral Filter），可以理解为是关于 $L_G$ 的特征值的函数^[4]^，$\odot$ 表示阿达马乘积（Hadamard product）。

#### 参考文献

- [1] [Graph Fourier transform - Wikipedia](https://en.wikipedia.org/wiki/Graph_Fourier_transform)
- [2] Deep Learning: Graph Convolutional Networks - NYU. [PDF](https://drive.google.com/file/d/1oq-nZE2bEiQjqBlmk5_N_rFC8LQY0jQr/edit) [VEDIO](https://www.youtube.com/watch?v=Iiv9R6BjxHM)
- [3] Machine Learning: Graph Neural Network - NTU. [PDF](http://speech.ee.ntu.edu.tw/~tlkagk/courses/ML2020/GNN.pdf) [VEDIO](https://www.youtube.com/watch?v=M9ht8vsVEw8)
- [4] [Kipf T N, Welling M. Semi-supervised classification with graph convolutional networks[J]. arXiv preprint arXiv:1609.02907, 2016.](https://arxiv.org/abs/1609.02907)