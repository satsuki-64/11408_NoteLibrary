---
title: Lecture39：全微分
tags:
  - 数学
  - 微分方程
  - 全微分
categories: 
date: 2024-02-02
---
---
## 1.1 全微分
### 1.1.1 全微分基本概念
##### **定义**： #全微分 
> <font color="#ccc1d9">描述：</font> $\text{设 }z=f(x,y)\text{ 在点 }(x,y)\text{ 的某邻域 }U(x,y)$ 内有定义。如果：
>   $\Delta z=f(x+\Delta x,y+\Delta y)-f(x,y)$
>    $=A\Delta x+B\Delta y+o(\rho)$，其中 A、B 时 x、y 的函数，与 $\Delta x$ 以及 $\Delta y$ 无关；
> 则称函数 $f(x,y)$ 在点 $(x,y)$ 处可微：
> $$
dz=Adx+Bdy
$$ 称之为其全微分；

**解释**
+ 多元函数的微分，就是全微分；
	+ 一元函数中的微分，只是考虑了 x 一个自变量导致的变化：
		+ $dy=A\Delta x$
	+ 在二元函数中，则是要将 x、y 两个变量导致的变化都表示出来：
		+ $dz=Adx+Bdy$
+ 偏增量和全增量
	+ 偏增量：$\begin{aligned}\Delta z_{x}=f\left(x_{0}+\Delta x,y_{0}\right)-f\left(x_{0},y_{0}\right)\\\Delta z_{y}=f\left(x_{0},y_{0}+\Delta y\right)-f\left(x_0,y_{0}\right)\end{aligned}$
	+ 全增量：$\Delta z=f(x_{0}+\Delta x,y_{0}+\Delta y)-f(x_{0},y_{0})$

**全微分的两个问题**
+ 二元函数有两个自变量：x、y
+ 一元微分的定义，和二元微分的定义在概念上是十分类似的；
+ 微分的两个问题
	+ 1. 是否可微分
		+ （一元微分）由于可微分就可导，因此可使用导数的性质进行判断；
		+ 二元微分是否有这样的结论？
	+ 2. 微分如何计算
		+ （一元微分）由于 $dy=f^{\prime}(x)dx$，所以可以用导数来求出 $dz=Adx$ 中的 A 的部分；
		+ 把微分的计算归结为导数的计算

### 1.1.2 全微分的性质
##### **定理**： #多元函数可微的必要条件
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>如果函数 $z=f(x,y)$ 在点 $(x,y)$ 处可微，则该函数在点 (x, y)的偏导数 $\frac{\partial z}{\partial x}$ 与 $\frac{\partial z}{\partial y}$ 必定存在，且：$dz=\frac{\partial z}{\partial x}\Delta x+\frac{\partial z}{\partial y}\Delta y$
> 注意：其中 
> 1.  $\frac{\partial z}{\partial x}$ 就是 $dz=Adx+Bdy$ 中的 A；
> 2.  $\frac{\partial z}{\partial y}$ 就是 $dz=Adx+Bdy$ 中的 B；

**解释**
+ 偏导数存在是可微分的必要不充分条件
+ 偏导数和微分的关系
	+ 可微 -> 可导
	+ 但可导 -×> 可微
	+ 前提
		+ ![[Pasted image 20240202215853.png]]
	+ 假设
		+ ![[Pasted image 20240202215648.png]]
	+ 则
		+ ![[Pasted image 20240202215656.png]]
	+ 导数是否存在？
		+ ![[Pasted image 20240202215737.png]]
		+ 所以对 X 的偏导数存在，因为等式右边的两项当中：
		+ 第一项是常数 A，第二项是无穷小量；
	+ 同理对 Y 的偏导数也存在，且等于 B ；
+ **可微 -> 可导**
+ **可导 -×> 可微**

**方法：** 用定义判断可微分性质；
+ 总结
	+ ![[Pasted image 20240202221901.png]]
+ 第一步：
	+ 判断 ![[Pasted image 20240202221343.png]]
		+ 首先按照多元函数微分的定义，它的两个偏导数都得存在；
	+ 但是
		+ ![[Pasted image 20240202222615.png]]
+ 第二步：
	+ 判断 ![[Pasted image 20240202221453.png]]
	+ 是否成立
	+ 即将 X 和 Y 的偏导数分别带入后，看是否符合；
	+ 即：
		+ ![[Pasted image 20240202221825.png]]

##### **定理**： #多元函数的连续性与可微性
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>如果函数 $z=f(x,y)\text{ 的偏导数 }\frac{\partial z}{\partial x},\frac{\partial z}{\partial y}$ 在点 $(x_0,y_0)\text{ 连续，则函数在该点可微分}$

**解释**
![[Pasted image 20240202223602.png]]

### 1.1.3 例题
**例题**：$\text{ 证明函数 }f(x,y)=\begin{cases}\frac{xy}{\sqrt{x^2+y^2}},&x^2+y^2\neq0,\\0,&x^2+y^2=0&\end{cases}\text{在点(0,0)处}$ 连续且偏导数存在，但不可微性；
+ 分析
+ 解析
	+ 首先：证明连续 -> 在（0，0）点极限存在 -> 证明极限值等于函数值；
		+ ![[Pasted image 20240202220448.png]]
		+ 由于夹逼定理可知：
			+ ![[Pasted image 20240202220641.png]]
			+ 所以
			+ ![[Pasted image 20240202220653.png]]
	+ 然后，证明偏导性
		+ X 的偏导 
			+ ![[Pasted image 20240202220958.png]]
		+ 同理，Y
	+ 因此证明了：
		+ ![[Pasted image 20240202221952.png]]
	+ 然后证明第二点：
		+ 首先，求
			+ ![[Pasted image 20240202222036.png]]
			+ 得到：
				+ ![[Pasted image 20240202222107.png]]
		+ 然后再带入：
			+ ![[Pasted image 20240202222135.png]]
			+ ![[Pasted image 20240202222258.png]]
+ 题型： #全微分 

## 1.2 总结
**微分的定义与关系**
![[Pasted image 20240202223854.png]]

**可微性的判定**
+ 方法一：定义法证明
	+ ![[Pasted image 20240202221901.png]]
+ 方法二：用关系证明
	+ 不连续 -> 不可微
	+ 不可导 -> 不可微
	+ 偏导连续 -> 可微