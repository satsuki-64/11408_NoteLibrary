---
title: Lecture 56：幂级数
tags:
  - 数学
  - 无穷级数
categories: 
date: 2024-02-14
---
---
## 1.1 幂级数基本概念
### 1.1.1 基本概念
**数列**：每一项只和 n 有关
+ 数列： $u_{1},u_{2},\cdots,u_{n}$
+ 无穷级数：$u_{1}+u_{2}+\cdots+u_{n}+\cdots$

**函数列**：每一项和 n 以及 $x$ 有关
+ 假设 x 在区间 $I$ 上；
+ 函数列： $u_{1}(x), u_{2}(x), u_{n}(x),\cdots$
+ 函数项无穷级数：$u_{1}(x)+u_{2}(x)+\cdots+u_{n}(x)+\cdots$ 

**幂级数**
+ 幂级数： $a_{0}a_{1},a_{2}x^{2}\cdots a_{n}x^{n}\cdots$
+ 幂级数其实是函数项级数的最简单的一种，$x^{n}$ 就是 x 的函数，$a_n$ 就是一列数；
+ $a_0,a_1,a_2...a_n$ 称之为系数；

##### **定义**： #收敛点与发散点
> <font color="#ccc1d9">描述：</font>
> 1. 如果 $x_{0}\in I$ 时，$u_{1}(x)+u_{2}(x)+\cdots+u_{n}(x)+\cdots$ 收敛，则称 $x_o$ 为收敛点，如果是一段区间则称之为收敛域；
> 2. 如果 $x_{0}\in I$ 时，$u_{1}(x)+u_{2}(x)+\cdots+u_{n}(x)+\cdots$ 发散，则称 $x_o$ 为发散点，如果是一段区间则称之为发散域；
> 3. $S\left (x\right)=u\left (x\right)+u_{2\left (x\right)}+\cdots+u_{n}\left (x\right)+\cdots$ 称之为和函数，$\lim_{n\to\infty}S_n(x)=S\left(x\right)$；

**解释**
+ 一般就是求两个问题：收敛域是什么？和函数是什么？

**举例**
+ $1+x+x^{2}+x^{3}+\cdots+x^{n}+\cdots$
+ 此时：
	+ $|x|<1\text{时，收敛城(-1,1)}\frac{a}{1-q}=\frac{1}{1-x}$
	+ $|\times|\geq1 时，发散域(-\infty,-1)|U[1,+\infty]$

##### **定理**： #阿贝尔定理 
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> 
> $\sum_{n=0}^{+\infty}a_nx ，当x=x_0 时收敛,|x|<|x_0|时幂级数绝对收敛$
> $\sum_{n=0}^{+\infty}a_nx ，当x=x_0 时发散,|x|>|x_0|时幂级数发散$

**解释**

**推论**：收敛情况分析
+ 1. $\text{x=0时，收敛}$
+ 2. $x\in(-\infty+\infty)，\text{ 收敛}$
+ 3. $\text{|x|<R}，$ 绝对收敛，但 $-R，R 两个端点，可能收敛、可能发散$；
	+ R 为收敛半径；
	+ 收敛域的四种情况：$\left(-R,R\right),\left[-R,R\right),\left(-R,R\right],\left[-R,R\right]$；

### 1.1.2 求收敛半径 R
##### **定理**： #收敛半径判断
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>若 $\lim_{n\to\infty}\left|\frac{a_{n+1}}{a_{n}}\right|=\rho$，此时有三种情况：$R=\begin{cases}\frac{1}{\rho},&\rho\neq0\\+\infty,&\rho=0\\0,&\rho=+\infty\end{cases}$
> 也可以理解成：$\begin{cases}R=+\infty&\rho=0\\R=0&\rho=+\infty\\\frac{1}{\rho}&\rho\neq0\end{cases}$

**解释**
+ 情况一：ρ=0 时：$|\frac{a_{n+1}}{a_{n}}|\rightarrow0|a_{n+1}|比|a_{n}|为高阶无穷小，R=+\infty,x\in(-\infty,+\infty)都收敛；$ 
+ 情况二： $\rho=+\infty时：\vert\frac{a_{n+1}}{a_{n}}\vert\rightarrow+\infty，x只能在取0的时候收敛，所以R=0$；
+ 情况三：如果ρ是个常数，则 $R=\frac{1}{\rho}$ ； 

### 1.1.3 例题
**例题**：求 $x-\frac{x^{2}}{2}+\frac{x^{3}}{3}\cdots+(-1)^{n-1}\frac{x^{n}}{n}+\cdots$ 的收敛半径
+ 分析
+ 解析
	+ 因为 $\lim_{n\to\infty}\left|\frac{\frac{1}{n+1}}{\frac{1}{n}}\right|=1$ ，其结果为 1，所以其收敛半径就等于 1；
	+ 因为 $\lim_{n\to\infty}\left|\frac{\frac{1}{n+1}}{\frac{1}{n}}\right|=1=p,R=\frac{1}{p}=1$；
		+ 注意：不要漏掉了这里先等于 $\rho$，然后等于 $\rho$ 的倒数；
	+ 因此当前 $(-1,1)$ 为收敛区间，然后接下来单独判断-1 和 1 这两个端点；
	+ 当 x=-1 时，$-1-\frac{1}{2}-\frac{1}{3}-...\frac{1}{n}$ 是一个调和级数，发散；
	+ 当 x=1 时，$1-\frac{1}{2}+\frac{1}{3}-\frac{1}{4}$，是一个交错的调和级数，因此收敛；
	+ 所以 $(-1,1]$ 是收敛域；
+ 题型： #幂级数 

**例题**：求 $\sum_{n=0}^{+\infty}\frac{(2n)!}{(n!)^{2}}x^{2n}$ 的收敛半径
+ 分析
	+ **只有在奇数项时，才可以使用收敛半径判断定理**；
+ 解析
	+ 用比值审敛法，不用收敛半径判断定理；
	+ $\lim_{n\to+\infty}\frac{\frac{\left(2\left(n+1\right)\right)!}{\left(\left(n+1\right)!\right)^{2}}x^{2n+2}}{\frac{\left(2n\right)!}{\left(n!\right)^{2}}x^{2n}}$ $=4|x|^{2}<1$，$|x|<\frac{1}{2},R=\frac{1}{2}$
+ 题型： #幂级数

## 1.2 幂级数的运算
### 1.2.1 幂级数的运算性质
**性质 1**（逐项求导）：若 $\sum_{n=0}^{+\infty}a_{n}x^{n}$ 的和函数为 $S(x)$，则在它的收敛域上 $I$ 是连续的；

**性质 2**（逐项求积分）：若 $\sum_{n=0}^{\pm\infty}a_{n}x^{n}$ 的和函数 $S(x)$ 在 $I$ 上是可积的，则：
+ $\int_{0}^{x}s\left(t\right)dt=\int_{0}^{x}\left(\sum_{n=0}^{\infty}a_{n}t^{n}\right)dt$  $=\sum_{n=0}^{\infty}\int_{0}^{x}a_{n}t^{n}dt$ $=\sum_{n=0}^{\infty}\frac{a_{n}}{n+1}x^{n+1}\left(x\in I\right)$；
+ 逐项求积分后的幂级数，与原幂级数的收敛半径是相同的，但是在端点处是否收敛需要重新考察，进而才能得到新的收敛域；

**性质 3**：$\text{S(x)在(-R,R)内可导}$，$S^{\prime}(x)=(\sum_{n=0}^{\infty}a_{n}x^{n})^{\prime}=\sum_{n=0}^{\infty}(a_{n}x^{n})^{\prime}=\sum_{n=0}^{\infty}na_{n}x^{n-1}$