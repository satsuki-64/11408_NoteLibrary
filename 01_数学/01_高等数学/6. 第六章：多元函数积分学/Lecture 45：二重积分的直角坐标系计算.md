---
title: Lecture 45：二重积分的计算
tags:
  - 数学
  - 二重积分
categories: 
date: 2024-02-09
---
---
## 1.1 二重积分的计算
### 1.1.1 基本概念与方法
**核心思想**：把二重积分转化成一元定积分的计算，简化计算方法；

**X 型区域 （累次积分）**：$\int_{a}^{b}[\int_{y_{1}(x)}^{y_{2}(x)}f(x,y)dy]dx$ 或 $\int_a^b\mathbf{d}x\int_{y_1(x)}^{y_2(x)}f(x,y)\operatorname{d}y.$
+ 前提： $(\sigma)=\{(x,y)\mid a\leq x\leq b,y_1(x)\leq y\leq y_2(x)\}$
	+ 图示
		+ ![[Pasted image 20240209014016.png]]
	+ 对应的曲顶柱体的体积
		+ ![[Pasted image 20240209014221.png]]
+ 公式推理
	+ 曲边梯形面积求解：$S(x)=\int_{y_1(x)}^{y_2(x)}f(x,y)\mathsf{d}y.$
		+ 图示：![[Pasted image 20240209014547.png]]
	+ 曲边梯形体积求解：$V=\int_a^bS(x)\operatorname{d}x$
	+ 最终合并：$\int_{a}^{b}[\int_{y_{1}(x)}^{y_{2}(x)}f(x,y)dy]dx$
+ 特点
	+ 令 X 为常数，和边界最多交点只有两个；
	+ 先对 y 做定积分，再对 x 做定积分；
	+ 关键在于定限；

**Y 型区域**
+ 前提：$(\sigma)=\{(x,y)\mid x_1(y)\leq x\leq x_2(y),c\leq y\leq d\}$
	+ 图示：
		+ ![[Pasted image 20240209015118.png]]
+ 化成先 x 后 y 的两次一重定积分；
+ 公式：$\begin{aligned}\iint_{(\sigma)}f(x,y)\operatorname{d}\sigma&=\int_c^d[\int_{x_1(y)}^{x_2(y)}f(x,y)dx]\operatorname{d}y\\\\&=\int_c^d\operatorname{d}\left.y\right]_{x_1(y)}^{x_2(y)}f(x,y)\operatorname{d}x.\end{aligned}$

**非 X 非 Y 区域**
+ 图示
	+ ![[Pasted image 20240209015436.png]]
+ 一个复杂的、非 X 非 Y 的图形的二重积分，可以**通过分割的方式转化为：多个 X 型以及多个 Y 型的求和**；

### 1.1.2 例题
**例题**：$\text{计算}\iint_{(\sigma)}(x+y)d\sigma,\text{ 其中 }(\sigma)=\{(x,y)\mid0\leq x\leq1,0\leq y\leq2\}.$
+ 分析
	+ 即使 X 型也是 Y 型；
+ 解析：X 型区域计算
	+ 原式= $\int_{0}^{1}dx\int_{0}^{2}(x+y)dy$
	+ 算内层：= $\int_0^1[(xy+\frac12y^2)|_0^2]\mathrm{dx}$ $=\int_{0}^{1}[2x+2]dx$
	+ 算外层：$\int_{0}^{1}\left[2x+2\right]dx=1+2=3$
+ 题型： #二重积分