---
title: Lecture 38：常系数非齐次线性微分方程
tags:
  - 数学
  - 微分方程
categories: 
date: 2024-02-02
---
---
## 1.1 非齐次微分方程
### 1.1.1 基本概念
**什么是非齐次线性微分放长**
+ 阶数不一致：$y^{\prime\prime}+py^{\prime}+qy=f(x)$
+ 解决思路：将不齐次的方程，转 化为两个部分：
	+ 非齐次 = 齐次的通解 + 非齐次的特解

+ 求特解
	+ **情况 1**：若非齐次项是 $f(x)=e^{\lambda x}P_{m}(x)$
		+ 此时待定特解为：$y^{*}=x^{k}Q_{m}(x)e^{\lambda x}$
	+ **情况 2**：若非齐次项是指数×多项式×三角 $f(x)=e^{\alpha}[P_l(x)\cos\beta x+Q_n(x)\sin\beta x]$
		+ $y^{\bullet}=x^{k}e^{\alpha x}\bigl[R_{m}^{(1)}(x)\cos\beta x+R_{m}^{(2)}(x)\sin\beta x\bigr].\quad m=\max\{l,n\}$
### 1.1.2 例题
**例题**：$\text{求微分方程 }y^{\prime\prime}-2y^{\prime}-3y=3x+1\text{ 的通解}$
+ 分析
	+ 这是一个**二阶、线性、常系数、非齐次**
	+ 因此：**先求齐次通解**
+ 解析
	+ 特征方程和特征根，得出齐次的通解：
		+ ![[Pasted image 20240202191313.png]]
	+ 设 y 星号
		+ 因为 3 x+1 符合 $f(x)=e^{\lambda x}P_{m}(x)$ 的形式，同时因为它没有 e，因此表示 e 的次数为 0；
		+ 待定特解：
			+ ![[Pasted image 20240202191516.png]]
		+ 带入原方程
			+ 设 y 星号为其特定解；
			+ 因此求导得到的，就是 y 一撇和 y 二撇的特定解；
			+  ![[Pasted image 20240202191556.png]]
		+ 解系数
			+ ![[Pasted image 20240202191902.png]]
		+ 然后可以写其通解
			+ 通解 = 齐次的通解 + 非齐次的特解
			+ ![[Pasted image 20240202192036.png]]
			+ 齐次的通解 
				+ ![[Pasted image 20240202192113.png]]
			+ 非齐次的特解 
				+ ![[Pasted image 20240202192127.png]]
+ 题型：# 