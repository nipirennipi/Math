## 半正定矩阵（Positive Semidefinite Matrix）

#### 半正定二次型

​		**定义：设二次型 $\boldsymbol{x^T}A\boldsymbol{x}$，若对任意 $\boldsymbol{x} \neq \boldsymbol{0}$，都有 $f(\boldsymbol{x})\geqslant0$，则称 $f$ 为半正定二次型。**

#### 半正定矩阵

​		**定义：设实对称矩阵 $A$，若对任意 $\boldsymbol{x} \neq \boldsymbol{0}$，都有 $\boldsymbol{x^T}A\boldsymbol{x}\geqslant0$，则称 $A$ 为半正定矩阵。**

​		**定理：$n$ 元二次型 $f=x^TAx$ 为半正定的充分必要条件：它的标准形的 $n$ 个系数全为非负，即它的规范形的 $n$ 个系数全为 $0$ 或 $1$。**

​		**证：**设可逆变换 $x=Cy$ 使
$$
f(x)=f(Cy)=\sum_{i=1}^{n}k_iy_i^2
$$
​		充分性：设 $k_i\geqslant0\ (i=1,2,...,n)$，故
$$
f(x)=\sum_{i=1}^{n}k_iy_i^2 \geqslant 0
$$
​		必要性：反证法，假设有 $k_s<0$，则当 $y=e_s$（单位坐标向量）时，$Ce_s\neq0$，$f(Ce_s)=k_s<0$，这与 $f$ 为半正定相矛盾，即证得 $k_i\geqslant0\ (i=1,2,...,n)$。

​		**推论：对称矩阵 $A$ 为半正定矩阵的充分必要条件：$A$ 的特征值全为非负。**

​		**证：**
方法一：
​		$n$ 阶对称矩阵 $A$ 为半正定矩阵
​		$\iff$ $f(x)=x^TAx$ 为半正定二次型
​		$\iff$ $f$ 的标准形的 $n$ 个系数全为非负，而这 $n$ 个系数是 $A$ 的 $n$ 个特征值
​		$\iff$ $A$ 的特征值全为非负

方法二：
		设 $\lambda$ 是半正定矩阵 $A$ 的任意一个特征值，$x$ 为对应特征向量（$x\neq 0$），即 $Ax = \lambda x$，则 $x^TAx=x^T\lambda x$，从而有
$$
\lambda = \frac{x^TAx}{x^Tx}
$$
其中 $x^T>0$，$x^TAx \geqslant 0$，从而 $\lambda \geqslant 0$。

​		**推论：满秩半正定矩阵为正定矩阵。**

​		**证：**设 $n$ 阶满秩半正定矩阵 $A$，其特征值为 $\lambda_1,\lambda_2,...,\lambda_n$，有
$$
\lambda_1\lambda_2\cdots\lambda_n=|A|
$$
由于满秩矩阵为可逆矩阵，所以 $\lambda_i\neq0\ (i=1,2,...,n)$；又半正定矩阵的特征值全为非负， 得 $A$ 的特征值全为正，即证得 $A$ 为正定矩阵。

#### 半正定矩阵分解

​		**定理：矩阵 $A$ 为半正定矩阵当且仅当存在矩阵 $M$，使**
$$
A=M^TM
$$
**其中 $M$ 不必是方阵，且 $M$ 不是唯一的。**

​		**证：**
​		充分性：若 $A=M^TM$，
$$
x^TAx = x^TM^TMx=(Mx)^TMx
$$
令 $y=Mx$
$$
x^TAx=y^Ty=\|y\|_2^2\geqslant0
$$
​		必要性：半正定矩阵 $A$ 可以对角化
$$
A=P^T\Lambda P
$$
因此
$$
A=P^T\Lambda^{1/2} \Lambda^{1/2} P = (\Lambda^{1/2}P)^T(\Lambda^{1/2} P)
$$
