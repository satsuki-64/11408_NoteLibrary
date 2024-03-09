---
title: Lecture 46：二重积分的极坐标系计算
tags:
  - 数学
  - 二重积分
categories: 
date: 2024-02-09
---
---
## 1.1 极坐标系计算
### 1.1.1 基本概念
**极坐标表示**
+ $x=\rho\cos\theta,\quad y=\rho\sin\theta\quad(0\leq\rho<+\infty,0\leq\theta\leq2\pi)$
+ $f(x,y)=f(\rho\cos\theta,\rho\sin\theta)$
+ $\Delta\sigma=\frac12[(\rho+\Delta\rho)^2\Delta\theta-\rho^2\Delta\theta]$ = $\rho\Delta\rho\Delta\theta+\frac12(\Lambda\rho)^2\Delta\theta.$
	+ 图示：
	+ ![[Pasted image 20240209021559.png]]

+ 即：
	+ $\Delta\sigma\approx\rho\Delta\rho\Delta\theta$
	+ ${d\sigma=\rho d\rho d\theta.}$

**公式**
+ $\iint_{(\sigma)}f(x,y)\operatorname{d}\sigma=\iint_{(\sigma)}f(\rho\cos\theta,\rho\sin\theta){\rho\operatorname{d}\rho\operatorname{d}\theta}.$
+ 举例
	+ 图示：
		+ ![[Pasted image 20240209022052.png]]
	+ 对应公式：
		+ $=\int_{\alpha}^{\beta}d\theta\int_{\beta_{1}(\theta)}f(\mu_{0}\cdot\rho_{n+0})\rho\mathrm{d}$

### 1.1.2 例题
**例题**：计算 $I=\iint \left ( x^2+ y^2\right ) $d$ \sigma$  其中 $(\sigma)$ 为不等式 $(\sigma)$ $1\leq x^2+y^2\leq4,x\geq0,y\geq0\text{所确定的区域}$
+ 分析
	+ ![[Pasted image 20240209022544.png]]
+ 解析
	+ 原式= $\int_{0}^{\frac{\pi}{2}}\int_{1}^{2}\rho^{2}\rho d\rho$
+ 题型： #二重积分 

## 1.2 总结
**直角坐标计算**
$$
\begin{aligned}&\text{1)先 y 后 }\mathbf{x}\quad\iint_{D}f(\mathbf{x},\mathbf{y})\mathrm{d}\sigma=\int_{a}^{b}d\mathbf{x}\int_{\phi_1(\mathbf{x})}^{\phi_2(\mathbf{x})}f(\mathbf{x},\mathbf{y})d\mathbf{y}\\&\text{2)先 x 后 }y\quad\iint_{D}f(\mathbf{x},\mathbf{y})\mathrm{d}\sigma=\int_{c}^{d}dy\int_{\psi_1(\mathbf{y})}^{\psi_2(\mathbf{y})}f(\mathbf{x},\mathbf{y})d\mathbf{x}\end{aligned}
$$

**极坐标计算**
$$
1\text{)先}\rho\text{ 后 }\theta\iint_{D}f(x,y)\mathsf{d}\sigma=\int_{\alpha}^{\beta}d\theta\int_{\varphi_{1}(\theta)}^{\varphi_{2}(\theta)}f(\rho\cos\theta,\rho\sin\theta)\rho\mathsf{d}\rho 
$$

**适合用极坐标的情况**
![[Pasted image 20240209023830.png]]