---
title: Lecture 49：对坐标的曲线积分
tags:
  - 数学
  - 曲线积分
categories: 
date: 2024-02-11
---
---
## 1.1 对坐标的曲线积分
### 1.1.1 基本概念
 ##### **定义**： #第二类曲线积分
> <font color="#ccc1d9">描述：</font>设 Г 为空间上一条从 $A$ 到 $B$ 的有向光滑曲线弧，向量值函数 $\mathbf{F}(x,y,z)=(P(x,y,z),Q(x,y,z),R(x,y,z))$ 定义在Г上，若对 Г 的任意分割和在局部弧段上任意取点，极限：
>      $\lim_{\lambda\to0}\sum_{k=1}^n\mathbf{F}(\xi_k,\eta_k,\zeta_k)\cdot\overline{P_{k-1}P_k}$ 
>      可以记作：$\int_\Gamma P(x,y,z)\operatorname{d}x+Q(x,y,z)\operatorname{d}y+R(x,y,z)\operatorname{d}z$

**解释**
+ L 称之为积分的弧段；L 是有向的；
+ 把 L 弧线切分成 n 份，对每一份求有向曲线做的功，然后求和；
+ 注意：
	+ 无论是二维的还是三维的曲线，它都是沿着一条曲线求曲线上做的功，因此都是一个符号 $\Gamma$ 来表示积分域；

**性质**
+ 1.  $\int_{L}p(x,y)dx+\int_{L}Q(x,y)dy=\int_{L}p(x,y)dx+Q(x,y)dy=\int_{L}F(x,y)\cdot dr$
+ 2. 两个力沿着同一条曲线做工，求它们做功的和：$\int_{L}(\alpha F_{1}(x,y)+\beta F_{2}(x,y))\cdot dr$ = $\alpha\int_{L}F_{1}(x,y)\cdot dr+\beta\int_{L}F_{2}(x,y)\cdot dr$
+ 3. $\int_{L}F(x,y)\cdot dr=\int_{L_{1}}F(x,y)\cdot dr+\int_{L_{2}}F(x,y)\cdot dr$

### 1.1.2 计算方法
##### **定理**： #第二类曲线积分的计算
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>当前参数方程为 $\begin{cases}x=\varphi(t)\\y=\psi(t)\end{cases}$，从起点 A 到终点 B 中，t 从 α 到 β   ，有：
>     $\int_{L}P(x,y)dx+Q(x,y)dy = \int_{\alpha}^{\beta}[p(\psi(t),\psi(t))\psi(t)+Q(\varphi(t),\psi(t))\psi^{\prime}(t)]dt$

**解释**
+ 注意：α 不一定比 β 小；所以不一定是从小的数到大的数进行积分；
