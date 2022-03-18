## 拉普拉斯算子（Laplace Operator）

#### 拉普拉斯算子

​		**定义：若函数 $f:\mathbb{R}^n\to\mathbb{R}$ 是一个二次可微的实值函数，那么 $f$ 的拉普拉斯算子定义为**
$$
\Delta f = \nabla^2 f = \nabla \cdot \nabla f
$$
$\Delta f$ 也是一个实值函数，其中
$$
\nabla = 
\begin{pmatrix}
\displaystyle
\frac{\partial}{\partial x_1},
\frac{\partial}{\partial x_2},
\cdots,
\frac{\partial}{\partial x_n}
\end{pmatrix}
$$
​		通过定义可以看出 $f$ 的拉普拉斯算子其实就是 $f$ 的梯度（Gradient）的散度（Divergence）
$$
\Delta f = \mathrm{div}(\mathrm{grad}(f))
$$
​		在笛卡尔坐标系中，可以给出更加直观的定义
$$
\Delta f = \sum_{i=1}^{n} \displaystyle
\frac{\partial^2 f}{\partial x^2_i}
$$
​		拉普拉斯算子的物理意义^[1]^，**函数 $f$ 在以点 $p$ 为圆心的邻域边界上的平均值与 $f(p)$ 之差可以由 $\Delta f(p)$ 来度量。**

#### 离散拉普拉斯算子（Discrete Laplace Operator）

​		使用有限差分法（Finite difference method）^[3]^，可以得到拉普拉斯算子的近似，称之为离散拉普拉斯算子。函数 $f(x,y):\mathbb{R}^2\to\mathbb{R}$，其离散拉普拉斯算子可以表示为
$$
\begin{aligned}
\Delta f(x,y) 
&= \displaystyle\frac{\partial^2 f}{\partial x^2} + \displaystyle\frac{\partial^2 f}{\partial y^2} \\
&\approx \frac{f(x+h,y) + f(x-h,y) - 2f(x,y)}{h^2} + \frac{f(x,y+h) + f(x,y-h) - 2f(x,y)}{h^2} \\
&= \frac{f(x+h,y) + f(x-h,y) - 4f(x,y) + f(x,y+h) + f(x,y-h)}{h^2}
\end{aligned}
$$
继续对其进行变形
$$
\begin{aligned}
\Delta f(x,y) &\approx \frac{f(x+h,y) + f(x-h,y) - 4f(x,y) + f(x,y+h) + f(x,y-h)}{h^2} \\
&= \frac{4}{h^2} \left[\frac{f(x+h,y) + f(x-h,y) f(x,y+h) + f(x,y-h)}{4} - f(x,y)  \right]
\end{aligned}
$$
可以看出 $f(x,y)$ 的离散拉普拉斯算子描述了 $f$ 在点 $(x,y)$ 的邻域边界上的平均值与 $f(x,y)$ 之差。

#### 参考文献

- [1] [Laplace operator - Wikipedia](https://en.wikipedia.org/wiki/Laplace_operator)
- [2] [Discrete Laplace operator - Wikipedia](https://en.wikipedia.org/wiki/Discrete_Laplace_operator)
- [3] [Finite difference method#Example:_The_Laplace_operator - Wikipedia](https://en.wikipedia.org/wiki/Finite_difference_method#Example:_The_Laplace_operator)
- [4] [为什么 空间二阶导（拉普拉斯算子）这么重要？ - 知乎](https://www.zhihu.com/question/26822364/answer/1831093667)

