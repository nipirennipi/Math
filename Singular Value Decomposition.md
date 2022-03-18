## 奇异值分解（Singular Value Decomposition）

#### 对称矩阵的对角化

​		**定理：设 $A$ 为 $n$ 阶对称矩阵，则必有正交矩阵 $P$，使 $P^{-1}AP=P^TAP=\varLambda$（也可写作 $A=P\varLambda P^T$），其中 $\varLambda$ 是以 $A$ 的 $n$ 个特征值为对角元的对角矩阵**。

由 $P^TAP=\varLambda$ 得 $AP=P\varLambda$，并将 $P$ 使用列向量表示 $P=(p_1,p_2,...,p_n)$，即得：
$$
A\left(p_1,p_2,...,p_n\right)=\left(p_1,p_2,...,p_n\right)
\begin{bmatrix}
\lambda_1&&& \\
&\lambda_2&& \\
&&\ddots& \\
&&&\lambda_n \\
\end{bmatrix}
$$
于是 $Ap_i=\lambda_ip_i \ (i=1,2,...,n)$ ，$P$ 的列向量 $p_i$ 为 $A$ 对应于特征值 $\lambda_i$ 的特征向量。

#### 奇异值分解

设 $A$ 为 $m\times n$ 的实数矩阵，希望将其分解为：
$$
A=U\Sigma V^T
$$
其中 $U$ 与 $V$ 都是正交矩阵，$U\in \mathbb{R}^{m\times m}$ 称为左奇异矩阵，$V\in \mathbb{R}^{n\times n}$ 称为右奇异矩阵，$\Sigma \in \mathbb{R}^{m\times n}$ 仅在主对角线上有非零元素，称之为奇异值。

假定 $m<n$ （下同），则（其中 $\sigma_1,\sigma_2,...,\sigma_m$ 即为奇异值）：
$$
\Sigma=
\begin{bmatrix}
\sigma_1 &&&&\\
&\sigma_2 &&&\\
&&\ddots &&\\
&&&\sigma_m &&\\
\end{bmatrix}_{m\times n}
$$
求解 $U,\Sigma,V$
$$
AA^T=U\Sigma V^TV\Sigma^TU^T=U\Sigma\Sigma^T U^T \\
A^TA=V\Sigma^TU^TU\Sigma V^T=V\Sigma^T\Sigma V^T
$$
其中：
$$
\Sigma\Sigma^T=
\begin{bmatrix}
\sigma_1^2 &\\
&\sigma_2^2 &\\
&&\ddots &\\
&&&\sigma_m^2 \\
\end{bmatrix}_{m\times m}

\Sigma^T\Sigma=
\begin{bmatrix}
\sigma_1^2 &&&&&\\
&\sigma_2^2 &&&&\\
&&\ddots &&&\\
&&&\sigma_m^2 &&\\
&&&&0 &\\
&&&&&\ddots \\
\end{bmatrix}_{n\times n}
$$
而 $AA^T,A^TA$ 都是对称矩阵，使用对称矩阵的可对角化的性质，可求出 $U,V$，$\Sigma\Sigma^T$ 或 $\Sigma^T\Sigma$ 对角非零元素即为奇异值的平方。

从以上讨论中可以得出：

- $U$ 的列向量为 $AA^T$ 的特征向量
- $V$ 的列向量为 $A^TA$ 的特征向量，则 $V^T$ 的行向量为 $A^TA$ 的特征向量

#### 奇异值分解的应用

奇异值可以作为矩阵 $A$ 的代表值，它记录了 $A$ 中的信息，且奇异值越大，它代表的信息越多，而 $\Sigma$ 主对角线上的奇异值从左上到右下依次递减：
![SVD](.\SVG\Singular Value Decomposition0.svg)

只用取前面一部分奇异值，即可记录矩阵 $A$ 的大部分信息。

应用：图片压缩