---
title: Lecture 16：导数基本概念
tags:
  - 数学
  - 导数
categories: 
date: 2023-12-13
---
---
## 1.1 导数的定义
**为什么需要导数**
导数的本质对于一个点应变量增量与自变量增量的极限，这也就是反应了：在这个点，**应变量随着自变量变化的速度**；

##### **定义**： #什么是导数
> <font color="#ccc1d9">描述：</font> $\begin{aligned}\text{若 }&\lim_{\Delta x\to0}\frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}&\text{存在，则称 }f(x)\text{ 在 }x_0\text{ 点可导}.\end{aligned}$

**解释**
+ 等价形式：
	+ 因为 $x_0+\Delta x=x\quad\Delta x=x-x_0.$
	+ 所以 $f^{\prime}(x_0)=\lim_{\Delta x\to0}\frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}=\lim_{x\to x_0}\frac{f(x)-f(x_0)}{x-x_0}$
+ 可以写作：
	+ $f^{\prime}(x_0)=y^{\prime}|_{x=x_0}=\frac{dy}{dx}|_{x=x_0}$
+ 若以上极限不存在，则称 $f(x)$ 在 $x_{0}$ 处不可导； 
+ 若极限为无穷大，则称 $f(x)$ 在 $x_{0}$ 处导数为无穷大（导数为无穷，为不可导）.

##### **定义**： #左导数与右导数
> <font color="#ccc1d9">描述：</font> $\begin{aligned}&\text{ 左导数: }f_0^{\prime}(x_0)=\lim_{\Delta x\to0^-}\frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}=\lim_{x\to x_0^-}\frac{f(x)-f(x_0)}{x-x_0}\\&\text{ 右导数: }{f_0^{\prime}(x_0)}=\lim_{\Delta x\to0^+}\frac{f(x_0+\Lambda x)-f(x_0)}{\Delta x}=\lim_{x\to x_0^+}\frac{f(x)-f(x_0)}{x-x_0}\end{aligned}$

**解释**
+ 左导数的函数下面要加负号
+ 右导数的函数下面要加正号
+ 左右导数的关系
	+ 可导 <-> 左右导数存在且相等；
+ 公式：$f^{\prime}(x_0)=a\Leftrightarrow f_-^{\prime}(x_0)=f_+^{\prime}(x_0)=a$

## 1.2 导函数的定义与证明
**区间上可导**
在一个区间内每个点都有导数，称之为区间内可导；
这个导数构成的函数，称之为函数的导函数；

**导函数** 
$f^{\prime}(x)\quad x\in I$

### 1.2.1 证明函数的导数
**题目：**$\left(a^x\right)^{\prime}=a^x\ln a\left(a>0,a\neq1\right)$
+ 证明过程：
	+ $\lim_{\Delta x\to0}\frac{a^{x+\Delta x}-a^x}{\Delta x}=\lim_{\Delta x\to0}\frac{a^x\left[a^{\Delta x}-1\right]}{\Delta x}=a^x\ln a$
+ 其中，第二步的直接变成 lna 的步骤，因为有此等价极限：$\lim_{x\to0}\frac{a^x-1}{x}=\ln a$


**题目**：$(\sin x)^{\prime}=\cos x$
+ 证明过程：
	+ $\lim_{\Delta x\to0}\frac{\sin(x+\Delta x)-\sin x}{\Delta x}=\lim_{\Delta x\to0}\frac{2\sin\frac{\Delta x}{2}\cos\frac{2x+\Delta x}{2}}{4x}$
+ 因为 sinx~x，所以：
	+ $\operatorname*{lim}_{\Delta x\rightarrow0}\frac{2-\frac{\Delta x}{2}\sin\frac{2x+\Delta x}{2}}{\Delta x}=\cos x$

## 1.3 导函数的几何意义
**导函数与切线**
+ 定义：
	+ 导数 $f^{\prime}(x_0)$ 在几何上，表示为曲线 $y=f(x)$ 在点 $\left(x_0,f(x_0)\right)\text{处切线的斜率}$
+ 切线与法线 
	+ $\begin{gathered}y-y_{0}=f^{\prime}(x_{0})(x-x_{0}) \\y-y_0=-\frac1{f^{\prime}(x_0)}(x-x_0) \end{gathered}$

## 1.4 可导与连续的关系
可导和连续都是用于刻画，函数在一点的性质；

**可导与连续的关系**
+ **可导 -> 连续**
+ 证明：**可导推连续**
	+ 如果可导，则有：$\lim_{\Delta x\rightarrow0}\frac{\Delta y}{\Delta x}=f^{\prime}(x_0)$
	+ 因为 $\Delta y=\frac{\Delta y}{\Delta x}\cdot\Delta x$
	+ 所以其中的 $\frac{\Delta y}{\Delta x}$ 为常数，而 $\Delta x$ 趋向于 0，所以 $\Delta y$ 也趋向于 0
	+ 因此满足连续的定义：$\lim_{\Delta x\to0}\Delta y=0$
+ **连续 -X> 可导**
	+ 连续不可导的经典例子：$f(x)=|x|$，0 点连续，左右导数存在，但不相等；

**判断可导性的方法**
+ 判断可导性
	+ 不连续
		+ 一定不可导；
	+ 连续
		+ 直接用定义；
		+ 看左右导数是否存在且相等；