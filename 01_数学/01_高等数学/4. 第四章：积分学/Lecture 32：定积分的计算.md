---
title: Lecture 32：定积分的计算
tags: 
categories: 
date: 2024-01-23
---
---
## 1.1 定积分的计算
### 1.1.1 概念引入
**变速直线运动中位置函数与速度函数之间的联系**
+ 定积分的定义，直接用于计算很麻烦
	+ $\int_a^bf(x)\operatorname{d}x\mathop{\Delta}\lim_{\lambda\to0}\sum_{i=1}^nf(\xi_i)\Delta x_i$
+ 比如在计算路程时，$v(t)$ 为速度函数，$s(t)$ 为路程函数：
	+ $\int_{T_1}^{T_2}\nu(t)dt=s(T_2)-s(T_1)\quad s^{\prime}(t)=\nu(t)$
	+ 并且，根据不定积分的性质：$s(t)=\int_{t_0}^tv(t)dt\quad s^{\prime}(t)=v(t)$
+ 是否可以转化成，被积函数的原函数在两点之间的相差？

### 1.1.2 积分上限的函数及其导数
**情况分析：** 设 $f(x)$ 在 $[a,b]$ 上连续，并且 x 是 $[a,b]$ 上的任意一点：
![[Pasted image 20240123140558.png]]
这当中阴影部分的面积，其对应的函数称之为**积分上限的函数**
+ $\Phi(x)=\int_a^xf(t)\mathrm{d}t\quad x\in[a,b]$

**问题：** 这个积分上限的函数，是否在函数区间上可导？
+ 答案：可以，前提是 $f(x)$ 在 $[a,b]$ 上连续；

##### **定理**： #积分上限的函数
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{设 }f(x)\text{在 }[a,b]\text{ 上连续，则：}\int_a^xf(t)\mathrm{d}t\text{ 在 }[a,b]$ 有 
>     $(\int_a^xf(t)\mathrm{d}t)^{\prime}=f(x)$

**解释**
+ 对函数的积分求导，等于这一点的函数值；

##### **定理**： #定积分的原函数
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{设 }f(\mathrm{x})\text{在}\left[a,b\right]\text{ 上连续，则}\int_a^xf(t)\mathrm{d}t\text{ 是}f(\mathrm{x})\text{ 在 }\left[a,b\right]$ 上的一个原函数；

**解释**
+ 当被积函数 $f(x)$ 是一个连续函数时，其变上限的积分、作为上限的函数，是 $f(x)$ 在这一点上的原函数；
+ 即：**连续函数一定有原函数**，至少变函数积分一定是其一个原函数；

**推论：** 更加一般化的结论
+ $\text{若 }\varphi(x),\psi(x)\text{ 可导,}f(x)\text{ 连续,则}$：
	+ $\frac d{dx}\int_{\psi(x)}^{\varphi(x)}f(t)dt=f(\varphi(x))\varphi^{\prime}(x)-f(\psi(x))\psi^{\prime}(x)$
### 1.1.3 例题
**例题**：$\text{设 }\Phi(x)=\int_{0}^{x^{2}}e^{-t^{2}}dt,\text{求}\Phi^{\prime}(x)$
+ 分析
	+ 由定积分的原函数的性质，可以用对定积分 $\int_{0}^{x^{2}}e^{-t^{2}}dt$ 的求导，来求 $\Phi^{\prime}(x)$ 的值；
	+ 不能直接对 x 的平方求导，要把它看作是一个复合函数求导；
+ 解析
	+ $\Phi=\int_{0}^{u}e^{-t^{2}}dt$
	+ 其中 $u=x的平方$
	+ 注意：不能直接对 x 的平方求导，要把它看作是一个复合函数求导：
	+ $\bar{\Phi}_{x}^{\prime}(x)=\bar{\Phi}_{u}^{\prime}\cdot U_{x}^{\prime}=e^{-u^2}\cdot2x=e^{-x^4}\cdot2x.$
+ 题型： #定积分的原函数 

**例题**：当函数的上下限都变时： $g(x)=\int_{\sin x}^{x^2}e^{-t^2}dt\quad$，求其导函数；
+ 分析
	+ 可以将其分成两段，从 sinx 到 0，再从 0 到 x 的平方；
	+ 分开求解，相加；
+ 解析
	+ ${\int_0^{x^2}e^{-t^2}dt+\int_{sinx}^0e^{-t^2}dt}$
+ 题型： #定积分的原函数

## 1.2 牛顿-莱布尼茨公式
### 1.2.1 基本概念
##### **定理**： #牛顿莱布尼茨公式
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{设 }F(x)\text{ 为连续函数 }f(x)$ $\text{在 }[a,b]\text{ 上的一个原函数,则}$：$\int_{a}^{b}f(x)dx=F(b)-F(a)$，也称之为微积分基本公式；

**解释**
+ 把求解定积分的问题，转变成了找原函数的问题；
+ 并且此公式：沟通了积分学和微分学之间的关系；
 
**推论：** 证明积分中值定理
+ $\text{若 }f(x)\text{ 在 }[a,b]\text{ 上连续,则}$
+ $\int_a^bf(x)\operatorname{d}x=f(\xi)(b-a)\quad\quad a<\xi<b$
	+ ![[Pasted image 20240123145622.png]]

### 1.2.2 例题
**例题**：$\int_{0}^{\pi}\sin xdx$
+ 分析
+ 解析
	+ $\int_{0}^{\pi}\sin xdx=\left(-cosx\right)\int_{0}^{\pi}=1-(-1)=2.$
+ 题型： #牛顿莱布尼茨公式 

