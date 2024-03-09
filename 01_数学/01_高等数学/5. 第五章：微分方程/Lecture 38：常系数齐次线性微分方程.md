---
title: Lecture 37：常系数齐次线性微分方程
tags:
  - 微分方程
  - 数学
categories: 
date: 2024-02-01
---
---
## 1.1 二阶常系数齐次微分方程
### 1.1.1 基本概念
##### **定义**： #二阶常系数齐次微分方程
> <font color="#ccc1d9">描述：</font> $y^n+py^{\prime}+qy=0$

**解释**
+ 常系数：$y^n+py^{\prime}+qy=0$
+ 变系数：$y^n+p(x)y^{\prime}+q(x)y=0$
	+ 通解 $y=C_1y_1(x)+C_2y_2(x)$
	+ y 1 和 y 2 是线性无关的；
	+ y 1/y 2 不等于常数；

**方法**
+ 第一步：写特征方程
+ 第二步：找出特征根
+ 第三步，根据根的方程，写出对应式子
	+ 若是不等实根 
		+ 通解： $y=C_1e^{r_1x}+C_2e^{r_2x}$
	+ 若是相等实根 
		+ 通解：$y=e^{rx}(C_1+C_2x)$
	+ 若是共轭复根 
		+ 通解：$y=e^{\alpha x}(C_1\cos\beta x+C_2\sin\beta x)$

**推导**
+ 假设：
	+ ![[Pasted image 20240201164449.png]]
+ 则当前的特征方程为
	+ ![[Pasted image 20240201164507.png]]
	+ 如果当前 ![[Pasted image 20240201164525.png]] 中 r 是方程的一个根，则表示 ![[Pasted image 20240201164545.png]] 为方程的一个解；
+ 设 r 1 和 r 2 为特征方程的两个根；
	+ 若是不等实根
		+ ![[Pasted image 20240201164936.png]]
		+ ![[Pasted image 20240201164806.png]]
		+ 因此：$y=C_1e^{r_1x}+C_2e^{r_2x}$
	+ 若是相等实根
		+ ![[Pasted image 20240201164930.png]]
		+ ![[Pasted image 20240201165043.png]]
		+ 因此：$y=e^{rx}(C_1+C_2x)$
	+ 若是共轭复根
		+ ![[Pasted image 20240201165118.png]]
		+ ![[Pasted image 20240201165353.png]]
		+ 因此：$y=e^{\alpha x}(C_1\cos\beta x+C_2\sin\beta x)$

### 1.1.2 例题

**例题**：$\text{求微分方程 }y^{\prime\prime}-2y^{\prime}-3y=0\quad\text{的通解}$
+ 分析
	+ 不等实根
+ 解析
	+ 写特征根
		+ ![[Pasted image 20240201173000.png]]
	+ 答案
		+ ![[Pasted image 20240201173042.png]]
+ 题型： #二阶常系数齐次微分方程 

**例题**：$\text{求微分方程}\quad y^{\prime\prime}+2y^{\prime}+y=\mathbf{0}\quad\text{的通解}.$
+ 分析
	+ 相等实根
+ 解析
	+ 写特征根
		+ ![[Pasted image 20240201173132.png]]
	+ 答案
		+ ![[Pasted image 20240201173232.png]]
+ 题型： #二阶常系数齐次微分方程 

**例题**：$\text{求微分方程 }y^{\prime\prime}+2y^{\prime}+3y=0\quad\text{的通解}.$
+ 分析
	+ 共轭实根
+ 解析
	+ 写特征根
		+ ![[Pasted image 20240201173343.png]]
	+ 写公式，套答案
		+ ![[Pasted image 20240201173442.png]]
+ 题型： #二阶常系数齐次微分方程 

**例题**：$\text{求微分方程}\quad y^{(4)}-2y^{(3)}+5y^{\prime\prime}=0\text{ 的通解}$
+ 分析
+ 解析
	+  四个根
		+ ![[Pasted image 20240201174042.png]]
	+ 两种情况下分别对应的项
		+ ![[Pasted image 20240201174145.png]]
	+ 最后结果为
		+ ![[Pasted image 20240201174245.png]]
+ 题型： #二阶常系数齐次微分方程 

### 1.1.3 不同实根情况总结
**四种情况**
![[Pasted image 20240201173846.png]]

**总结**
![[Pasted image 20240201174342.png]]