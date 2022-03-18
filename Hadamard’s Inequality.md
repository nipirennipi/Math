## 阿达马不等式（Hadamard’s Inequality）

#### Hadamard’s Inequality^[1][3]^

​		**定理1：若 $A$ 为半正定矩阵，则：**
$$
\det(A) \leqslant \prod_ia_{ii}
$$
**当且仅当 $A$ 为对角矩阵时取等号。**

​		**证：**$A$ 为 $n\times n$ 半正定矩阵，故所有对角元素 $a_{ii} \geqslant 0$，令 $D=\text{diag}(a_{11}^{1/2},a_{22}^{1/2},\cdots,a_{nn}^{1/2})$，令 $C = D^{-1}AD^{-1}$，可知 $\mathrm{tr}(C) = n$，记 $\lambda_1,\lambda_2,\cdots,\lambda_n$ 为 $C$ 的 $n$ 个特征值，由于 $C$ 亦为半正定矩阵，所以 $\lambda_1,\lambda_2,\cdots,\lambda_n$ 均为非负实数。由算术几何平均不等式^[2]^可得：
$$
\det(C) = \prod_i^n\lambda_i 
\leqslant \left(\frac{1}{n}\sum_i^n\lambda_i \right)^{n} 
= \left(\frac{1}{n}\sum_i^n c_{ii} \right)^{n}
= \left(\frac{1}{n}\mathrm{tr}(C) \right)^{n}
= 1
$$
进一步
$$
\det(A) = \det(DCD) = \det(C)[\det(D)]^2 
= \det(C)\prod_i^na_{ii} \leqslant \prod_i^na_{ii}
$$
​		**定理2：对于 $n \times n$ 矩阵 $B=[b_1,b_2,\cdots,b_n]$，有：**
$$
\left | \det(B)  \right | \leqslant \prod_i^n\|b_i\|_2
$$
​		**证：**令 $A = B^HB$，故 $A$ 为半正定的 Hermitian 矩阵
$$
\left | \det(B)  \right | ^ 2 
=[\det(B)]^*\det(B)
=\det(B^H)\det(B)
=\det(B^HB)
=\det(A)
$$
其中 $A^H$ 表示共轭转置，$A^*$ 表示复数共轭，$|x|$ 表示取模。又定理 1 可知：
$$
\det(A) \leqslant \prod_i^n a_{ii} 
= \prod_i^n \sum_j^n b_{ij}^* b_{ij}
= \prod_i^n \sum_j^n |b_{ij}|^2
= \prod_i^n\|b_i\|_2^2
$$
综合上面两个公式：
$$
\left | \det(B)  \right | \leqslant \prod_i^n\|b_i\|_2
$$

> 上面两个不等式都被称为阿达马不等式（Hadamard’s Inequality）

#### 参考文献

- [1] R. A. Horn, C. R. Johnson, Matrix Analysis, Cambridge University Press, 1985, p505~506.

- [2] [Inequality of arithmetic and geometric means - Wikipedia](https://en.wikipedia.org/wiki/Inequality_of_arithmetic_and_geometric_means)

- [3] [proof of Hadamard’s inequality - planetmath](https://planetmath.org/proofofhadamardsinequality)

