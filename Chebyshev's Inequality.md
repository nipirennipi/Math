## 切比雪夫不等式（Chebyshev's Inequality）

#### 切比雪夫不等式^[1]^

​		**定理：设 $X$ 为随机变量，且 $E(X)=\mu<+\infty$， $D(X)=\sigma^2<+\infty$，则对任意 $\varepsilon>0$，有**
$$
P(|X-\mu|\geqslant\varepsilon) \leqslant \frac{\sigma^2}{\varepsilon^2}
$$
**这就是切比雪夫不等式，它也可写为：**
$$
P(|X-\mu|<\varepsilon) \geqslant 1 - \frac{\sigma^2}{\varepsilon^2}
$$
​		**证：**设连续型随机变量（Continuous random variable）$X$ 的概率密度函数（Probability Density Function, PDF）为 $f(x)$，由概率密度函数的非负性，则
$$
\begin{aligned}
P(|X-\mu|\geqslant\varepsilon) &= \int_{|x-\mu|\geqslant\varepsilon}f(x)\mathrm{d}x \leqslant
\int_{|x-\mu|\geqslant\varepsilon} \frac{(x-\mu)^2}{\varepsilon^2} f(x)\mathrm{d}x \\
&\leqslant \int_{-\infty}^{+\infty} \frac{(x-\mu)^2}{\varepsilon^2} f(x)\mathrm{d}x
= \frac{D(X)}{\varepsilon^2} = \frac{\sigma^2}{\varepsilon^2}
\end{aligned}
$$
​		离散型随机变量（Discrete random variable）$X$ 的概率质量函数（Probability Mass Function, PMF）为 $p_X(x_k)=P(X=x_k)$ 
$(k=1,2,\cdots)$，同理由概率质量函数的非负性，则
$$
\begin{aligned}
P(|X-\mu|\geqslant\varepsilon) &= \sum_{|x_k-\mu|\geqslant\varepsilon}p_X(x_k)  \leqslant
\sum_{|x_k-\mu|\geqslant\varepsilon} \frac{(x_k-\mu)^2}{\varepsilon^2} p_X(x_k) \\
&\leqslant \sum_{k} \frac{(x_k-\mu)^2}{\varepsilon^2} p_X(x_k) = \frac{D(X)}{\varepsilon^2}
=\frac{\sigma^2}{\varepsilon^2}
\end{aligned}
$$
​		证毕。

​		**切比雪夫不等式揭示了^[2]^：若随机变量 $X$ 的方差 $D(X)$ 很小，那么 $X$ 远离数学期望 $E(X)$ 的概率很小。**更好的解释了随机变量的方差反映其分布的离散程度。

​		切比雪夫不等式的另一种形式^[3]^：**设 $X$ 为随机变量，且 $E(X)=\mu<+\infty$， $D(X)=\sigma^2<+\infty$，则对任意 $k>0$，有**
$$
P(|X-\mu|\geqslant k\sigma) \leqslant \frac{1}{k^2}
$$
当 $k>1$ 时这个不等式是有意义的，当 $k\leqslant 1$ 时显然成立。它表明了 $X$ 落在区间 $[\mu-k\sigma,\mu+k\sigma]$ 之外的概率不会大于 $1/k^2$，落在其之内的概率不会小于 $1-1/k^2$。

#### 参考文献

- [1] 刘安平, 肖海军, 2019. 概率论与数理统计[M]. 北京: 科学出版社. p92~93
- [2] [Introduction to Probability: Lecture 18: Inequalities, Convergence, and the Weak Law of Large Numbers - MIT OpenCourseWare](https://ocw.mit.edu/resources/res-6-012-introduction-to-probability-spring-2018/part-ii-inference-limit-theorems/MITRES_6_012S18_L18.pdf). p4~5
- [3] [Chebyshev's inequality - Wikipedia](https://en.wikipedia.org/wiki/Chebyshev%27s_inequality)

