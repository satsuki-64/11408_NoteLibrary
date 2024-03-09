---
title: Lecture 48：对弧长的曲线积分
tags:
  - 数学
  - 曲线积分
categories: 
date: 2024-02-11
---
---
## 1.1 对弧长的曲线积分
### 1.1.1 基本概念
##### **定义**： #第一类曲线积分
> <font color="#ccc1d9">描述：</font>设 L 为 xOy 平面上的一条光滑的简单曲线弧，f (x, y)在 L 上有界，在 L 上任意插入一点列 $M_1,M_2,\ldots,M_n$ 把 L 分成 n 个小弧段 $\Delta L_i$ 的长度为 ds，又 $M_i\left(x,y\right)$ 是 L 上的任一点，作乘积 $f_i\left(x,y\right)ds$ ,并求和即 $\sum f_i\left(x,y\right)ds$ ,记λ=max(ds),若 $\sum f_i\left(x,y\right)ds$ 的极限在当入一 0 的时候存在，且极限值与 L 的分法及 $M_i$ 在 L 的取法无关，则称极限值为 f (x, y)在 L 上对弧长的曲线积分，记为 $:\int f\left(x,y\right)ds$ ; 其中 f (x, y)叫做被积函数，L 叫做积分曲线，对弧长的曲线积分也叫第一类曲线积分。 


**解释**
+ 在 L 直线上（三维空间中），对表示曲线密度的密度函数 $f(x,y,z)$ 求积分 $ds$ -> 表示三维空间中的一条曲线；

**推论**
+ 1.  $\int_{L_{1}+L_{2}}f(x,y)ds=\int_{L_{1}}f(x,y)ds+\int_{L_{2}}f(x,y)ds$；
+ 2. $\int_{L}[df(x,y)+\beta g(x,y)]ds=\alpha\int_{L}f(x,y)ds+\beta\int_{L}g(x,y)ds$；
+ 3. $\int_{C}f(x,y)ds=\int_{C_{1}}f(x,y)ds+\int_{C_{2}}f(x,y)ds$；
+ 4. $f(x,y)<=g(x,y) ; \int_{L}f(x,y)ds\leq\int_{L}g(x,y)ds$

### 1.1.2 曲线积分的计算
##### **定理**： #第一类曲线积分的计算
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>假设 L 的参数方程为 $\begin{cases}x=\varphi(t),\\y=\psi(t),&\end{cases}(\alpha\leqslant t\leqslant\beta)$，则 $\int_{L}f(x,y)\mathrm{d}s=\int_{\alpha}^{\beta}f(\varphi(t),\psi(t))\sqrt{\varphi'(t)^2+\psi'(t)^2}\mathrm{d}t$

**解释**
+ 注意：α < β 

### 1.1.3 例题
**例题**：已知求曲线的定积分 $\int_{L}\sqrt{y}ds$，其中曲线为 $L:y=x^{2}，经过了：O(0.0)，B(1.1)$ 点，
+ 分析
+ 解析
	+ $原式 =\int_{0}^{1}x\cdot\sqrt{1+4x^{2}}d\frac{x^{2}}{x^{2}}$
+ 题型： #曲线积分 

**例题**：求圆弧形的曲线积分：$I=\int y^{2}ds$
+ 分析
+ 解析
	+ ![[Pasted image 20240211205454.png]]
+ 题型： #曲线积分 

