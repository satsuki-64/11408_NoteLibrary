---
title: Lecture 36：一阶线性微分方程
tags:
  - 数学
  - 微分方程
categories: 
date: 2024-02-01
---
---
## 1.1 线性方程
### 1.1.1 基本概念
##### **定义**： #一阶线性微分方程
> <font color="#ccc1d9">描述：</font> $y^\prime+p(x)y=Q(x)$

**解释**
+ 什么是一阶
	+ 未知函数 y 和未知函数的导数都是一次的，所以一阶是相对于未知函数而言的；
+ 齐次（一阶的特殊情况）
	+ $y^{\prime}+p(x)y=0$
	+ 齐次方程的通解 
		+ $y=Ce^{-\int p(x)dx}$
+ 非齐次
	+ $y^{\prime}+p(x)y=Q(x)$
		+ 有时候也可以使用变量代换，使用 x 做为函数，导数还是一样的 dx/dy，然后 Q 是关于 y 的函数；
	+ 非齐次方程的通解
		+ $y=e^{-\int p(x)dx}(\int Q(x)e^{\int p(x)dx}dx+C)$

**补充**：求齐次方程的通解
+ 因为
	+ ![[Pasted image 20240201145937.png]]
+ 所以
	+ ![[Pasted image 20240201145945.png]]
+ 求非齐次的方法
	+ 可以先解出齐次方程的通解，然后把齐次方程的通解带入到非齐次方程中，得到非齐次方程的通解；

### 1.1.2 例题
**例题**：$y^{\prime}-\frac2xy=x^2$
+ 分析
	+ 公式：$y=e^{-\int p(x)dx}(\int Q(x)e^{\int p(x)dx}dx+C)$
+ 解析
	+ 设 $P(x)=-\frac{2}{x},\quad Q(x)=x^2$
	+ 然后带入公式
		+ ![[Pasted image 20240201151303.png]]
+ 题型： #一阶线性微分方程 

## 1.2 伯努利方程
### 1.2.1 基本概念
##### **定义**： #伯努利方程
> <font color="#ccc1d9">描述：</font>$y^{\prime}+p (x) y=Q (x) y^\alpha$

**解释**
+ 如果阿法是等于 0，那就是线性方程
+ 如果阿法是等于 1，那就直接可以使用可分离变量；
+ 因此：当前的讨论，都是假设阿法及不等于 0，也不等于 1；
+ 思路：思考如何才能化成线性方程

**处理方法**
+ 已知：$y^{\prime}+p (x) y=Q (x) y^\alpha$
+ 第一步
	+ 把 $y^\alpha$ 除到等式的左边来，和 y 相除，得到：
	+ $y^{1-\alpha}$
+ 第二步：设 z
	+ 令 $y^{1-\alpha}=z$
+ 第三步
	+ 化成线性方程

### 1.2.2 例题
**例题**：$\frac{dy}{dx}+\frac yx=a(\ln x)y^2$
+ 分析
+ 解析
	+ 先将 y 的平方除以过去：
		+ $\frac1{y^2}\frac{\mathrm{d}y}{\mathrm{d}x}+\frac1x\frac1y=a\ln x$
		+ $-\frac{1}{y^{2}}\frac{dy}{dx}=\frac{dt}{dx}$
	+ 然后设 y 的负一次方为 z
		+ $-\frac{\mathrm{d}z}{\mathrm{d}x}+\frac1xz=\mathrm{alnx}$
	+ 左右对 x 求导：
+ 题型： #伯努利方程


![[Pasted image 20240201162538.png]]