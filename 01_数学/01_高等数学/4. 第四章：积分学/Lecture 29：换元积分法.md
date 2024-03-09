---
title: Lecture 29：换元积分法
tags:
  - 数学
  - 不定积分
categories: 
date: 2024-01-17
---
---
## 1.1 第一类换元法
**从求导数开始**
- 求导数的时候，最核心的方法是什么？
	- 1. 有理运算法则（加减乘除）；
	- 2. 复合函数求导法；
		- 隐函数求导法进而参数方程求导法都是前两者的结论；
- 所以当考虑求导数的逆过程时，就可以考虑基于 1、2 两点的求其逆过程；
- 逆过程
	- 复合函数 
		- 把复合函数求导法的过程倒过来 -> **换元积分法**；
	- 有理运算法则
		- 倒过来 -> 分项积分法；
		- 乘法 -> **分部积分法**；

### 1.1.1 第一类换元法基本概念
##### **定理**： #第一类换元法：凑微分法 
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>若 $\int f(u)\mathrm{d}u=F(u)+C$，$\text{则}\int f[\varphi(x)]\varphi^{\prime}(x)\operatorname{d}x=\int f[\varphi(x)]\operatorname{d}\varphi(x)=F[\varphi(x)]+C$

**解释**
+ 比如：$\int e^x\mathrm{d}x=e^x+c$
+ 当前为 $\int xe^{x^2}dx=\frac12\int e^{x^2}(x^2)dx=\frac12\int e^{x^2}dx^2=\frac12e^{x^2}+c^2$
	+ 为了想用上面 $\int e^x\mathrm{d}x=e^x+c$ 的结论，所以把它写成 $\frac12\int e^{x^2}dx^2$ 的形式；
	+ 这个步骤就是凑微分；

### 1.1.2 例题
**例题**：$\int(1+3x)^{100}dx$
+ 分析
	+ 因为被积分对象是复合函数，因此可以先考虑如何将其转化为简单的、可以使用公式的形式：
	+ $\int u^{100}du=\frac1{101}u^{101}+c$
+ 解析
	+ $\int(1+3x)^{100}dx=\frac13\int(1+3x)^{100}d(1+3x)=\frac1{303}(1+3x)^{10}+C$
	+ 凑了一个 $d$ 的 $1+3x$
+ 题型： #凑微分法 

**例题**：$\int\frac{dx}{a^2+x^2}$
+ 分析
	+ 因为
+ 解析
	+ $\int\frac{dx}{a^{2}+x^{2}}=\frac{1}{a}\int\frac{d\frac{x}{a}}{1+(\frac{x}{a})^{2}}=\frac{1}{a}\operatorname{arcc}t,\frac{x}{a}+C^{1}$
+ 题型： #凑微分法 

**例题**：$\int\frac{dx}{\sqrt{1-x^2-2x}}$
+ 分析
	+ $17、\int\frac{dx}{\sqrt{1-x^2}}=\begin{cases}\arcsin x+C\\-\arccos x+C&\end{cases}$
+ 解析
	+ $\int\frac{dx}{\sqrt{1-x^2-2x}}=\int\frac{d(x+1)}{\sqrt{2-(x+1)^2}}$ = $\arcsin\frac{x+1}{\sqrt{2}}+c$
+ 题型： #凑微分法 

## 1.2 第二类换元法
### 1.2.1 第二类换元法基本概念 
##### **定理**： #第二类换元法
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{设 }x=\varphi(t)\text{ 是单调的、可导的函数,并且 }\varphi^{\prime}(t)\neq0$ $\int f[\varphi(t)]\varphi^{\prime}(t)\mathrm{d}t=F(t)+C,$ 
> 则：$\int f(x)\mathrm{d}x=\int f[\varphi(t)]\varphi^{\prime}(t)\mathrm{d}t=F(t)+C=F[\varphi^{-1}(x)]+C,$

**解释**
+ 关键是变量代换的选取；

**总结**
以下三种形式：
$$
\begin{aligned}
&\sqrt{a^2-x^2} \\
&\sqrt{a^2+x^2} \\
&\sqrt{x^2-a^2}
\end{aligned}
$$
分别可以使用以下三种形式的 x 来带入，进而消掉根号：
$$
\begin{aligned}x&=a\sin t(a\cos t)\\\\x&=a\tan t\\\\x&=a\sec t\end{aligned}
$$

### 1.2.2 例题
**例题**：$\int\frac{dx}{\sqrt{a^2+x^2}}\quad(a>0)$
+ 分析
	+ 因为原式中有根号，因此当需要求其不定积分时，首先应该考虑如何消掉这个根号；
	+ 此时可以想到用**第二类换元法**来把 a 以及 x 从根号中弄出来；
+ 解析
	+ 可以设 $x=a*tant$
	+ 此时先带入分母中，可知：分母变成 $a*sect$
	+ 然后求 $dx$ -> 求 $d(a*tant)$ 
	+ 然后：![[Pasted image 20240119002138.png]]
+ 题型： #第二类换元法