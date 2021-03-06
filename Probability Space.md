## 概率空间（Probability Space）

#### 测理论（Measure theory）基础^[1]^

​		**定义^[3][4]^：现有集合 $\Omega$，$\mathcal{F}$ 为关于 $\Omega$ 子集的集合，当 $\mathcal{F}$ 满足下列条件时，称 $\mathcal{F}$ 为 $\Omega$ 的一个 ==$\sigma$-代数（$\sigma$-algebra, or $\sigma$-field）==：**

- **（i）$\Omega \in \mathcal{F}$**
- **（ii）若 $A \in \mathcal{F}$，则 $A^c \in \mathcal{F}$**
- **（iii）若 $A_1,A_2,\cdots \in \mathcal{F}$，则 $\displaystyle\bigcup_{i=1}^{\infty}A_i \in \mathcal{F}$**

其中 $A_c$ 表示给定全集 $\Omega$ 下，$A$ 的补集。由（ii），我们可以将（i）替换为 $\varnothing \in \mathcal{F}$。

​		**命题：**若 $A_1,A_2,\cdots,A_n \in \mathcal{F}$，则 $\displaystyle\bigcup_{i=1}^{n}A_i \in \mathcal{F}$

​		**证：**由（iii）
$$
A_1\cup A_2\cup \cdots\cup A_n = A_1\cup A_2\cup \cdots\cup A_n\cup \varnothing \cup \varnothing \cup \cdots
\in \mathcal{F}
$$
​		**推论：$\Omega$ 上的任意 $\sigma$-代数 $\mathcal{F}$ 一定满足**
$$
\{\varnothing,\Omega\} \subseteq \mathcal{F} \subseteq 2^{\Omega}
$$
其中 $2^\Omega$ 为 $\Omega$ 的幂集。

​		**定义^[4][10]^：现有集合 $\Omega$，$\mathcal{C}$ 为关于 $\Omega$ 子集的集合（$\mathcal{C}$ 不必是 $\sigma$-代数），存在最小的 $\sigma$-代数 $\mathcal{F}$，满足 $\mathcal{C}\subseteq\mathcal{F}$，则称 $\mathcal{F}$ 为==由 $\mathcal{C}$ 生成的 $\sigma$-代数（the $\sigma$-field generated by）==，记为 $\sigma(\mathcal{C})。$**

​		**定义^[5]^：现有集合 $\Omega$，$\mathcal{F}$ 为 $\Omega$ 的一个 $\sigma$-代数，称 $(\Omega,\mathcal{F})$ 为一个==可测空间（Measurable space）==。**

​		**定义^[6]^：在可测空间 $(\Omega,\mathcal{F})$ 上的==测度（Measure）==被定义为满足下列条件的函数 $\mu:\mathcal{F}\to[0,+\infty)$**

- **（i）零空集（Null empty set）：$\mu(\varnothing) = 0$**

- **（ii）可数可加性（Countable additivity）：若 $A_1,A_2,\cdots \in \mathcal{F}$ 且两两互不相交，则**
    $$
    \sum_{i=1}^{\infty}\mu(A_i) = \mu\left(\bigcup_{i=1}^{\infty} A_i\right)
    $$

​		**命题：**若 $A_1,A_2,\cdots,A_n \in \mathcal{F}$ 且两两互不相交，则
$$
\sum_{i=1}^{n}\mu(A_i) = \mu\left(\bigcup_{i=1}^{n} A_i\right)
$$
​		**证：**
$$
\begin{aligned}
\sum_{i=1}^{n}\mu(A_i) &= 
\mu(A_1) + \mu(A_2) + \cdots + \mu(A_n) + 0 + 0 + \cdots \\
&= \mu(A_1) + \mu(A_2) + \cdots + \mu(A_n) + \mu(\varnothing) + \mu(\varnothing) + \cdots \\
&= \mu \left(A_1 \cup A_2 \cup \cdots \cup A_n \cup \varnothing \cup \varnothing \cup \cdots \right) \\
&=\mu\left(\bigcup_{i=1}^{n} A_i\right)
\end{aligned}
$$
​		**命题：**若 $A \subseteq B$，则 $\mu(A)\leqslant\mu(B)$

​		**证：**由 $A \subseteq B$ 得 $B=A\cup(B-A)$，又 $A$ 与 $(B-A)$ 不相交
$$
\mu(B) = \mu(A\cup(B-A)) = \mu(A) + \mu(B-A)
$$
又 $\mu(B-A)\geqslant0$，故 $\mu(A)\leqslant\mu(B)$，证毕。

​		**定义^[7]^：现有可测空间 $(\Omega,\mathcal{F})$，$\mu$ 为 $(\Omega,\mathcal{F})$ 上的一个测度，则称三元组 $(\Omega,\mathcal{F},\mu)$ 为==测度空间（Measure space）==。**

#### 概率空间（Probability space）^[8][9]^

​		概率空间是一种特殊的测度空间。

​		**定义：现有测度空间 $\displaystyle(\Omega,\mathcal{F},P)$，若测度 $P$ 满足：**

- **（i）$P:\mathcal{F}\to[0,1]$**
- **（ii）$P(\varnothing)=0$，$P(\Omega)=1$**
- **（iii）若 $A_1,A_2,\cdots \in \mathcal{F}$ 且两两互不相交，则**

$$
\sum_{i=1}^{\infty}\mu(A_i) = \mu\left(\bigcup_{i=1}^{\infty} A_i\right)
$$

**则称测度空间 $\displaystyle(\Omega,\mathcal{F},P)$ 为==概率空间==**。

​		在概率论中，一个概率空间提供了一个随机过程或随机实验的形式化模型，对于概率空间 $\displaystyle(\Omega,\mathcal{F},P)$ 的三个组成部分进一步描述：

- $\Omega$：样本空间（Sample space），是一个随机试验（Experiment）所有可能出现的结果构成的集合。
- $\mathcal{F}$：事件（Event）的集合，事件是样本空间 $\Omega$ 的一个子集。
- $P$：概率测度（Probability measure），为 $\mathcal{F}$ 中每一个事件赋值一个概率，范围为 $[0,1]$。

#### 参考文献

- [1] [Almost Sure Convergence of a Sequence of Random Variables - University of Colorado Boulder](https://www.colorado.edu/amath/sites/default/files/attached-files/almost_sure_conv.pdf)
- [2] [18.445 Introduction to Stochastic Processes, Lecture 15 - MIT OpenCourseWare](https://ocw.mit.edu/courses/mathematics/18-445-introduction-to-stochastic-processes-spring-2015/lecture-notes/MIT18_445S15_lecture15.pdf). p3
- [3] [Sigma-Algebras - LSU Math](https://www.math.lsu.edu/~sengupta/7312s02/sigmaalg.pdf)
- [4] [σ-algebra - Wikipedia](https://en.wikipedia.org/wiki/%CE%A3-algebra)
- [5] [Measurable space - Wikipedia](https://en.wikipedia.org/wiki/Measurable_space)
- [6] [Measure - Wikipedia](https://en.wikipedia.org/wiki/Measure)
- [7] [Measurable space - Wikipedia](https://en.wikipedia.org/wiki/Measurable_space)
- [8] [Probability measure - Wikipedia](https://en.wikipedia.org/wiki/Probability_measure)
- [9] [Probability space - Wikipedia](https://en.wikipedia.org/wiki/Probability_space)
- [10] [6.436J / 15.085J Fundamentals of Probability, Lecture 1: Probabilistic Models and Probability Measures - MIT OpenCourseWare](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-436j-fundamentals-of-probability-fall-2018/lecture-notes/MIT6_436JF18_lec01.pdf). p6

