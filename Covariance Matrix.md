## 协方差矩阵（Covariance Matrix）

#### 协方差

​		**定义：设 $X$ 和 $Y$ 为两个随机变量，$X$ 与 $Y$ 的协方差**
$$
Cov[X,Y]=\sigma_{XY}=E[(X-E[X])(Y-E[Y])]=E[XY]-E[X]E[Y]
$$

#### 协方差矩阵

​		**定义：设 $n$ 维随机变量 $(X_1,X_2,...,X_n)$ 的第 $i$ 个分量 $X_i$ 与第 $j$ 个分量 $X_j$ 的协方差为 $\sigma_{ij}$，则称矩阵**
$$
\Sigma=
\begin{pmatrix}
\sigma_{11} & \sigma_{12} & \dots & \sigma_{1n} \\
\sigma_{21} & \sigma_{22} & \dots & \sigma_{2n} \\
\vdots & \vdots & & \vdots\\
\sigma_{n1} & \sigma_{n2} & \dots & \sigma_{nn} \\
\end{pmatrix}
$$
**为 $n$ 维随机变量 $(X_1,X_2,...,X_n)$ 的协方差矩阵。**

​		设 $\Sigma$ 为 $n$ 维随机变量 $(X_1,X_2,...,X_n)$ 的协方差矩阵，则有如下性质：

- ① $\Sigma$ 为半正定矩阵（Positive Semidefinite Matrix）。
- ② 若随机变量 $X_1,X_2,...,X_n$ 相互独立，那么 $\Sigma$ 为对角矩阵。

​		**证：**① 由协方差矩阵的定义知，$\Sigma$ 为对称矩阵。
​		对任意 $x\in \mathbb{R}^n$
$$
\begin{aligned}
x^T\Sigma x&=\sum_{i=1}^n\sum_{j=1}^n(\sigma_{ij}x_ix_j)\\
&=\sum_{i=1}^n\sum_{j=1}^n\left(E[(X_i-E[X_i])(X_j-E[X_j])]x_ix_j\right) \\
&=E\left[\sum_{i=1}^n\sum_{j=1}^n(X_i-E[X_i])(X_j-E[X_j])x_ix_j\right] \\
&=E\left[\left(\sum_{i=1}^n(X_i-E[X_i])x_i\right)^2\right] \\
&\geqslant 0
\end{aligned}
$$
故，协方差矩阵 $\Sigma$ 为半正定矩阵。

​		**设 $n$ 维随机变量 $
X=\begin{bmatrix}
X_1\\
X_2\\
\vdots\\
X_n\end{bmatrix}$，则 $X$ 的协方差矩阵**
$$
\Sigma=E[(X-E[X])(X-E[X])^T]=E[XX^T]-E[X]E[X^T]
$$
​		**证：**
$$
\begin{aligned}
\Sigma&=
\begin{bmatrix}
Cov[X_1,X_1] & Cov[X_1,X_2] & \cdots & Cov[X_1,X_n] \\
Cov[X_2,X_1] & Cov[X_2,X_2] & \cdots & Cov[X_2,X_n] \\
\vdots & \vdots & & \vdots \\ 
Cov[X_n,X_1] & Cov[X_n,X_2] & \cdots & Cov[X_n,X_n] \\
\end{bmatrix} \\ \\

&=\begin{bmatrix}
E[(X_1-E[X_1])(X_1-E[X_1])] & E[(X_1-E[X_1])(X_2-E[X_2])] & \cdots & E[(X_1-E[X_1])(X_n-E[X_n])] \\
E[(X_2-E[X_2])(X_1-E[X_1])] & E[(X_2-E[X_2])(X_2-E[X_2])] & \cdots & E[(X_2-E[X_2])(X_n-E[X_n])] \\
\vdots & \vdots & & \vdots \\ 
E[(X_n-E[X_n])(X_1-E[X_1])] & E[(X_n-E[X_n])(X_2-E[X_2])] & \cdots & E[(X_n-E[X_n])(X_n-E[X_n])] \\
\end{bmatrix} \\ \\

&=E\begin{bmatrix}
(X_1-E[X_1])(X_1-E[X_1]) & (X_1-E[X_1])(X_2-E[X_2]) & \cdots & (X_1-E[X_1])(X_n-E[X_n]) \\
(X_2-E[X_2])(X_1-E[X_1]) & (X_2-E[X_2])(X_2-E[X_2]) & \cdots & (X_2-E[X_2])(X_n-E[X_n]) \\
\vdots & \vdots & & \vdots \\ 
(X_n-E[X_n])(X_1-E[X_1]) & (X_n-E[X_n])(X_2-E[X_2]) & \cdots & (X_n-E[X_n])(X_n-E[X_n]) \\
\end{bmatrix} \\ \\

&=E\begin{bmatrix}
\begin{bmatrix}
X_1-E[X_1]\\
X_2-E[X_2]\\
\vdots \\
X_n-E[X_n]\\
\end{bmatrix}
\begin{bmatrix}
X_1-E[X_1] & X_2-E[X_2] & \cdots & X_n-E[X_n]\\
\end{bmatrix}
\end{bmatrix} \\ \\
&=E[(X-E[X])(X-E[X])^T] \\\\
&=E[(X-E[X])(X^T-E[X]^T)] \\\\
&=E[XX^T-XE[X]^T-E[X]X^T+E[X]E[X]^T] \\\\
&=E[XX^T]-E[XE[X]^T]-E[E[X]X^T]+E[E[X]E[X]^T] \\\\
&=E[XX^T]-E[X]E[X]^T-E[X]E[X^T]+E[X]E[X]^T \\\\
&=E[XX^T]-E[X]E[X^T] \\\\
\end{aligned}
$$

