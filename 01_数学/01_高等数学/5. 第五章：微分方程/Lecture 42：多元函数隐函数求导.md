---
title: Lecture 41：隐函数求导
tags:
  - 数学
  - 隐函数
categories: 
date: 2024-02-07
---

---
## 1.1 隐函数基本概念
### 1.1.1 基本概念
##### **定义**： #隐函数
> <font color="#ccc1d9">描述：</font>

**解释**
+ 什么是隐函数
	+ 形如 F (x, y)=0 的函数叫隐函数；
	+ 将自变量和因变量放在同一个式子中，隐藏了二者之间的函类关系，因此称之为隐函数。
+ 什么是显函数
	+ 显函数可以理解为：
	+ 自变量和因变量的函数关系明显的函数，形如 y=f (x)对应隐函数概念

##### **定理**： #隐函数存在定理
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $F(x,y)$ 在点 $M_0(x_0,y_0)$ 邻域内连续可偏导，且 $F(x_0,y_0)=0,F_y\:\prime(x_0,y_0)\neq0$ 则由 $F(x,y)$ 在 $M_{0}$ 邻域内唯一确定一个连续可导函数 $y=f(x)$ 使 $y_0=f(x_0)$
> 则： $\frac{dy}{dx}=-\frac{F_{x}'}{F_{y}'}$


**解释**
+ 更通俗的解释
	+ $F(x,y)=0,\text{若}x\text{为自变量},F(x,y)=0\Rightarrow y=y(x),\text{求}\frac{dy}{dx}$
	+ 根据要求，x 是自变量，因此理论上可以将 y 变成 x 的一元函数，即将 y 直接看成 y (x)，进而同时两边对 x 求导：
		+ $F_{x}'+F_{y}'\frac{dy}{dx}=0\Longrightarrow\frac{dy}{dx}=-\frac{F_{x}'}{F_{y}'}$
+ 记忆
	+ 1. 一定有负号；
	+ 2. $\frac{dy}{dx}=-\frac{F_{x}'}{F_{y}'}$ 中的 x 和 y 是交错对应的；

**证明**
+ 因为在隐函数 $F(x,y)$ 中：
	+ x 是对于 x 的函数：$x=x$
	+ y 是对于 x 的函数：$y=f(x)$
+ 所以当对 $F(x,y)=0$ 求导时，它们的求导链条为：$F<_{y}^x>x$
+ 所以分别对 x、y 求导后：$\frac{\partial F}{\partial x}+\frac{\partial E}{\partial y}\frac{dy}{dx}=0$
+ 转化位置，得到：$\frac{dy}{dx}=-\frac{F_{x}'}{F_{y}'}$

##### **定理**： #高阶隐函数存在定理
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $F(x,y,z)$ 在点 $M_{0}(x_{0},y_{0},z_{0})$ 邻域内连续可偏导，且 $F(x_{0},y_{0},z_{0})=0,F_{z}\:{\prime}(x_{0},y_{0},z_{0})\neq0$ 则由 $F(x,y,z)=0$ 在 $M_{0}$ 邻域内唯一确定一个连续可导函数 $z=\varphi(x,y)$ 且 $z_0=\varphi(x_0,y_0)$
> 则：$\frac{\partial z}{\partial x}=-\frac{F_{x}’}{F_{z}’},\frac{\partial z}{\partial y}=-\frac{F_{y}’}{F_{z}’}$

### 1.1.2 例题
**例题**：$e^xy^3-x^2+2y=1,\text{求}\frac{dy}{dx},\frac{d^2y}{dx^2}$
+ 分析
	+ $\text{依题目知,x为自变量,y为关于x的函数}$
+ 解析：求 $\frac{dy}{dx}$
	+ $$\begin{aligned}&e^{x}y^{3}-x^{2}+2y=1 \\&e^{x}y^{3}+e^{x}3y^{2}{\frac{dy}{dx}}-2x+2{\frac{dy}{dx}}=0 \\&\frac{dy}{dx}=\frac{2x-e^{x}y^{3}}{e^{x}3y^{2}+2}\end{aligned}$$
+ 解析：求 $\frac{d^2y}{dx^2}$
	+ $$
\begin{aligned}
&\text{求}\frac{d^{2}y}{dx^{2}},\text{这里对}e^{x}y^{3}+e^{x}3y^{2}\frac{dy}{dx}-2x+2\frac{dy}{dx}=0\text{再对x求导} \\
&e^{x}y^{3}+e^{x}3y^{2}{\frac{dy}{dx}}+e^{x}3y^{2}{\frac{dy}{dx}}+e^{x}6y({\frac{dy}{dx}})^{2}+e^{x}3y^{2}{\frac{d^{2}y}{dx^{2}}}-2+2{\frac{d^{2}y}{dx^{2}}}=0 \\
&\frac{d^{2}y}{dx^{2}}=\frac{2-e^{x}y^{3}-6e^{x}y^{2}\frac{dy}{dx}+e^{x}6y(\frac{dy}{dx})^{2}}{e^{x}3y^{2}+2} \\
&将{\frac{dy}{dx}}={\frac{2x-e^{x}y^{3}}{e^{x}3y^{2}+2}}{\text{代入}}
\end{aligned}
$$
+ 题型： #隐函数求导

**例题**：已知 $x^{2}+y^{2}-1=0$，当 $(0,1)$ 点处 XXXX，求一阶隐函数求导以及二阶隐函数求导；
+ 分析
	+ 注意是 $F(x,y)=0$
+ 解析：一阶
	+ 设 $F(x,y)=x^{2}+y^{2}-1$
	+ 可得：$F_{x}^{\prime}=2x，F_{y}^{\prime}=2y$
	+ 所以：$F(0,1)=0，F_{y}^{\prime}(0,1)=2\neq0$
	+ 带入公式：$\frac{dy}{dx}=-\frac{F_{x}^{\prime}}{Fy^{\prime}}=-\frac{2x}{2y}=-\frac{x}{y}$
+ 解析：二阶
	+ 对 $-\frac{x}{y}$ 中的 $x$ 再求一次导；
	+ $\frac{d^{2}y}{dx^{2}}=-\frac{y-xy^{\prime}}{y^{2}}=-\frac{y+x\frac{x}{y}}{y^{2}}$
+ 题型： #隐函数求导 