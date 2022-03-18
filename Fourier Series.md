## 傅里叶级数（Fourier Series）

#### 傅里叶级数^[1]^

​		考虑周期为 $T$ 的实值函数 $f(t)$，它可以描述为正弦和余弦曲线的加权和，这个和被称为傅里叶级数，它具有三种形式。

##### 振幅-相位形式（amplitude-phase form）

$$
\color{red}f(t) = \frac{A_0}{2} +
\sum_{n=1}^\infty A_n\cos\left(\frac{2\pi n}{T}t-\varphi_n \right)
$$

##### 正弦-余弦形式（sine-cosine form）

​		相比于振幅-相位形式，这种形式更加常用
$$
\color{red}{f(t) = \frac{a_0}{2}+\sum_{n=1}^\infty\left[
	a_n \cos \left(
			\frac{2 \pi n}{T}t
		\right)
	+ b_n \sin \left(
			\frac{2 \pi n}{T}t
		\right)
\right]}
$$
其中
$$
\color{red}\begin{aligned}
a_n &= \frac{2}{T} \int_{-\frac{T}{2}}^{\frac{T}{2}}
f(t) \cos \left(\frac{2 \pi n}{T}t\right) \mathrm{d} t 
&& n = 0,1,\cdots \\

b_n &= \frac{2}{T} \int_{-\frac{T}{2}}^{\frac{T}{2}}
f(t) \sin \left(\frac{2 \pi n}{T}t\right) \mathrm{d} t
&& n = 1,2,\cdots \\
\end{aligned}
$$
​		正弦-余弦形式由振幅-相位形式变形而得
$$
A_n\cos\left(\frac{2\pi n}{T}t-\varphi_n \right) =
	A_n\cos(\varphi_n) \cos \left(
			\frac{2 \pi n}{T}t
		\right)
	+ A_n\sin(\varphi_n) \sin \left(
			\frac{2 \pi n}{T}t
		\right)
$$
令 $a_n = A_n\cos(\varphi_n)$，$b_n = A_n\sin(\varphi_n)$，从而有
$$
\sqrt{{a_n}^2 + {b_n}^2} = A_n \quad \tan(\varphi_n) = \frac{b_n}{a_n}
$$

##### 指数形式（exponential form）^[2]^

$$
\color{red}f(t) = \sum_{n=-\infty}^{\infty}c_n
e^{i\frac{2\pi n}{T}t}
$$

其中
$$
\color{red}
\begin{aligned}
c_n = \frac{1}{T} \int_{-\frac{T}{2}}^{\frac{T}{2}}f(t)
e^{-i\frac{2\pi n}{T}t} \mathrm{d}t  &&n =0,\pm1,\pm2,\cdots \\
\end{aligned}
$$
​		下面我们推导指数形式与正弦-余弦形式是等价的，考虑欧拉公式（Eualr’s Formula）
$$
e^{i\theta} = \cos\theta + i\sin\theta
$$

- 当 $n>0$ 时
    $$
    \begin{aligned}
    c_n &= \frac{1}{T} \int_{-\frac{T}{2}}^{\frac{T}{2}}f(t)
    e^{-i\frac{2\pi n}{T}t} \mathrm{d}t \\
    &= \frac{1}{T} \int_{-\frac{T}{2}}^{\frac{T}{2}}
    f(t) \cos \left(\frac{2 \pi n}{T}t\right) \mathrm{d} t -
    i\cdot \frac{1}{T} \int_{-\frac{T}{2}}^{\frac{T}{2}}
    f(t) \sin \left(\frac{2 \pi n}{T}t\right) \mathrm{d} t \\
    & = \frac{1}{2}(a_n - i b_n)
    \end{aligned}
    $$

- 当 $n<0$ 时
    $$
    \begin{aligned}
    c_n &= \frac{1}{T} \int_{-\frac{T}{2}}^{\frac{T}{2}}f(t)
    e^{i\frac{2\pi n}{T}t} \mathrm{d}t \\
    &= \frac{1}{T} \int_{-\frac{T}{2}}^{\frac{T}{2}}
    f(t) \cos \left(\frac{2 \pi n}{T}t\right) \mathrm{d} t +
    i\cdot \frac{1}{T} \int_{-\frac{T}{2}}^{\frac{T}{2}}
    f(t) \sin \left(\frac{2 \pi n}{T}t\right) \mathrm{d} t \\
    & = \frac{1}{2}(a_{-n} + i b_{-n})
    \end{aligned}
    $$

- 当 $n=0$ 时
    $$
    \begin{aligned}
    c_n &= \frac{1}{2}a_0
    \end{aligned}
    $$

- 

可知 $c_n$ 与 $c_{-n}$ 互为共轭，从而
$$
\begin{aligned}
f(t) &= \sum_{n=-\infty}^{\infty}c_n e^{i\frac{2\pi n}{T}t} \\
&=c_0 + \sum_{n=1}^{\infty}c_ne^{i\frac{2\pi n}{T}t} +
	\sum_{n=-\infty}^{-1}c_ne^{i\frac{2\pi n}{T}t}  \\
&=c_0 +\sum_{n=1}^{\infty}c_ne^{i\frac{2\pi n}{T}t} +
	\sum_{n=1}^{\infty}c_{-n}e^{-i\frac{2\pi n}{T}t}  \\
&=\frac{a_0}{2}+\sum_{n=1}^{\infty}  \frac{a_n-ib_n}{2} 
	\left( \cos \left(\frac{2 \pi n}{T}t\right) + \sin \left(\frac{2 \pi n}{T}t\right)  \right) +
	\sum_{n=1}^{\infty} \frac{a_n+ib_n}{2} 
	\left( \cos \left(\frac{2 \pi n}{T}t\right) - \sin \left(\frac{2 \pi n}{T}t\right)  \right) \\
&= \frac{a_0}{2}+\sum_{n=1}^\infty\left[
	a_n \cos \left(
			\frac{2 \pi n}{T}t
		\right)
	+ b_n \sin \left(
			\frac{2 \pi n}{T}t
		\right)
\right]
\end{aligned}
$$

> 观看 [2] 中的视频，你会对傅里叶级数的指数形式理解更多。

#### 复值函数

​		考虑周期为 $T$ 的复值函数 $f(t) \in \mathbb{C}$，但其实部（real part）与虚部（imaginary part）都是实值函数，可以使用傅里叶级数来表示，只需将他们组合起来，即得复值函数的傅里叶级数：
$$
\begin{aligned}
f(t) &= \operatorname{Re}\{f(t)\} + i \operatorname{Im}\{f(t)\} \\
&= \sum_{n=-\infty}^{\infty}\operatorname{Re}\{c_n\}
e^{i\frac{2\pi n}{T}t} +
\sum_{n=-\infty}^{\infty}\operatorname{Im}\{c_n\}
e^{i\frac{2\pi n}{T}t} \\
& =\sum_{n=-\infty}^{\infty}\left(\operatorname{Re}\{c_n\} + i \operatorname{Im}\{c_n\}\right)
e^{i\frac{2\pi n}{T}t} \\
& =\sum_{n=-\infty}^{\infty}c_n
e^{i\frac{2\pi n}{T}t}

\end{aligned}
$$
其中
$$
\begin{aligned}
c_n &= \operatorname{Re}\{c_n\} + i \operatorname{Im}\{c_n\} \\
&= \frac{1}{T} \int_{-\frac{T}{2}}^{\frac{T}{2}}
\operatorname{Re}\{f(t)\} 
e^{-i\frac{2\pi n}{T}t} \mathrm{d}t +
i \cdot \frac{1}{T} \int_{-\frac{T}{2}}^{\frac{T}{2}}
\operatorname{Im}\{f(t)\} 
e^{-i\frac{2\pi n}{T}t} \mathrm{d}t \\ 
&=\frac{1}{T} \int_{-\frac{T}{2}}^{\frac{T}{2}}
\left(\operatorname{Re}\{c_n\} + i \operatorname{Im}\{c_n\}\right)
e^{-i\frac{2\pi n}{T}t} \mathrm{d}t \\
&=\frac{1}{T} \int_{-\frac{T}{2}}^{\frac{T}{2}}c_n
e^{-i\frac{2\pi n}{T}t} \mathrm{d}t
\end{aligned}
$$
这与实值函数的傅里叶级数是相同的，但是 $c_n$ 与 $c_{-n}$ 不再共轭
$$
\begin{aligned}
\overline{c_n} &= \overline{\operatorname{Re}\{c_n\}+i\operatorname{Im}\{c_n\}} \\
&= \overline{\operatorname{Re}\{c_n\}}-i\overline{\operatorname{Im}\{c_n\}} \\
&= \operatorname{Re}\{c_{-n}\}-i\operatorname{Im}\{c_{-n}\} \\
&\neq c_{-n}
\end{aligned}
$$

#### 参考文献

- [1] [Fourier series - Wikipedia](https://en.wikipedia.org/wiki/Fourier_series)
- [2] [But what is a Fourier series? From heat flow to drawing with circles | DE4 - YouTube](https://www.youtube.com/watch?v=r6sGWTCMz2k&t=414s)