## 拉普拉斯矩阵（Laplacian Matrix）

#### 拉普拉斯矩阵

​		**定义：给定节点数为 $n$ 的图 $G$，其拉普拉斯矩阵 $L=L_G$ 是一个 $n\times n$ 矩阵，它的定义如下：**
$$
{[L_G]}_{ij} = \begin{cases}
   deg(i) &i=j \\
   -1 &(i,j)\in E(G)   \\
   0 &\text{otherwise } 
\end{cases}
$$
**拉普拉斯矩阵的另一种等价定义：**
$$
L_G=D_G-A_G
$$
其中 $D_G$ 为度矩阵，$A_G$ 为邻接矩阵（Adjacency Matrix）。

​		若图 $G$ 中的边 $(i,j)\in E(G)$ 存在权重 $w_{ij}$，则带权重的拉普拉斯矩阵（Weighted Laplacian Matrix）为
$$
L_{G,w} = D - W
$$
其中 $W=\begin{cases}
   0 &(i,j)\notin E(G) \\
   w_{ij} &(i,j)\in E(G)   \\
\end{cases}$，$D=\text{diag}(d_i)$，$d_i = \displaystyle\sum_{(i,j)\in E(G)}w_{ij}$。

#### 为什么叫拉普拉斯矩阵？

​		现有函数 $f = (f_1,f_2,\cdots,f_n)^T$，其中 $f_i$ 表示节点 $v_i$ 上的信号量（signal），则
$$
[L_Gf]_i = deg(i)[f_i- \text{average of signal on neighbors of } v_i]
$$

上面的公式表示节点 $v_i$ 上的信号量 $f_i$ 与它邻居节点的信号量平均值之间的差值，这种表达类于离散拉普拉斯算子，例如：函数 $f(x,y):\mathbb{R}^2\to\mathbb{R}$，其离散拉普拉斯算子可以表示为
$$
\begin{aligned}
\Delta f(x,y) 
\approx \frac{4}{h^2} \left[\frac{f(x+h,y) + f(x-h,y) f(x,y+h) + f(x,y-h)}{4} - f(x,y)  \right]
\end{aligned}
$$
 $\Delta f(x,y)$ 描述了 $f$ 在点 $(x,y)$ 的邻域边界上的平均值与 $f(x,y)$ 之差。但是需要注意的是 $[L_Gf]_i$ 是节点 $v_i$ 上的信号量 $f_i$ 与它邻居节点的信号量平均值之间的差值，而不是节点 $v_i$ 的邻居节点的信号量平均值与信号量 $f_i$ 之间的差值。综上，拉普拉斯矩阵可以看作是一个负离散拉普拉斯算子的矩阵形式^[6]^。

#### 拉普拉斯矩阵的性质

​		**性质1（可加性）：如果图 $G$ 与图 $H$ 具有相同的节点集，不相交的边集，则**
$$
L_{G\cup H}=L_G+L_H
$$
​		**性质2^[2\ p2]^：$L_G$ 是半正定矩阵。**

​		**证：**记 $L_e$ 为由图 $G$ 节点集与边 $e\in E(G)$ 构成的图所对应的拉普拉斯矩阵
$$
[L_e]_{i,j} = \begin{cases}
   1 &i=j \ \and \ (e\ incident\ to\ v_i) \\
   -1 &e=(i,j)   \\
   0 &\text{otherwise } 
\end{cases}
$$
所以有
$$
x^TL_ex = (x_i-x_j)^2 \qquad e=(i,j)
$$
由可加性：
$$
x^TL_Gx=x^T\sum_{e\in G(E)} L_e x=\sum_{e\in G(E)}  x^T L_e x =\sum_{(i,j)\in G(E)}(x_i-x_j)^2\geqslant 0
$$

同理对于带权重的拉普拉斯矩阵有
$$
x^TL_{G,w}x =\sum_{(i,j)\in G(E)}w_{ij}(x_i-x_j)^2\geqslant 0
$$
证毕。

​		**性质3^[3\ p2]^：$L_G$ 必定必定存在特征值 $0$，其对应的特征向量为 $(1,1,\cdots,1)^T$ 。**

​		证：根据拉普拉斯矩阵定义知，
$$
\sum_{j} [L_G]_{ij} = deg(i) + \sum_{(i,j)\in E(G)}(-1) = 0
$$
即 $L_G$ 的各行的和均为 $0$，令 $n$ 维向量 $p=(1,1,\cdots,1)^T$，则
$$
L_Gp = \boldsymbol{0} = 0p
$$
则 $L_G$ 存在特征值 $0$，对应的特征向量为 $p$。同理，对于带权重的拉普拉斯矩阵也可以给出证明，证毕。

#### 归一化的邻接矩阵与拉普拉斯矩阵^[4]^

​		**定义：归一化的邻接矩阵（Normalized Adjacency Matrix）为（假设图 $G$ 中没有孤立点）**
$$
\mathcal{A} = D^{-1/2}AD^{-1/2}
$$
其中 $A$ 为邻接矩阵，$D$ 为度矩阵，
$$
D^{-1/2} = 
\begin{bmatrix}
1/\sqrt{d_{1}} & 0 & \cdots & 0 \\
0 & 1/\sqrt{d_{2}} & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & 1/\sqrt{d_{n}} \\
\end{bmatrix}
\qquad \qquad 
\begin{aligned}
\mathcal{A}_{ij} &= \sum_k D^{-1/2}_{ik} [AD^{-1/2}]_{kj} \\
&= \sum_k D^{-1/2}_{ik} \sum_l A_{kl}D^{-1/2}_{lj} \\
&= \sum_k \sum_l D^{-1/2}_{ik} A_{kl}D^{-1/2}_{lj} \\
&= D^{-1/2}_{ii} A_{kl}D^{-1/2}_{jj} \\
&= \frac{A_{ij}}{\sqrt{d_{i}d_{j}}}
\end{aligned}
$$
​		**定义：归一化的拉普拉斯矩阵（Normalized Laplacian Matrix）为**
$$
\mathcal{L} = I - \mathcal{A} = I - D^{-1/2}AD^{-1/2}
$$
$I$ 表示单位矩阵，可知 $\mathcal{L} = I - \mathcal{A} = D^{-1/2}(D-A)D^{-1/2} = D^{-1/2}LD^{-1/2}$，其中 $L$ 是非归一化的拉普拉斯矩阵，同样地，有
$$
\mathcal{L_{ij}} = \frac{L_{ij}}{\sqrt{d_id_j}}
$$
​		**性质：$\mathcal{L}$ 是半正定矩阵。**

​		**证：**记 $L_e$ 为由图 $G$ 节点集与边 $e\in E(G)$ 构成的图所对应的拉普拉斯矩阵
$$
x^T D^{-1/2} L_e D^{-1/2} x = \left(\frac{x_i}{\sqrt{d_i}} - \frac{x_j}{\sqrt{d_j}}\right)^2 \qquad e=(i,j)
$$
由可加性：
$$
\begin{aligned}
x^T\mathcal{L}x &= x^T D^{-1/2}LD^{-1/2} x \\\\
&= x^T D^{-1/2} \sum_{e\in E(G)}L_e D^{-1/2} x \\
&= \sum_{e\in E(G)} x^T D^{-1/2} L_e D^{-1/2} x \\
&= \sum_{(i,j)\in E(G)} \left(\frac{x_i}{\sqrt{d_i}} - \frac{x_j}{\sqrt{d_j}}\right)^2 \\ 
&\geqslant 0
\end{aligned}
$$
证毕。

​		**性质：令 $a_1 \leqslant a_2 \leqslant \cdots \leqslant a_n$ 为 $\mathcal{A}$ 的特征值，令 $\lambda_1 \leqslant \lambda_2 \leqslant \cdots \leqslant \lambda_n$ 为 $\mathcal{L}$ 的特征值，则**
$$
\begin{aligned}
-1 \leqslant a_1 \leqslant a_2 \leqslant \cdots \leqslant a_n = 1 \qquad  \qquad
0 = \lambda_1 \leqslant \lambda_2 \leqslant \cdots \leqslant \lambda_n \leqslant 2
\end{aligned}
$$
​		**证：**由于 $\mathcal{L}$ 是半正定矩阵，对任意 $x\neq \boldsymbol{0}$
$$
x^T \mathcal{L} x =  x^T (I - \mathcal{A}) x = x^Tx - x^T\mathcal{A}x \geqslant 0 
\quad \Longrightarrow \quad
1 \geqslant \frac{x^T\mathcal{A}x}{x^Tx}
$$
当 $x = D^{-1/2}p$
$$
x^T \mathcal{L} x =  (D^{-1/2}p)^T \mathcal{L} (D^{-1/2}p)
= 0
\quad \Longrightarrow \quad
1 =  \frac{x^T\mathcal{A}x}{x^Tx} \quad \text{when }\ x = D^{-1/2}p
$$
故
$$
\max_{x\neq \boldsymbol{0}} \frac{x^T\mathcal{A}x}{x^Tx} = 1
$$
由 Rayleigh-Ritz 定理^[5]^，得 $a_n=1$。

​		可以证明 $(I+\mathcal{A})$ 也是半正定矩阵，证明方法与证明 $\mathcal{L}$ 为半正定矩阵同理，故
$$
x^T(I+\mathcal{A})x  = \sum_{(i,j)\in E(G)} \left(\frac{x_i}{\sqrt{d_i}} + \frac{x_j}{\sqrt{d_j}}\right)^2
\geqslant 0
\quad \Longrightarrow \quad
\frac{x^T\mathcal{A}x}{x^Tx} \geqslant -1
$$
由 Rayleigh-Ritz 定理，得 $a_1\geqslant -1$。

​		再次利用 $(I+\mathcal{A})$ 是半正定矩阵的性质
$$
\begin{aligned}
x^T(I+\mathcal{A})x
&= -(x^TIx-x^T\mathcal{A}x) + 2x^Tx \\
&= -x^T\mathcal{L}x + 2x^Tx \\
&\geqslant0
\end{aligned}
\quad \Longrightarrow \quad
\frac{x^T\mathcal{L}x}{x^Tx}  \leqslant 2
$$
由 Rayleigh-Ritz 定理，得 $\lambda_n\leqslant 2$。

​		令 $n$ 维向量 $p=(1,1,\cdots,1)^T$，由拉普拉斯矩阵性质，可知 $p$ 为 $L$ 的特征向量，且对应的特征值为 $0$，则
$$
\mathcal{L}(D^{1/2}p) = D^{-1/2}LD^{-1/2} D^{1/2}  p = D^{-1/2}  Lp 
= \boldsymbol{0} = 0(D^{1/2}p)
$$
则 $\mathcal{L}$ 存在特征值 $0$，对应的特征向量为 $D^{-1/2}p$。又 $\mathcal{L}$ 是半正定矩阵，所有特征值非负，故 $\mathcal{L}$ 的最小特征值 $\lambda_1=0$。

​		证毕。

​		实际上该证明可以简化为只证明 $-1 \leqslant a_1 \leqslant a_2 \leqslant \cdots \leqslant a_n = 1$，因为 $- \mathcal{A}$ 的特征值可由 $\mathcal{A}$ 的特征值取相反数得出，由 $(I+A)x=(\lambda+1)x$，其中 $x$ 为矩阵 $A$ 对应于特征值 $\lambda$ 的特征向量，可知 $I-\mathcal{A}$ 的特征值可由 $-\mathcal{A}$ 的特征值加 $1$ 得出，故 $\mathcal{L} = I - \mathcal{A}$ 的特征值可由 $\mathcal{A}$ 的特征值取相反数加 $1$ 得出，故只需证明 $-1 \leqslant a_1 \leqslant a_2 \leqslant \cdots \leqslant a_n = 1$，即可推出 $0 = \lambda_1 \leqslant \lambda_2 \leqslant \cdots \leqslant \lambda_n \leqslant 2$。

#### 参考文献

- [1] [Topics in Theoretical Computer Science: An Algorithmist's Toolkit: Linear algebra review, adjacency and Laplacian matrices associated with a graph, example Laplacians - MIT OpenCourseWare](https://ocw.mit.edu/courses/mathematics/18-409-topics-in-theoretical-computer-science-an-algorithmists-toolkit-fall-2009/lecture-notes/MIT18_409F09_scribe1.pdf)
- [2] [Topics in Theoretical Computer Science: An Algorithmist's Toolkit: Properties of the Laplacian, positive semidefinite matricies, spectra of common graphs, connection to the continuous Laplacian - MIT OpenCourseWare](https://ocw.mit.edu/courses/mathematics/18-409-topics-in-theoretical-computer-science-an-algorithmists-toolkit-fall-2009/lecture-notes/MIT18_409F09_scribe2.pdf)
- [3] [ORIE 6334: Spectral Graph Theory: Graph Laplacians. Algebraic connectivity. Some easy bounds on bisection and max cut.](https://people.orie.cornell.edu/dpw/orie6334/Fall2016/lecture5.pdf)
- [4] [ORIE 6334: Spectral Graph Theory: Normalized Laplacians. Cheeger's inequality.](https://people.orie.cornell.edu/dpw/orie6334/Fall2016/lecture7.pdf)
- [5] 张贤达. 矩阵分析与应用[M]. 清华大学出版社有限公司, 2004. p443
- [6] [Laplacian matrix#Interpretation_as_the_discrete_Laplace_operator_approximating_the_continuous_Laplacian - Wikipedia](https://en.wikipedia.org/wiki/Laplacian_matrix#Interpretation_as_the_discrete_Laplace_operator_approximating_the_continuous_Laplacian)

