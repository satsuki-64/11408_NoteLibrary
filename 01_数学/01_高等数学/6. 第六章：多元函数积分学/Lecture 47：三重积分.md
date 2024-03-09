---
title: Lecture 47：三重积分
tags:
  - 数学
  - 三重积分
categories: 
date: 2024-02-09
---
---
## 1.1 三重积分
### 1.1.1 基本概念
##### **定义**： #三重积分 
> <font color="#ccc1d9">描述：</font> $\iiint_{\Omega}f(x,y,z)\mathrm{d}\mathbf{v}=\lim_{\lambda\to0}\sum_{k=1}^{n}f(\xi_{k},\eta_{k},\xi_{k})\Delta\nu_{k}$

**解释**
+ 概念解释
	+ 一个三元函数，在一个空间体 $\Omega$ 当中的积分；
	+ $\Delta\nu_{k}$ 为第 k 个小区域的几何体的体积；

**三重积分的计算**：直角坐标系计算
+ 核心思路：将三重积分的计算，转化成二重积分和定积分的计算；
+ 计算区域：$\Omega=\left\{(x,y,z)|z_1(x,y)\leq z\leq z_2(x,y),(x,y)\in D_{xy}\right\}$
	+ 对应几何图形：
	+ ![[Pasted image 20240209160019.png]]
+   核心公式：$\iiint_{\Omega}f (x, y, z)\mathrm{d}V=\iint_{D_{xy}}[\int_{z_{1}(x, y)}^{z_{2}(x, y)}f (x, y, z) dz|d\sigma$

### 1.1.2 例题
**例题**：计算 $I=\iint_0xyzd\nu$, 其中 $\Omega$ 由坐标面 $x=0,y=0,z=0\text{ 和平面 }x+y+z=1\text{ 所围成}.$
+ 分析
	+ ![[Pasted image 20240209161522.png]]
	+ 先对 z，后对 x、y；
+ 解析
	+ 先对 z 积分：原式 $=\int\int\left[\int f(x,y,z)dz\right]dxdy$
		+ 其中 z 的积分区域为 Dxy：
		+ ![[Pasted image 20240209161731.png]]
		+ 从 $x=0,y=0,z=0$ 的地方进，从 $1-x-y$ 地方出；
	+ ![[Pasted image 20240209162023.png]]
+ 题型： #三重积分 

**例题**：$\text{计算 }I=\iiint_{\Omega}z^2d\nu,\quad\Omega=\left\{(x,y,z)\frac{x^2}{a^2}+\frac{y^2}{b^2}+\frac{z^2}{c^2}\leq1\right\}$
+ 分析：直角坐标下的先 2 后 1；
	+ 根据积分域可知，这是一个球体：
	+ ![[Pasted image 20240209162428.png]]
	+ 这个题：先对 x、y 做，在对 z 做会更加方便；
	+ x、y 的区域：用 z=z 去截这个图形，得到的面为积分区域 -> 一个椭圆域；
+ 解析 
	+ ${I=\int dz\int\int z^2dxdy}$
	+ = $=\int_{-C}^{C}\left[z^{2}\pi\mathrm{ab}\left(1-\frac{z^{2}}{c^{2}}\right)\right]\mathrm{d}z$
+ 题型： #三重积分 

## 1.2 柱坐标计算三重积分
### 1.2.1 基本概念
**柱坐标基本概念**
+ 图示
	+ ![[Pasted image 20240209164105.png]]
+ 概念
	+ 基础元素： $\begin{matrix}0\leq\rho<+\infty\\0\leq\theta\leq2\pi\\-\infty<z<+\infty\end{matrix}$
	+ x、y、z：$\begin{aligned}x&=\rho\cos\theta\\y&=\rho\sin\theta\\z&=z\end{aligned}$
	+ $dv=\rho d\rho d\theta dz$
+ 公式
	+ $\iiint_\Omega f(x,y,z)d\nu=\iiint_{\Omega}f(\rho\cos\theta,\rho\sin\theta,z)\rho\operatorname{d}\rho\operatorname{d}\theta\operatorname{d}z$

### 1.2.2 例题
**例题**：$\text{计算 }I=\iiint_{(V)}\sqrt{x^2+y^2}\mathrm{~d}V\text{,其中(}(V)\text{ 由锥面 }z=\sqrt{x^2+y^2}$、$\text{圆柱面}\quad x^2+y^2=2x\text{ 及平面 z}=\mathbf{0}\quad\text{所围成}.$
+ 分析
+ 解析
	+ ![[Pasted image 20240209165830.png]]
+ 题型： #三重积分

## 1.3 球坐标计算三重积分
### 1.3.1 基本概念
**球坐标基本概念**
+ 图示
	+ ![[Pasted image 20240209170411.png]]
+ 基础元素
	+ $r$：空间中一个点，到原点的距离；
		+ $0\leq r<+\infty$
	+ $\varphi$：
		+ $0\leq\varphi\leq\pi$
	+ $\theta$ ：
		+ $0\leq\theta\leq 2\pi$
+ x、y、z
	+ $\begin{aligned}x&=r\sin\varphi\cos\theta\\y&=r\sin\varphi\sin\theta\\z&=r\cos\varphi\end{aligned}$
+ $\iiint_{\Omega}f(x,y,z)d\nu =\iiint_\Omega f (r\sin\varphi\cos\theta, r\sin\varphi\sin\theta, r\cos\varphi) r^2\sin\varphi\operatorname{d}r\operatorname{d}\varphi\operatorname{d}\theta$