---
title: Lecture 43：多元函数的极值与最值
tags:
  - 数学
  - 多元函数
categories: 
date: 2024-02-07
---
---
## 1.1 多元函数的无条件极值
### 1.1.1 基本概念
##### **定义**： #多元函数的极值
> <font color="#ccc1d9">描述：</font>在一个领域中，多元函数的最大值或者最小值；

**解释**
+ 举例
+ $z=3x^{2}+4y^{2}在(0.0)$ 处为极小值；
+ $z=-\sqrt{x^{2}+y^{2}}在\quad(0.0)$ 处为最大值

##### **定义**： #多元函数的驻点
> <font color="#ccc1d9">描述：</font>多元函数偏导数等于 0 的点，称之为多元函数的驻点；

**解释**
+ $f_{x}^{\prime}=0.f_{y}^{\prime}=0$ 同时存在的点，称之为驻点；
##### **定理**： #多元函数极值存在的必要条件
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>如果 $z=f(x,y)$ 有偏导数，并且在 $(x_0,y_0)$ 处取得极值，则有：$f_{y}^{\prime}(x_{0},y_{0})=0，f_{y}^{\prime}(x_{0},y_{0})=0$

##### **定理**： #多元函数的驻点极值性判断
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>当 $z=f(x,y)\quad f^{\prime}(x,y_{0})=0\quad f^{\prime}(x,y_{0})=0$ 时，$A=f_{xx}^{\prime\prime}(x_{0},y_{0})B=f^{\prime\prime}(x_{0},y_{0})C=f^{\prime\prime}(x_{0},y_{0})$；
> 1. 如果是 $AC-B^{2}>0$，则有极值
> 	1. A<0，是极大值；
> 	2. A>0，是极小值；
> 2. 如果是 $AC-B^{2}<0$，则无极值
> 3. 如果是 $AC-B^{2}=0$，则无法判断

### 1.1.2 例题
**例题**：求 $f(x,y)=x^{3}-y^{3}+3x^{2}+3y^{2}-9x$ 的极值；
+ 分析
+ 解析
	+ 分别求偏导：
		+ $f_{x}^{\prime}=3x^{2}+6x-9$
		+ $f_{y}^{\prime}=-3y^{2}+6y$
	+ 得到
		+ $\begin{cases}x^{2}+2x-3=0\\-y^{2}+2y=0\end{cases}$
	+ 化简
		+ $(x+3)(x-1)=0$ 时，$x=-3或1$；
		+ $y(y-2)=0$ 时，$y=0或2$；
	+ 排列组合，得到驻点
		+ $(1,0),(1,2),(-3,0),(-3,2)$
	+ 求 A、B、C
		+ $f_{xx}^{\prime\prime}=6x+6$
		+ $f_{xy}^{\prime\prime}=0$
		+ $f_{yy}^{\prime\prime}=-6y+6$
	+ 当 (1,0)点时：
		+ $A=12.B=0.C=6$
		+ 所以 $AC-B^{2}=72>0$
		+ 所以是极小值点，即带入 $(1,0)$ 后得到的结果-5，为极小值点；
	+ 其他的同理
+ 题型： #多元函数的极值 

## 2.1 多元函数的条件极值：拉格朗日乘数法
### 2.1.1 基本概念
**无条件极值与条件极值**
+ 无条件
	+ 举例：找全校最高的人
+ 有条件
	+ 举例：找全校最高的、山东的、双子座的同学；
+ 加多条件越多，最值就越小

##### **定义**： #条件极值
> <font color="#ccc1d9">描述：</font>已知 $z=f(x,y)$，其极值在 $\varphi(x,y)=0$ 的条件之下，求其极值为条件极值；

**解释**
+ 在 $z=f(x,y)$ 中： $z=f(x,\varphi(x))$
+ 其中用 z 对 x 求导：$\frac{dz}{dx}=\frac{\partial f}{\partial x}+\frac{\partial f}{\partial y}\cdot\frac{dy}{dx}$ 
+ 写出 $\frac{dz}{dx}\vert_{x=x_{0}}=f^{\prime}(x_{0},y)+f^{\prime}(x_{0},y)\frac{dy}{dx}\vert_{x=x_{0}}=0$

## 3.1 多元函数的最值
### 3.1.1 基本概念
**多元函数得最值在哪些地方取到**
1. 驻点；
2. 偏导不存在的点；
3. 端点；
通常而言，最值就是在驻点，并且通常驻点就是一个；

**举例**：2 平方 m 的有盖长方体，长为 x，宽为 y，高为 $\frac{2}{xy}$，求 $\begin{aligned}A=2(xy+x\cdot\frac{2}{xy}+y\cdot\frac{2}{xy})=\\2(xy+\frac{2}{y}+\frac{2}{x})\end{aligned}$
+ 所以：$A_{x}=2(y-\frac{2}{x^{2}})=0A^{\prime}y=2(x-\frac{2}{y^{2}})=0$
+ 所以：$y=\frac{2}{x^{2}}，x=\frac{2}{y^{2}}，x=\frac{2}{\frac{4}{x^{4}}}$
+ 解得：$x^{3}=2,x=3\sqrt{2}y=3\sqrt{2},高3\sqrt{2}$

