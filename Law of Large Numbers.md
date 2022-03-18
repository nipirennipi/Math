## 大数定理（Law of Large Numbers）

​		我们都能直观地理解，在独立重复试验（Independent repeated trials）中，随着试验次数的增加，大量试验结果的算术平均值应该越接近其期望值。而大数定理可以从数学上精确描述这一直觉。

#### 弱大数定理（weak law of large numbers）

​		弱大数定理也被称为辛钦大数定理（Khinchin's law）。

​		**定理：设 $X_1,X_2,\cdots,X_n,\cdots$ 是独立同分布（independent and identically distributed, i.id.）的随机变量序列，且 $E(X_i)=\mu<+\infty$，令 $\overline{X_n}=\displaystyle\frac{1}{n}\sum_{i=1}^nX_i$，则对任意的 $\varepsilon>0$，有**
$$
\color{red}\lim_{n\to \infty}P\left(\left|\overline{X_n}-\mu\right|<\varepsilon\right)=1
$$
​		**证^[3]^：**由于 $X_1,X_2,\cdots,X_n,\cdots$ 是独立同分布的随机变量序列，记 $D(X_i)=\sigma^2<+\infty$，可知
$$
\begin{aligned}
E(\overline{X_n}) &= E\left(\frac{1}{n} \sum_{i=1}^{n} X_i \right) 
= \frac{1}{n} \sum_{i=1}^{n} E\left( X_i \right) =\mu \\

D(\overline{X_n}) &= D\left(\frac{1}{n} \sum_{i=1}^{n} X_i \right)
= \frac{1}{n^2} \sum_{i=1}^{n} D\left( X_i \right) = \frac{\sigma^2}{n} \\
\end{aligned}
$$
由切比雪夫不等式，对任意的 $\varepsilon > 0$，有
$$
P\left(\left|\overline{X_n}-\mu\right|<\varepsilon\right)
\geqslant 1 - \frac{\sigma^2}{n \varepsilon^2}
$$
又 $P\left(\left|\overline{X_n}-\mu\right|<\varepsilon\right) \leqslant 1$，由夹逼定理：
$$
\lim_{n\to \infty}P\left(\left|\overline{X_n}-\mu\right|<\varepsilon\right)=1
$$
证毕。

​		弱大数定理表明：独立同分布的随机变量序列的算术平均值依概率收敛于（Convergence in Probability）随机变量的期望值。

#### 强大数定理（strong law of large numbers）^[4]^

​		强大数定理也被称为柯尔莫哥洛夫大数定理（Kolmogorov's law）。

​		**定理：设 $X_1,X_2,\cdots,X_n,\cdots$ 是独立同分布的随机变量序列，且 $E(X_i)=\mu<+\infty$，令 $\overline{X_n}=\displaystyle\frac{1}{n}\sum_{i=1}^nX_i$，则**
$$
\color{red}P\left(\lim_{n\to \infty} \overline{X_n} =\mu \right)=1
$$
​		强大数定理表明：独立同分布的随机变量序列的算术平均值几乎必然收敛于（Almost Sure Convergence）随机变量的期望值。

#### 伯努利大数定理

​		**定理：设在 $n$ 次独立重复试验中事件 $A$ 发生的次数为 $n_A$，$A$ 在每次实验中发生的概率为 $p$，则对任意的 $\varepsilon>0$，有**
$$
\color{red}\lim_{n\to \infty}P\left(\left|\frac{n_A}{n}-p\right|<\varepsilon\right)=1
$$
​		**证：**令随机变量 $X_i\ (i=1,2,\cdots,n)$ 表示第 $i$ 次实验中事件 $A$ 发生的次数，可知随机变量序列 $X_1,X_2,\cdots,X_n,\cdots$ 相互独立且同服从伯努利分布，$E(X_i) = p$。又
$$
n_A = \sum_{i=1}^{n}X_{i}\qquad 
\frac{n_A}{n}=\frac{1}{n} \sum_{i=1}^{n}X_{i}
$$
由弱大数定理即可得证，证毕。

​		伯努利大数定理表明：在大量的独立重复试验中，事件 $A$ 的发生频率依概率收敛于事件 $A$ 发生的概率。

#### 切比雪夫大数定理

​		**定理：设 $X_1,X_2,\cdots,X_n,\cdots$ 是相互独立的随机变量序列，且 $E(X_i)=\mu_i<+\infty$，$D(X_i)\leqslant l<+\infty$，令 $\overline{X_n}=\displaystyle\frac{1}{n}\sum_{i=1}^nX_i$，则对任意的 $\varepsilon>0$，有**
$$
\color{red}
\lim_{n\to\infty}P\left( \left| \overline{X_n} - \frac{1}{n}\sum_{i=1}^{n} \mu_i \right| < \varepsilon \right) =1
$$
​		**证：**由于 $X_1,X_2,\cdots,X_n,\cdots$ 是相互独立的随机变量序列，可知
$$
\begin{aligned}
E(\overline{X_n}) &= E\left(\frac{1}{n} \sum_{i=1}^{n} X_i \right) = \frac{1}{n} \sum_{i=1}^{n} E\left( X_i \right) = \frac{1}{n} \sum_{i=1}^{n} \mu_i \\
D(\overline{X_n}) &= D\left(\frac{1}{n} \sum_{i=1}^{n} X_i \right)= \frac{1}{n^2} \sum_{i=1}^{n} D\left( X_i \right) \leqslant \frac{l}{n}  \\
\end{aligned}
$$
由切比雪夫不等式，对任意的 $\varepsilon > 0$，有
$$
P\left(\left| \overline{X_n} - \frac{1}{n} \sum_{i=1}^{n} \mu_i \right| < \varepsilon \right) 
\geqslant 1 - \frac{1}{\varepsilon^2}D(\overline{X_n}) 
\geqslant 1 - \frac{l}{n\varepsilon^2} \\
$$
又 $P\left(\left| \overline{X_n} - \frac{1}{n} \sum_{i=1}^{n} \mu_i \right| < \varepsilon \right)  \leqslant 1$，由夹逼定理：
$$
\lim_{n\to\infty}P\left(\left| \overline{X_n} - \frac{1}{n} \sum_{i=1}^{n} \mu_i \right| < \varepsilon \right) = 1
$$
证毕。

​		相比于弱大数定理，切比雪夫大数定理只要求随机变量序列相互独立。

#### 参考文献

- [1] 刘安平, 肖海军, 2019. 概率论与数理统计[M]. 北京: 科学出版社. p93~95
- [2] [Law of large numbers - Wikipedia](https://en.wikipedia.org/wiki/Law_of_large_numbers)
- [3] [Law of Large Numbers - probabilitycourse](https://www.probabilitycourse.com/chapter7/7_1_1_law_of_large_numbers.php)
- [4] [Almost Sure Convergence - probabilitycourse](https://www.probabilitycourse.com/chapter7/7_2_7_almost_sure_convergence.php)


