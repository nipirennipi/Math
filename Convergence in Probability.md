## 依概率收敛（Convergence in Probability）

#### 依概率收敛

​		**定义：设 $X_1,X_2,\cdots,X_n,\cdots$ 是随机变量序列，$X$ 为另一随机变量，若对任意 $\varepsilon>0$，有：**
$$
\lim_{n\to\infty} P(|X_n-X|<\varepsilon)=1
$$
**则称随机变量序列 $X_1,X_2,\cdots,X_n,\cdots$ 依概率收敛于 $X$，记作 $X_n \xrightarrow{P}X$**

​		或者我们可以这样定义它：$P_n(\varepsilon)$ 是事件 $\{|X_n-X|\geqslant\varepsilon\}$ 发生的概率，若对任意 $\varepsilon>0$，任意 $\delta>0$，存在正整数 $N$，使得对于任意 $n>N$，都有 $P_n(\varepsilon)<\delta$，则称 $X_n \xrightarrow{P}A$

​		依概率收敛的意思是，当 $n$ 无限增大时，对任意 $\varepsilon>0$，事件 $\{|X_n-X|<\varepsilon\}$ 发生的概率无限接近 $1$，但并不排除事件 $\{|X_n-X|\geqslant\varepsilon\}$ 发生，只是发生的可能性很小。

#### 参考文献：

- [1] 刘安平, 肖海军, 2019. 概率论与数理统计[M]. 北京: 科学出版社. p93
- [2] [Convergence of random variables#Convergence_in_probability - Wikipedia](https://en.wikipedia.org/wiki/Convergence_of_random_variables#Convergence_in_probability)
- [3] [14.381 Statistics Fall, 2004: Handout # 6 - MIT](http://web.mit.edu/14.381/www/ho6.pdf)
- [4] [Convergence in Probability - probabilitycourse](https://www.probabilitycourse.com/chapter7/7_2_5_convergence_in_probability.php)


