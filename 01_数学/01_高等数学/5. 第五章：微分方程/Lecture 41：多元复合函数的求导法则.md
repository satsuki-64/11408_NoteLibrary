---
title: Lecture 40：多元复合函数的求导法则
tags:
  - 数学
  - 微分方程
categories: 
date: 2024-02-03
---
---
## 1.1 多元复合函数的求导法则
### 1.1.1 基本概念
##### **定理**： #多元复合函数的求导法则
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>设 $u=u(x,y),\quad v=v(x,y)$ 在点 $(x,y)$ 处有对 x 及对 $y$ 的偏导数，函数 $z=f(u,\nu)$ 在对应点 $(u,\nu)$ 处有连续偏导数，则 $z=f[u(x,y),v(x,y)]$ 在点 (x, y) 处的两个偏导数存在，且有：
> $\frac{\partial z}{\partial x}=\frac{\partial z}{\partial u}\frac{\partial u}{\partial x}+\frac{\partial z}{\partial\nu}\frac{\partial v}{\partial x},\quad\frac{\partial z}{\partial y}=\frac{\partial z}{\partial u}\frac{\partial u}{\partial y}+\frac{\partial z}{\partial\nu}\frac{\partial\nu}{\partial y}$

**核心**
+ 变量之间的树形图
+ ![[Pasted image 20240203042443.png]]

**解释**
+ 内层的偏导数存在（类似于一元导函数的导数存在）
+ z=f () 有连续偏导数（比可微分的条件还强）
+ 其中：
	+ $\frac{\partial z}{\partial x}=\frac{\partial z}{\partial u}\frac{\partial u}{\partial x}+\frac{\partial z}{\partial\nu}\frac{\partial v}{\partial x}$ 是对 X 的偏导数；

**证明：对 X 的部分证明**
![[Pasted image 20240203042310.png]]
+ 同理可对 Y 的部分证明；

### 1.1.2 例题
**例题**：$\text{设 }z=f(x+y,xy),\text{ 其中 }z=f(u,v)\text{ 可微,求}$：$\frac{\partial z}{\partial x},\frac{\partial z}{\partial y}$
+ 分析
	+ 当前的 z 的函数是由两个部分复合而成；
	+ $u=x+y,\quad v=xy$
+ 解析 1：使用定理代公式解题
	+ ![[Pasted image 20240203042922.png]]
	+ 更简洁的写法：
		+ ![[Pasted image 20240203043020.png]]
+ 题型： #多元复合函数的求导 

**例题**：$设$ u=f (x, y, z)$ 具有连续的二阶偏导数，$z=x\sin y$,求 $\frac{\partial^2u}{\partial y\partial x}$
+ 分析
	+ 基本关系
		+ ![[Pasted image 20240203162837.png]]
	+ 所以
		+ ![[Pasted image 20240203162843.png]]
+ 解析
	+ 先分析对 y 的求偏导：
		+ ![[Pasted image 20240203163147.png]]
	+ 然后再分析加上对 x 求偏导后的结果
		+ ![[Pasted image 20240203163224.png]]
+ 题型： #多元复合函数的求导法则

### 1.1.3 不同情况分析
**核心思想**
+ 第一步：画树形图
+ 第二步：根据树形图，画出偏导数

**情况 1：**$\text{设 }z=f(u,v),u=\varphi(x),v=\psi(x)\text{ 均可微,则}$
+ $\frac{dz}{dx}=\frac{\partial z}{\partial u}\frac{du}{dx}+\frac{\partial z}{\partial\nu}\frac{d\nu}{dx}$
+ 分析：
	+ 因为 u、v 对 z 是偏导数，所以是偏微分 $\partial$
	+ 因为如图所示的关系
		+ ![[Pasted image 20240203161930.png]]
	+ 所以 z 是对 x 的一元函数，所以 u 对 x 是直接求导；

**情况 2：**$\text{设 }w=f(u),u=\varphi(x,y,z)\text{ 均可微},$
+ $\frac{\partial w}{\partial x}=\frac{dw}{du}\frac{\partial u}{\partial x},\frac{\partial w}{\partial y}=\frac{dw}{du}\frac{\partial u}{\partial y},\frac{\partial w}{\partial z}=\frac{dw}{du}\frac{\partial u}{\partial z}$
+ 分析
	+ w 是对 xyz 的三元函数
	+ ![[Pasted image 20240203162158.png]]

**情况 3：**$\text{设 }u=f(x,y,z),z=\varphi(x,y)\text{ 均可微}$
+ $\frac{\partial u}{\partial x}=\frac{\partial f}{\partial x}+\frac{\partial f}{\partial z}\frac{\partial z}{\partial x},\frac{\partial u}{\partial y}=\frac{\partial f}{\partial y}+\frac{\partial f}{\partial z}\frac{\partial z}{\partial y}$
	+ 因为当中等式前面的 u 的含义和后背的 u 的含义不一样，所以在后背写成 f 以表示区分；
+ 分析
	+ ![[Pasted image 20240203162504.png]]

## 1.2 全微分形式的不变性
### 1.2.1 基本概念
**微分形式的不变性**
+ 因为 ${dy}=y_{x}^{\prime}dx =y_u^{\prime}\mathrm{du}$
+ 所以 $y_{x}^{\prime}dx$ 和 $y_u^{\prime}\mathrm{du}$ 完全一致 -> 微分形式的不变性；

##### **定理**： #全微分形式的不变性
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>设函数 $z=f(u,v),\quad u=u(x,v)$ 及 $\nu=\nu(x,y)$ 都有连续的一阶偏导数，则复合函数 $z=f[u(x,y),v(x,y)]$ 的全微分
> 不变性：$\mathbf{d}z=\frac{\partial z}{\partial x}\mathbf{d}x+\frac{\partial z}{\partial y}\mathbf{d}y$ $=\frac{\partial z}{\partial u}\operatorname{d}u+\frac{\partial z}{\partial\nu}\operatorname{d}\nu.$
> 即多元函数也具有微分形式的不变性；
> 由此推到而来：$\frac{\partial z}{\partial x}=\frac{\partial z}{\partial u}\frac{\partial u}{\partial x}+\frac{\partial z}{\partial\nu}\frac{\partial\nu}{\partial x},\quad\frac{\partial z}{\partial y}=\frac{\partial z}{\partial u}\frac{\partial u}{\partial y}+\frac{\partial z}{\partial v}\frac{\partial\nu}{\partial y}$

**解释**
+ 一元时：
	+ 无论当前是 x 的导数还是 u 的导数（无论是自变量还是中间变量），当前都是：
	+ **对这个变量的导数乘以对这个变量的微分**；
+ 多元时：
	+ 也有这样的结论； 
	+ 带入
		+ ![[Pasted image 20240203172405.png]]
		+ 
### 1.2.2 例题   
**例题**：$\text{设 }z=f(x+y,xy),\text{ 其中 }z=f(u,v)\text{ 可微,求 }\frac{\partial z}{\partial x},\frac{\partial z}{\partial y}$
+ 分析
+ 解析
	+ $dz=\frac{\partial f}{\partial u}du+\frac{\partial f}{\partial v}dv=\frac{\partial f}{\partial u}(dx+dy)+\frac{\partial f}{\partial V}(ydx+xdy)$
	+ 由不变性可知
	+  = $\frac{\partial f}{\partial x}dx+\frac{\partial f}{\partial y}dy$
	+ 然后因为是分别求 x、y，所以分开得：
	+ ![[Pasted image 20240203173251.png]]
+ 题型： #多元复合函数的求导法则

## 1.3 总结
**链式法则**
![[Pasted image 20240203173352.png]]