---
title: Lecture 17：导数求导法则
tags:
  - 数学
categories: 
date: 2023-12-17
---
---
## 1.1 和差积商求导法则
**定理 1：**
设 $u(x),\nu(x)$ 都可导，则
+ $\quad(u\pm v)^{\prime}=u^{\prime}\pm v^{\prime}$
+ $(uv)^{\prime}=u^{\prime}v+uv^{\prime}$
+ $(\frac\mu\nu)^{\prime}=\frac{\mu^{\prime}\nu-\nu^{\prime}\mu}{\nu^2}\quad(\nu\neq0)$

## 1.2 反函数的求导法则
**定理 2：**
设区间 $I$ 上严格单调且连续的函数 $x=f(y)$ 在 $y$ 处可导，且 $f^{\prime}(y)\neq0$,则它的反函数 $y=f^{-1}(x)$ 在对应点可导，且：
+ $(f^{-1})^{\prime}(x)=\frac1{f^{\prime}(y)}\quad\frac{dy}{dx}=\frac1{dx}$
+ 含义
	+ 函数和反函数是两个函数，但是是同一条曲线；
	+ 因此**当函数连续且单调时，可以知其反函数也同样可导**；

**例题：**$\text{求}\quad y=\arcsin\quad x\quad(x\in[-1,1])\text{ 导数}$
反函数：$x=\sin y\quad y\in\left[-\frac\pi2,\frac\pi2\right]$
函数的导数：$\frac{dy}{dx}=(\arctan x)^{\prime}=\frac{1}{\log}=\frac{1}{\sqrt{1-\sin^{2}y}}=\frac{1}{\sqrt{1-x^{2}}}$

## 1.3 复合函数求导法则
**定理 3：链式法则**
设 $u=g(x)$ 在 $x$ 可导，$y=f(u)$ 在对应 $u$ 处可导，则 $y=f[g(x)]$ 在 x 处可导，且 
+ $\frac{dy}{dx}=f^{\prime}(u)g^{\prime}(x)$
+ 其他形式：
	+ $\frac{dy}{dx}=\frac{dy}{du}\cdot\frac{du}{dx}$

**例题：**$y=2\cos^2\frac1x$
使用链式法则： $y=2u^{2},u=\cos v,v=\frac{1}{-x^2}$
+ $\begin{aligned}\frac{dy}{dx}&=4u\cdot(-\sin v)(-\frac1{x^2})\\&=4\end{aligned}$

**注意：求函数值时，是从里到外；但求导数时，是从外到里，一直求到对 x 求导；**


## 1.5 求导结论
**基本初等函数**
![[Pasted image 20231217234610.png]]

+ 三角函数
	+ $\begin{aligned}(\tan x)^{\prime}&=\sec^2x&(\cot x)^{\prime}&=-\csc^2x\\\\(\sec x)^{\prime}&=\sec x\tan x&(\csc x)^{\prime}&=-\csc x\cot x\end{aligned}$
+ 反函数导数
	+ $\begin{aligned}&(\arcsin x)^{\prime}=\frac1{\sqrt{1-x^2}}&&(\arccos x)^{\prime}=-\frac1{\sqrt{1-x^2}}\\&(\arctan x)^{\prime}=\frac1{1+x^2}&&(\arctan x)^{\prime}=-\frac1{1+x^2}\end{aligned}$