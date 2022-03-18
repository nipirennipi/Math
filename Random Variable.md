## 随机变量（Random Variable）

#### 可测函数（Measurable Functions）^[1][2]^

​		**定义：现有可测空间 $(\Omega,\mathcal{F})$ 与 $(S,\mathcal{A})$，若存在函数 $f:\Omega\to S$，满足对任意 $A \in \mathcal{A}$，有 $f^{-1}(A) \in \mathcal{F}$，则称函数 $f$ 是可测的（Measurable）。其中 $f^{-1}(A)$ 表示 $A\subseteq S$ 在 $f$ 之下的原像^[3]^（Preimage, or Inverse image），即**
$$
f^{-1}(A):=\{\omega \in \Omega|f(\omega) \in A \}
$$

#### 随机变量

​		**定义^[4][5]^：现有概率空间 $(\Omega,\mathcal{F},P)$ 与可测空间 $(\mathbb{R},\mathcal{B(\mathbb{R})})$ 若函数 $X:\Omega\to \mathbb{R}$ 满足对任意 $B\in\mathcal{B(\mathbb{R})}$，有 $f^{-1}(B)\in\mathcal{F}$，则称 $X$ 为随机变量。**

​		其中 $\mathcal{B(\mathbb{R})}$ 表示 $\mathbb{R}$ 的博雷尔代数^[6\ p3][7][8]^（Borel algebra，or Borel $\sigma$-algebra），记集合 $\mathcal{C}$ 为 $R$ 上所有开区间 $(a,b)$ 的集合，则 $\mathcal{B(\mathbb{R})}$ 为由 $\mathcal{C}$ 生成的 $\sigma$-代数。

​		或者直接利用可测函数来定义^[6\ p6]^：现有概率空间 $(\Omega,\mathcal{F},P)$，随机变量 $X$ 为从样本空间到 $\Omega$ 到 $\mathbb{R}$ 的可测函数。

​		**定义^[9]^：若随机变量 $X$ 的像^[3]^（image）是可数的（countable），则称 $X$ 为离散随机变量（discrete random variable）。**

​		**定义^[10][11]^：对于随机变量 $X$，若存在非负函数 $f(x)$，对于任意 $x \in \mathbb{R}$，有**
$$
P(X\leqslant x)=\int_{-\infty}^x f(x)\mathrm{d}x
$$
**则称 $X$ 为连续随机变量（continuous random variable），$f(x)$ 为概率密度函数（ Probability Density Function, PDF）。**

#### 参考文献

- [1] [Measurable function - Wikipedia](https://en.wikipedia.org/wiki/Measurable_function)
- [2] [Measurable Functions, Random Variables, and Integration - CMU Statistics](https://www.stat.cmu.edu/~arinaldo/Teaching/36752/S18/Notes/lec_notes_2.pdf). p1
- [3] [Image (mathematics) - Wikipedia](https://en.wikipedia.org/wiki/Image_(mathematics)#Inverse_image)
- [4] [Fundamental Tools - Probability Theory II - University of Warwick](https://warwick.ac.uk/fac/sci/statistics/staff/research_students/norgilas/fundamental_tools/day_2.pdf). p3
- [5] [Random Variables and Measurable Functions - University of Waterloo](https://sas.uwaterloo.ca/~dlmcleis/s901/chapt3.pdf). p1
- [6] [Almost Sure Convergence of a Sequence of Random Variables - University of Colorado Boulder](https://www.colorado.edu/amath/sites/default/files/attached-files/almost_sure_conv.pdf)
- [7] [Borel set - Wikipedia](https://en.wikipedia.org/wiki/Borel_set)
- [8] [probability - Borel $\sigma$-Algebra on Real Numbers and interval elements - Mathematics Stack Exchange](https://math.stackexchange.com/questions/1090217/borel-sigma-algebra-on-real-numbers-and-interval-elements)
- [9] [Random variable - Wikipedia](https://en.wikipedia.org/wiki/Random_variable)
- [10] 刘安平, 肖海军, 2019. 概率论与数理统计[M]. 北京: 科学出版社. p34
- [11] [Introduction to Probability and Statistics, Reading 5b: Continuous Random Variables - MIT OpenCourseWare](https://ocw.mit.edu/courses/mathematics/18-05-introduction-to-probability-and-statistics-spring-2014/readings/MIT18_05S14_Reading5b.pdf). p2