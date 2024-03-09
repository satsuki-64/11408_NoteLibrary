---
title: Lecture 50：曲面积分
tags:
  - 数学
  - 曲面积分
categories: 
date: 2024-02-12
---
---
## 1.1 格林公式
### 1.1.1 基本概念
**概念引入**
+ 在一个平面闭区域 D 的二重积分上，是否可以升级只求边界曲线 L 上值得相差，而不计算曲面上的所有点的值；
+ 这个作用由格林公式达成；

##### **定义**： #单连通区域 
> <font color="#ccc1d9">描述：</font>假设在 D 平面区域内，D 内任意一闭曲线围成的部分都居于 D；否则则称之为复连通区域；


**解释**
+ 无洞无眼；

##### **定理**： #格林公式
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>闭区域 D 上由分段光滑的曲线 L 围成的，$P(x,y)、Q(x,y)$ 在 D 上有一阶连续偏导；则：
>     $\int_{D}\left(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\right)dxdy=\oint_{L}Pdx+Qdy$
>     

**解释**
+ 注意：格林公式使用的范围 -> 必须是在闭区域上；
+ 其中：L 是区域 D 的正方向的边界曲线；
+ $\int_{D}\left(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\right)dxdy$ ：是在区域 D 上的一个普通的二重积分；
+ $\oint_{L}Pdx+Qdy$ ：是在曲线的闭曲线上的曲线积分，并且是一个一重积分；

**题型**：
+ 题型一：从右往左出；
+ 题型二：从左往右出；

**应用**
+ 1. $P=-y，Q=x，\frac{\partial\alpha}{\partial x}=1，\frac{\partial P}{\partial y}=-1，2\int\int D dxdy=\oint_{L}xdy-ydx$
	+ 所以：$A=\frac{1}{2}\oint_{L}xdy-ydx$

### 1.1.2 例题
**例题**：$\phi_{L}x^{2}ydx-xy^{2}dy.\quad L:正向圆周x^{2}+y^{2}=a^{2}P=x^{2}y，Q=-xy^{2}$
+ 分析
+ 解析
	+ 先套公式的前一半：$\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}=-y^{2}-x^{2}$
	+ 然后带入积分式：$\int_{D}\left ((-y^{2}-x^{2}) dxdy=-\int_{0}^{2\pi}d\theta\int_{0}^{a}p^{2}\cdot pdP=-\frac{\pi}{2}a^{4}\right.$
+ 题型：#