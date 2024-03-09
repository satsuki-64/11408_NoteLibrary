---
title: Lecture 18：高阶导数
tags:
  - 数学
categories: 
date: 2023-12-18
---
---
## 1.1 多阶导数的定义
**多阶导数的表示方法**
$(y^{\prime})^{\prime}=y^2=\frac{d^2y}{dx^2}\quad\quad y^{m}\quad\quad y^{(4)}\quad\quad y^{(n)}=\frac{d^ny}{dx^n}$

**定义：n 阶导数**
若 $f^{(n)}(x)$ 在区间 $I$ 上连续，称 $f(x)$ 在 $I$ 上 n 阶连续可导
+ n 阶导函数存在，而且还是连续的

## 1.2 求 n 阶导数
### 1.1.2 常见求 n 阶导数
**常见求 n 阶导数**
+ 指数
	+ $(e^{x})^{(n)}=e^{x}$
+ 三角函数
	+ $(\sin x)^{(n)}=\sin(x+n\frac\pi2)$
	+ $(\cos x)^{(n)}=\cos(x+n\frac{\pi}{2})$
+ In 函数
	+ $(\ln(1+x))^{(n)}=(-1)^{n-1}\frac{(n-1)!}{(1+x)^n}$

### 1.2.2 基本运算的 n 阶导数
+ 加法
	+ $(u\pm v)^{(n)}=u^{(n)}\pm v^{(n)}$
+ 乘法
	+ 莱布尼茨公式
	+ ![[Pasted image 20231218212618.png]]

**例题**：$\text{设 }f(x)=\frac1{x^2-1}\text{,求 }f^{(n)}(x)$
思路：无法直接使用加法或者乘法公式，因此需要将分母分解因式，将其拆分：
+ $\begin{aligned}f(x)&=\frac{1}{(x-1)(x+1)}=\frac{1}{2}\frac{(x+1)-(x-1)}{(x-1)(x+1)}\\&=\frac{1}{2}\left[\frac{1}{x-1}-\frac{1}{x+1}\right]\end{aligned}$
拆分完成后，使用加法的 n 阶导数：
+ $f^{(n)}(x)=\frac12\left[(\frac1{x-1})^{(n)}-(\frac1{x+1})^{(n)}\right]$
+ 然后先分析一个：$(\frac1{x-1})^{(n)}=(-1)^nn!(x-1)^{-(n+1)}$
+ $f^{(n)}(x)=\frac{1}{2}\left[\frac{(-1)^{n}n!}{(x-1)^{n+1}}-\frac{(-1)^{n}n!}{(x+1)^{n+1}}\right].$