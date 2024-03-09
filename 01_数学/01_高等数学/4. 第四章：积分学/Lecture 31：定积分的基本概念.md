---
title: Lecture 31：定积分的基本概念
tags:
  - 数学
  - 定积分
categories: 
date: 2024-01-21
---
tijiwenti---
## 1.1 定积分基本概念
### 1.1.1 定积分的定义
##### **定义**： #定积分
> <font color="#ccc1d9">描述：</font> $f(x)$ 在 $[a,b]$ 上有界，在 $[a,b]$ 上任意插入分点，分成 n 个小区间 $\Delta x_{1}\Delta x_{2}\cdots\Delta x_{n}$ ，任取一点 i，有：
>     $\int_{a}^{b}f(x)dx=\lim_{x\to0}\sum_{i=1}^{n}f(\xi_{i})\Delta x_{i}$
>     $\lambda=\max\{\Delta x_{1}\cdots\Delta x_{n}\}$

**解释**
 + 设函数 $f(x)$ 在区间 $[a, b]$ 上连续，将区间 $[a, b]$ 分成 n 个子区间 $[x_0,x_1]$,($x_1,x_2],(x_2,x_3],\ldots,(x_{n-1},x_n]$, 其中 $x_0 = a$，$x_n = b$，设 ：
 + $\lambda=\max[-x_1,-2x_2,\ldots,-2x_n\}$ （即λ是最大的区间长度） 
 + 如果当 λ→0 时，积分和的极限存在，则这个极限叫做函数 f (x) 在区间[a, b]的定积分，记为 $\int_a^bf(x)dx$，并称函数 f (x)在区间 $[a, b]$ 上可积；

**使用条件**
+ 定 1：连续 -> 可积；
+ 定 2：有界，有有限个间断点 -> 可积；

**定积分注意事项**
+ 定积分求出来的是一个具体的数，且只和被积分函数以及积分区间有关，与积分变量无关；


### 1.1.2 定积分的几何含义
**函数值有正有负**
![[Pasted image 20240121212018.png]]
当函数值有正有负时，当前定积分的值会 A 和 C 部分的面积和，减去 B 部分的面积大小；
+ 不知道正负，求了才知道；

## 1.2 定积分的性质
### 1.2.1 基础性质
**两条规定**
+ 1. 如果 b = a 时，从 a 到 a 的定积分等于 0；
+ 2. 从 a 到 b 的定积分，等于从 b 到 a 的定积分的相反数；
	+ $\int_{a}^{b}f\left(x\right)dx=-\int_{b}^{a}f\left(x\right)dx$
	+ 交换上下限；

**性质 1：**$\int_{a}^{b}(\alpha f(x)+\beta g(x))dx=\alpha\int_{a}^{b}f(x)dx+\beta\int_{a}^{b}g(x)dx$

**性质 2：** 
+ 如果 $a<c<b$ （c 在里头）
	+ 则 $\int_{a}^{b}f\left(x\right)dx=\int_{a}^{c}f\left(x\right)dx+\int_{c}^{b}f\left(x\right)dx$
	+ ![[Pasted image 20240122224209.png]]
+ 如果 $a<b<c$（c 在外头）
	+ 则 $\int_{a}^{b}f(x)dx=\int_{a}^{c}f(x)dx-\int_{b}^{c}f(x)dx$ $=\int_{a}^{c}f\left(x\right)dx+\int_{c}^{b}f\left(x\right)dx$
+ 所以，最终结论：$\int_{a}^{b}f\left(x\right)dx=\int_{a}^{c}f\left(x\right)dx+\int_{c}^{b}f\left(x\right)dx$

**性质 3：** $\begin{aligned}f(x)\equiv1；\int_{a}^{b}1dx=b-a\\\int_{a}^{b}kdx=k(b-a)\end{aligned}$

**性质 4：** M，m 分别为最大值、最小值，因此 $m(b-a)\leq\int_{a}^{b}f(a)dx\leq M(cb-a)$