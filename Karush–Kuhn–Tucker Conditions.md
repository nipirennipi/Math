## KKT（Karush–Kuhn–Tucker Conditions）

#### 拉格朗日乘子法（Lagrange Multipliers）

​		考虑一个等式约束优化问题，$\boldsymbol{x} \in \mathbb{R}^{d}$，希望寻找 $\boldsymbol{x^*}$ 使得目标函数 $f(\boldsymbol{x})$ 取得最小值，同时满足等式约束 $g(\boldsymbol{x})=0$，即
$$
\begin{aligned}
\min_{\boldsymbol{x}}\quad & f(\boldsymbol{x}) \\
\text{s.t.}\quad & g(\boldsymbol{x}) = 0 
\end{aligned}
$$
在最优解 $\boldsymbol{x^*}$ 处，必然有 $\nabla f(\boldsymbol{x^*})$ 正交于 $g(\boldsymbol{x})=0$ 所确定的 $d-1$ 维约束曲面，即 $\nabla f(\boldsymbol{x^*})$ 与 $\nabla g(\boldsymbol{x^*})$ 方向相同或者相反，可令 $\lambda$ 使得
$$
\nabla f(\boldsymbol{x^*}) + \lambda \nabla g(\boldsymbol{x^*}) = \boldsymbol{0}
$$
其中 $\lambda$ 被称为拉格朗日乘子，再定义拉格朗日函数
$$
L(\boldsymbol{x},\lambda) =  f(\boldsymbol{x}) + \lambda g(\boldsymbol{x})
$$
从而将原等式约束优化问题转化为对 $L(\boldsymbol{x},\lambda)$ 的无约束优化问题
$$
\min_{\boldsymbol{x},\lambda} \quad L(\boldsymbol{x},\lambda)
$$
取得最优解 $\boldsymbol{x^*}$ 的必要条件
$$
\begin{aligned}
\nabla_\boldsymbol{x} L(\boldsymbol{x}, \lambda) &= 
\nabla f(\boldsymbol{x}) + \lambda \nabla g(\boldsymbol{x}) = \boldsymbol{0} \\
\nabla_\boldsymbol{\lambda} L(\boldsymbol{x}, \lambda) &= g(\boldsymbol{x}) = 0
\end{aligned}
$$
求解上面方程组，并对解进一步判断，即可得 $\boldsymbol{x^*}$。

​		**考虑有 $k$ 个等式约束条件与 $d$ 个变量的优化问题，拉格朗日乘子法可以将其等价转化为具有 $d + k$ 个变量的无约束优化问题。**

#### KKT

​		考虑一个不等式优化问题，$\boldsymbol{x} \in \mathbb{R}^{d}$，希望寻找 $\boldsymbol{x^*}$ 使得目标函数 $f(\boldsymbol{x})$ 取得最小值，同时满足等式约束 $g(\boldsymbol{x})\leqslant 0$，即
$$
\begin{aligned}
\min_{\boldsymbol{x}}\quad & f(\boldsymbol{x}) \\
\text{s.t.}\quad & g(\boldsymbol{x}) \leqslant 0 
\end{aligned}
$$
为了叙述方便，定义可行域（Feasible Set）$F = \{\boldsymbol{x}|g(\boldsymbol{x}) \leqslant 0\}$

- 当最优解 $\boldsymbol{x^*}$ 在区域 $g(\boldsymbol{x}) < 0$ 中时，$g(\boldsymbol{x})$ 约束失效，直接令 $\nabla f(\boldsymbol{x})=\boldsymbol{0}$ 来求解 $\boldsymbol{x^*}$，这等价于令 $\lambda=0$，然后利用必要条件$\nabla_\boldsymbol{x} L(\boldsymbol{x}, \lambda)=\boldsymbol{0}$ 来求解 $\boldsymbol{x^*}$。
- 当最优解 $\boldsymbol{x^*}$ 在边界 $g(\boldsymbol{x}) = 0$ 上时， $\nabla f(\boldsymbol{x^*})$ 与 $\nabla g(\boldsymbol{x^*})$ 的方向必然相反，因为要使得 $f(\boldsymbol{x})$ 最小化，$\nabla f(\boldsymbol{x^*})$ 的方向必然是指向可行域 $F$ 内部，而 $\nabla g(\boldsymbol{x^*})$ 的方向指向 $F$ 外部，它们都与曲面 $g(\boldsymbol{x}) = 0$ 正交。所以存在常数 $\lambda > 0$，使得 $\nabla f(\boldsymbol{x^*}) + \lambda \nabla g(\boldsymbol{x^*}) = \boldsymbol{0}$。

综合上面两种最优解的出现情形，$\lambda g(\boldsymbol{x}) = 0$ 与 $\lambda \geqslant 0$ 恒成立。因此取得最优解 $\boldsymbol{x^*}$ 的必要条件为
$$
\begin{cases}
\nabla_\boldsymbol{x} L(\boldsymbol{x}, \lambda)=\boldsymbol{0} \\\\

g(\boldsymbol{x}) \leqslant 0 \\\\

\lambda \geqslant 0 \\\\

\lambda g(\boldsymbol{x}) = 0
\end{cases}
$$
上式被称为 **KKT 条件**。

​		可以将其推广到多个约束，考虑具有 $m$ 个不等式约束与 $n$ 个等式约束的优化问题
$$
\begin{aligned} 
\min_{\boldsymbol{x}}\quad & f(\boldsymbol{x}) \\
\text{s.t.}\quad & g_i(\boldsymbol{x}) \leqslant 0 \quad(i=1,\dots,m) \\
&h_j(\boldsymbol{x}) = 0 \quad(j=1,\dots,l)
\end{aligned}
$$
引入拉格朗日乘子 $\boldsymbol{\mu} = (\mu_1,\dots,\mu_m)^T$，$\boldsymbol{\lambda} = (\lambda_1,\dots,\lambda_l)^T$，对应的拉格朗日函数为
$$
L(\boldsymbol{x},\boldsymbol{\mu},\boldsymbol{\lambda})=
f(\boldsymbol{x}) +
\sum_{i=1}^m\mu_ig_i(\boldsymbol{x}) + \sum_{j=1}^l\lambda_jh_j(\boldsymbol{x})
$$
引入 KKT 条件

- **定常方程式（Stationarity）**
    $$
    \nabla_\boldsymbol{x}L(\boldsymbol{x},\boldsymbol{\mu},\boldsymbol{\lambda}) =
    \nabla f(\boldsymbol{x}) +
    \sum_{i=1}^m\mu_i \nabla g_i(\boldsymbol{x}) + 
    \sum_{j=1}^l\lambda_j \nabla h_j(\boldsymbol{x}) = \boldsymbol{0}
    $$

- **原始可行性（Primal feasibility）**
    $$
    \begin{aligned} 
    g_i(\boldsymbol{x}) &\leqslant 0 \quad(i=1,\dots,m) \\
    h_j(\boldsymbol{x}) &= 0 \quad(j=1,\dots,l)
    \end{aligned}
    $$

- **对偶可行性（Dual feasibility）**
    $$
    \mu_i \geqslant 0 \quad(i=1,\dots,m)
    $$

- **互补松弛性（Complementary slackness）**
    $$
    \mu_i  g_i(\boldsymbol{x}) = 0 \quad(i=1,\dots,m)
    $$

可以发现，当 $m=0$ 时，KKT 退化为拉格朗日乘子法 ，也可以说 KKT 推广了只能求解等式约束优化问题的拉格朗日乘子法。

**KKT 的矩阵表示**

​		引入 $\boldsymbol{g}(\boldsymbol{x}) = (g_1(\boldsymbol{x}),\dots,g_m(\boldsymbol{x}))^T$ 与 $\boldsymbol{h}(\boldsymbol{x}) = (h_1(\boldsymbol{x}),\dots,h_l(\boldsymbol{x}))^T$，KKT 条件可以矩阵表示为
$$
\begin{cases}
\nabla_\boldsymbol{x}L(\boldsymbol{x},\boldsymbol{\mu},\boldsymbol{\lambda}) =
\nabla f(\boldsymbol{x}) +
[\mathrm{D}\boldsymbol{g}(\boldsymbol{x})]^T\boldsymbol{\mu} + 
[\mathrm{D}\boldsymbol{h}(\boldsymbol{x})]^T\boldsymbol{\lambda}
=\boldsymbol{0} \\\\

\boldsymbol{g}(\boldsymbol{x}) \leqslant \boldsymbol{0} \\
\boldsymbol{h}(\boldsymbol{x}) = \boldsymbol{0}\\\\

\boldsymbol{\mu} \geqslant \boldsymbol{0} \\\\

\boldsymbol{\mu}^T \boldsymbol{g}(\boldsymbol{x}) 
= 0
\end{cases}
$$
其中 $\mathrm{D}\boldsymbol{g}(\boldsymbol{x})$ 是 $\boldsymbol{g}(\boldsymbol{x})$ 的雅克比矩阵（Jacobian Matrix）。

#### 参考文献

- [1] [Karush–Kuhn–Tucker conditions - Wikipedia](https://en.wikipedia.org/wiki/Karush%E2%80%93Kuhn%E2%80%93Tucker_conditions#Regularity_conditions_(or_constraint_qualifications))
- [2] [Karush-Kuhn-Tucker (KKT)条件 - 知乎](https://zhuanlan.zhihu.com/p/38163970)
