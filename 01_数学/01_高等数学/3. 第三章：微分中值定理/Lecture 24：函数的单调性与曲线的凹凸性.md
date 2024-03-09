---
title: Lecture 24：函数的单调性与曲线的凹凸性
tags: 
categories: 
date: 2024-01-13
---
---
## 1.1 函数单调性的判断方法
### 1.1.1 单调增减的几何意义
**单调增和单调减**
+ 导数和单调增减的关系
	+ ![[Pasted image 20240113174945.png]]


##### **定理**：单调增减与导数
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{设函数 }f(x)\text{ 在区间 }[a,b]\text{ 上连续},\text{ 在 }(a,b)\text{ 内可导,则}$
> 1）$\text{如果在(}a,b)\text{ 内 }f^{\prime}(x)\geq0,\text{ 且等号只在有限个点上成立}$，则 $f(x)$ 在 $[a,b]$ 上单调增加
> 2）$\text{如果在(}a,b)\text{ 内 }f^{\prime}(x){\leq}0,\text{ 且等号只在有限个点上成立,}$ 则 $\text{则 }f(x)\text{ 在 }[a,b]\text{ 上单调减少}$
> 

**解释**
+ 注意：此条件 `等号只在有限个点上成立` ，即导数等于零的位置点是有限个，

**推论 1**：

**推论 2**：


### 1.1.2 例题
**例题**：$\text{确定 }f(x)=e^x-x-1\text{ 的增减区间}$
+ 分析
	+ 题型：利用单调增减性的定理，分析增减区间；
	+ 分析过程：$f^{\prime}(x)=e^x_{-1}=0\Rightarrow\mathrm{x=0}$
+ 解析
	+ 解答过程：
		+ $(-\infty, 0), f (x)<0\Rightarrow f (x)\downarrow$
		+ $(0,+\infty) f^{\prime}(x)>0 \Rightarrow f(x)$

**例题**：$\text{试证 }x>0\text{ 时,}x-\frac{x^3}6<\sin x<x$
+ 题型
	+ #使用单调性证明不等式
+ 解析
	+ 先分析 $sinx$ 和 $x$ 的关系
	+ $\begin{aligned}&f(x)=X-h^{\prime}x,\quad f(0)=0\\&f^{\prime}(x)=1-\cos x\geqslant0\quad,\quad f(x)\quad[0,a]\quad1\to(0,+\infty)\end{aligned}$
	+ 同理为右边不等式的关系；

## 1.2 曲线的凹凸性和拐点
### 1.2.1 凹凸性的基本概念
##### **定义**：凹凸的定义
> <font color="#ccc1d9">描述：</font> $\text{设函数}f(x)\text{在区间 }I\text{ 上连续, 如果对}$$I$ 上任意两点 $x_1,x_2$ 
> 1）恒有 $f(\frac{x_1+x_2}2)<\frac{f(x_1)+f(x_2)}2$，$则称  f(x)\text{ 在 }I\text{ 上的图形是凹的}$
> 2）如果恒有 $f(\frac{x_1+x_2}2)>\frac{f(x_1)+f(x_2)}2$，则称 $f(x)$ 在 $I$ 上的图形是凸的

**解释**
+ 几何意义
	+ 凹
		+ ![[Pasted image 20240113182849.png]]
		+ 其斜率在增加，即一阶导数在增加 -> 二阶导数大于零；
	+ 凸
		+ ![[Pasted image 20240113182901.png]]
		+ 其斜率在减少，即一阶导数在减少 -> 二阶导数小于零；

##### **定理**：凹凸性判定
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{设函数}f(x)\text{ 在区间 }[a,b]\text{ 上连续},\text{ 在 }(a,b)\text{ 内二阶可导},$
> 1）$\text{若在 }(a,b)\text{ 内 }f^{\prime\prime}(x)\text{>0, 则 }f(x)\text{ 在 }[a,b]\text{ 上的图形是凹的}$；
> 2）$\text{若在 }(a,b)\text{ 内 }f^{\prime\prime}(x)<0,\text{ 则 }f(x)\text{ 在 }[a,b]\text{ 上的图形是凸的}$

##### **定义**：拐点
> <font color="#ccc1d9">描述：</font>连续曲线上，凹凸的分界点

**解释**
 找拐点可以在这些位置：
+ ${f^{\prime\prime}(x_0)=0}$
+ 或者是二阶导数不存在的点；

### 1.2.2 例题
**例题**：$\text{判定曲线 }y=x^3\text{ 的凹凸性}$
+ 分析
	+ 分析过程：
+ 解析
	+ 解答过程：
	+ $y^{\prime}=3x^{2},y^{\prime\prime}=6x$
	+ $\begin{aligned}(-无限,0),y^{\prime\prime}<0,&\text{凸}\\(0,+无限),&y^{\prime\prime}>0\end{aligned}$
+ 推导结论
	+ 在函数的一点位置，函数的凹凸性发生变化，则称这一点为拐点
	+ ![[Pasted image 20240113184015.png]]
	+ 即：**拐点为二阶导数等于零的点**；

**例题**：$h(x)=\sqrt[3]{x}$，求它的凹凸区间以及拐点；
+ 分析
	+ 找拐点可以在这些位置：
		+ ${f^{\prime\prime}(x_0)=0}$
		+ 或者是二阶导数不存在的点；
+ 解析
	+ $\begin{aligned}h^{\prime}(x)&=\frac{1}{3}x^{-\frac{2}{3}}\\h^{\prime\prime}(x)&=-\frac{2}{9}x^{-\frac{5}{3}}=-\frac{2}{9x^{\frac{5}{3}}}\quad h^{\prime\prime}(0)\text{不存在}\end{aligned}$
	+ $\begin{aligned}&\color{red}{(-\infty,0)},\quad\color{red}{f^{\prime\prime}(x)>0},\quad\color{red}{\boxed4}\\&\color{red}{(0,+\infty)}\quad\color{red}{f^{\prime\prime}(x)<0},\quad\color{red}{\boxed4}\end{aligned}$
+ 题型
	+ #求拐点的方法

