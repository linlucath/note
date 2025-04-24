---
date: 2025/3/24
tags:
  - 定积分
  - 数学分析
  - 数学
aliases:
  - 定积分
---
## 0 . 不定积分的计算
一 . 基本积分表
1. 三角函数
   $$
   \int \tan x \, dx = -\ln|\cos x| + C
   $$
2. 反三角函数
   $$
   \int \frac{1}{\sqrt{a^2 - x^2}} \, dx = \arcsin\left(\frac{x}{a}\right) + C
   $$
   $$
    \int \frac{1}{a^2 + x^2} \, dx = \frac{1}{a} \arctan\left(\frac{x}{a}\right) + C
   $$
3. 有理函数
   $$
   \int \frac{1}{x^2 - a^2} \, dx = \frac{1}{2a} \ln\left|\frac{x - a}{x + a}\right| + C
   $$
   $$
    \int \frac{1}{(x + a)(x + b)} \, dx = \frac{1}{b - a} \ln\left|\frac{x + a}{x + b}\right| + C \quad (a \neq b)
   $$
<span style="color: red">summary</span>:
   对于有理多项式分式,:
   step1: 化成真分式
   step2: 分解为分母为一次, 二次的真分式相加
   step3: 分别积分, 相加

二 . 计算技巧
1. 换元
2. 分部积分$\int{udv}=uv-\int{vdu}$
3. 三角积分使用三角恒等式转乘为加

## 1 . 定积分概念:

设函数  $f$  在区间  $[a, b]$  上有定义。

1. 称点集  $P = \{x_0, x_1, \cdots, x_{n-1}, x_n\}$  为  $[a, b]$  的一个**分划**，如果满足条件：   
 $$
   a = x_0 < x_1 < \cdots < x_{n-1} < x_n = b.
   $$ 
   记  $\Delta x_i = x_i - x_{i-1}, i = 1, \cdots, n$ ，并称  $\|P\| = \max_{1 \leq i \leq n} \{\Delta x_i\}$  为分划  $P$  的**细度**。如果  $\Delta x_i = \frac{b-a}{n}, i = 1, \cdots, n$ ，则称  $P$  为**等距分划**。

2. 设  $P = \{x_0, x_1, \cdots, x_{n-1}, x_n\}$  为区间  $[a, b]$  的一个分划。对每个子区间  $[x_{i-1}, x_i]$ ，任取  $\xi_i \in [x_{i-1}, x_i]$ ，则称  $\xi = \{\xi_i \mid i = 1, 2, \cdots, n\}$  为从属于  $P$  的一个**介点集**；并称和式  $\sum_{i=1}^{n} f(\xi_i) \Delta x_i$  或  $\sum_{P}^{} f(\xi_i) \Delta x_i$  为  $f$  在区间  $[a, b]$  上的一个 **Riemann（积分）和**。

3. 设  $I$  为实数，且
 $$
   \lim_{\|P\| \to 0} \sum_{i=1}^{n} f(\xi_i) \Delta x_i = I,
   $$ 
   即  $\forall \varepsilon > 0, \exists \delta > 0$ ，对  $\|P\| < \delta$  的每个分划  $P$ ，以及对从属于  $P$  的每个介点集  $\xi$ ，成立  $\left| \sum_{i=1}^{n} f(\xi_i) \Delta x_i - I \right| < \varepsilon$ ，则称函数  $f$  在区间  $[a, b]$  上 **Riemann 可积**或简称 **可积**，记为   
 $$
   f \in R[a, b],
   $$
   并称  $I$  为  $f$  在区间  $[a, b]$  上的 **Riemann 积分**或 **定积分**，简称积分，记为
 $$
   \int_{a}^{b} f(x) \, dx = I,
   $$
   或其简化记号
 $$
   \int_{a}^{b} f = I.
   $$
## 2 . 可积条件

设函数 $f$ 在区间 $[a, b]$ 上有界， $P = \{x_0, x_1, \cdots, x_{n-1}, x_n\}$  为  $[a, b]$  的一个分划, 对  $i = 1, \cdots, n$, 记
$$ M_i = \sup\{f(x) \mid x \in [x_{i-1}, x_i]\} \quad \text{与} \quad m_i = \inf\{f(x) \mid x \in [x_{i-1}, x_i]\}, $$
称  $\omega_i = M_i - m_i$  为  $f$  在  $[x_{i-1}, x_i]$  上的振幅， $\sum_{i=1}^{n} \omega_i \Delta x_i$  为  $f$  的振幅面积。
1.  有界函数  $f \in R[a, b]$  的充分必要条件是 
$$
\lim_{\|P\| \to 0} \sum_{i=1}^{n} \omega_i \Delta x_i = 0.
  $$
**2. 有界函数  $f \in R[a, b]$  的充分必要条件是对每个  $\varepsilon > 0$ ，存在区间  $[a, b]$  的一个分划  $P$ ，使成立**
$$
\sum_{P} \omega_i \Delta x_i < \varepsilon.
  $$
2. 有界函数  $f \in R[a,b]$  的充分必要条件是  $\forall \varepsilon, \eta > 0$ ，存在  $[a,b]$  的分划  $P$ ，使振幅不小于  $\eta$  的子区间的长度之和小于  $\varepsilon$ 
<span style="color: red">通解:</span>
	<u><strong>step1</strong></u>:  证明有可列个不连续点的函数可积.(将可积的第三充要条件作为引理)
	对每个点 $a_k$，用区间 $I_k = \left( a_k - \frac{\epsilon}{2^{k+1}}, a_k + \frac{\epsilon}{2^{k+1}} \right)$ 覆盖，其长度为 $\frac{\epsilon}{2^k}$。
	总长度求和：  
	$$  
	\sum_{k=1}^\infty \frac{\epsilon}{2^k} = \epsilon \cdot \sum_{k=1}^\infty \frac{1}{2^k} = \epsilon \cdot 1 = \epsilon.  
	  $$
	于是对任意 $\epsilon > 0$，总存在覆盖使总长度 $\leq \epsilon$，故 $\mu(A) = 0$。  $\square$
	<u><strong>step2</strong></u>: 证明可积的第三充要条件.(将加强的覆盖定理作为引理)
	对于给定的  $\varepsilon, \eta > 0$ ，先用总长度小于  $\varepsilon$  的有限个或可列个开区间覆盖  $f$  的所有不连续点。然后对于每个连续点，设为  $x_0$ ，用一个邻域  $O(x_0)$  覆盖，且要求  $f$  在这个邻域上的振幅小于  $\eta$ 。由于  $f$  在点  $x_0$  的连续性，这是能够满足的。
	对于每个连续点都取这样的邻域，于是所有这些邻域和覆盖不连续点的开区间一起就构成为区间  $[a, b]$  的一个开覆盖，记为  $\{O_\alpha\}$ 。
	利用加强形式的覆盖定理（即例题 3.5.3），存在 Lebesgue 数  $\delta$ ，使得在区间  $[a, b]$  中的相距不超过  $\delta$  的任何两点可以用开覆盖  $\{O_\alpha\}$  中的某一个开区间同时覆盖。
	对于区间  $[a, b]$  取细度不超过  $\delta$  的等距分割  $P$ 。这时每个子区间被开覆盖中的一个开区间所覆盖。如果子区间是由原来覆盖不连续点的开区间所覆盖，则这类子区间的总长度必小于  $\varepsilon$ 。而覆盖所有其他子区间的开区间都是原先用于覆盖连续点的邻域，因此  $f$  在每一个这类子区间上的振幅小于  $\eta$ 。
	根据可积的第三充分必要条件，可知  $f$  在  $[a, b]$  上可积。 $\square$
	<u><strong>step3</strong></u>: 证明加强的覆盖定理
	首先用覆盖定理，得到区间  $[a, b]$  的一个有限子覆盖，即开覆盖  $\{O_\alpha\}$  中的有限个开区间
	 $$ 
	 O_1, O_2, \cdots, O_n, 
	 $$
	 它们的并覆盖了$[a, b]$ 。将这有限个开区间的所有端点按大小顺序排列，去掉其中可能有重复的点，记为
	$$ 
	x_0 < x_1 < \cdots < x_N. 
	$$
	并记这个端点集为  $A = \{x_0, x_1, \cdots, x_N\}$ 。现在令
	$$ \delta = \min\{x_1 - x_0, x_2 - x_1, \cdots, x_N - x_{N-1}\}. $$
	我们来证明这就是所求的 Lebesgue 数。
	设任取两点  $x', x'' \in [a, b]$ ，使  $0 < x'' - x' < \delta$ 。则有两个可能：
	(a) 在闭区间  $[x', x'']$  内没有端点集  $A$  中的点。于是在（3.1）中覆盖该闭区间中任何一点的开区间也就覆盖了整个闭区间。
	(b) 在闭区间  $[x', x'']$  内有  $A$  中的点。由于数  $\delta$  的取法，这样的点只有一个。在图 3.1(b) 中将这个点记为  $x_i$ ，于是有  $x' \leq x_i \leq x''$ 。由于这个点  $x_i$  是（3.1）中的开区间的端点，而这个开区间并不覆盖点  $x_i$ ，因此在（3.1）中一定另有开区间覆盖点  $x_i$ ，它的左右端点必然分别小于  $x'$  和大于  $x''$ ，从而也就同时覆盖点  $x'$  和  $x''$ 。$\square$

## 3 . 定积分的性质

1. **积分第一中值定理**
设  $f, g \in R[a, b]$ ， $m \leq f(x) \leq M, \forall x \in [a, b]$ ， $g$  在  $[a, b]$  上不变号，则存在  $\eta \in [m, M]$ ，使
$$
\int_a^b f(x)g(x) \, dx = \eta \int_a^b g(x) \, dx.
  $$ 如果  $f \in C[a, b]$ ， $g \in R[a, b]$  且在  $[a, b]$  上不变号，则存在  $\xi \in [a, b]$ ，使
 $$
\int_a^b f(x)g(x) \, dx = f(\xi) \int_a^b g(x) \, dx. 
  $$ 特别的，如果  $f \in C[a, b]$ ，则存在  $\xi \in (a, b)$ ，使
 $$
\int_a^b f(x) \, dx = f(\xi)(b - a).
  $$ 
2. **积分第二中值定理** 
设$f\in R[a,b]$，$g$在$[a,b]$上单调，则存在$\xi\in[a,b]$，使
$$
\int_a^b f(x)g(x) \, dx = g(a)\int_a^\xi f(x) \, dx + g(b)\int_\xi^b f(x) \, dx.
$$
特别的，如果$g$在$[a,b]$上单调增加且$g(x)\geq 0$，则存在$\xi\in[a,b]$，使
$$
\int_a^b f(x)g(x) \, dx = g(b)\int_\xi^b f(x) \, dx;
$$
如果$g$在$[a,b]$上单调减少且$g(x)\geq 0$，则存在$\xi\in[a,b]$，使
$$
\int_a^b f(x)g(x) \, dx = g(a)\int_a^\xi f(x) \, dx.
$$
## 4. 微积分基本定理
1. 积分求导
   $$
   \lim_{x \to 0^+} \frac{\int_{0}^{x^2} \sin \sqrt{t} \, dt}{x^3}
   $$
<span style="color: red">Solution:</span>
   令$u=x^2$, 
   $$
   \frac{\int^{x^2}_{0}sin\sqrt{t}dt}{dx}
   =\frac{\int^{u}_{0}sin\sqrt{t}dt}{du}\frac{du}{dx}
   $$
2. 利用积分求解级数
$$
求解\lim_{n \to \infty} \left( \frac{1}{n+1} + \frac{1}{n+2} + \cdots + \frac{1}{2n} \right)
$$

<span style="color: red">Solution:</span>
   思路: 让级数中只存在$\frac{k}{n}$与$n$有关
   $$
   原式=\lim_{n \to \infty}{\frac{1}{n}(\frac{1}{1+\frac{1}{n}}+\frac{1}{1+\frac{2}{n}}\cdot+\frac{1}{1+\frac{n}{n}})}=\int^{1}_{0}\frac{dx}{1+x}
   $$

$$
\int{xln^nxdx=\int{\frac{e^{u}u^ndu}{e^u}}}
$$