---
title: Lecture 21：微分中值定理
tags:
  - 数学
categories: 
date: 2023-12-25
---
---
## 1.1 微分中值定理
**目的**：为什么需要微分中值定理 -> 建立导数和函数的关系；

**基本概念**
+ 三大定理的意义
	+ 罗尔定理: $存在\xi\in(a,b)\text{,使 }f^{\prime}(\xi)=0$
	+ 拉格朗日中值定理 ：$f(b)-f(a)=f^{\prime}(\xi)(b-a)$
		+ 建立了局部与整体的关系
			+ 导数反应的是一点的变化率，是一个局部；
			+ 但 (a，b)是一个整体区间的变化；
			+ 所以：$f(b)-f(a)=f^{\prime}(\xi)(b-a)$ 建立了局部与整体之间的关系；
		+ 建立了函数值和导数值之间的关系
			+ 为：用导数研究函数，奠定了理论基础；
	+ 柯西中值定理

**三大定理的关系**
+ ![[Pasted image 20231225234350.png]]
+ 柯西定理是最一般的定理；

**适用范围**
+ 证明恒等式
+ 证明不等式
+ 证明有关中值问题的结论

---

## 1.2 罗尔定理
##### **定义**：极大值与极小值
> <font color="#ccc1d9">描述：</font> $若  \exists\delta>0\text{,使得}$ 
>   极小值： $\forall x\in U(x_0,\delta)\text{ 恒有 }f(x)\geq f(x_0)\text{,则称 }f(x)\text{ 在 }x_0\text{取极小值}$
>   极大值：$\forall x\in U(x_0,\delta)\text{ 恒有 }f(x)\leq f(x_0)\text{,则称 }f(x)\text{ 在 }x_0\text{ 取极大值}$

**解释**
因为这一点为极大值或者极小值，因此在极值这一点的斜率肯定和 Y 轴垂直；

**引理**：费马引理
+ $\text{若 }f(x)\text{ 在 }x_0\text{处取得极值,且 }f(x)\text{ 在 }x_0\text{ 处可导,则}$
	+ 极值点 $f^{\prime}(x_0)=0$

##### **定理**：罗尔定理
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>若满足三个条件：
> 1）$f$ 在 $[a,b]$ 上连续；
> 2）$f$ 在 $(a,b)$ 内可导；
> 3）f (a)=f (b)
> 则可知：$\text{则 }\exists\xi\in(a,b)\text{,使 }f^{\prime}(\xi)=0$


**解释**
推导关系：【定义】极大值与极小值 -> 【定理】费马引理 -> 【定理】罗尔定理
+ 图示
	+ ![[Pasted image 20231225142739.png]]
---
## 1.3 拉格朗日中值定理
##### **定理**：拉格朗日中值定理
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>若满足以下几个条件：
>   1）$f$ 在 $[a,b]$ 上连续 
>   2）$f$ 在 ($a,b)$ 内可导
>   则：$\text{可得 }\exists\xi\in(a,b)\text{,使 }f(b)-f(a)=f^{\prime}(\xi)(b-a)$

**补充**
+ $a>b,a<b\quad\text{结论都成立}$
+ 改写形式：$f(b)-b(a)=f^{\prime}[a+\theta(b-a)](b-a)\quad(0<\theta<1)$
+ **重要**->改写形式：$f(x_0+\Delta x)-f(x_0)=f^{\prime}[x_0+\theta\Delta x]\Delta x\quad(0<\theta<1)$
	+ 这种形式是以下微分近似形式的精确描述：$\Delta y\approx f^{\prime}(x_0)\Delta x$

**解释**
+ 图示
	+ ![[Pasted image 20231225143334.png]]
+ 没有了 f (a)=f (b)的限制条件，所以不一定有切线平行 X 轴；
+ 但是会有一点的斜率和当前函数值连线相等：
	+ ![[Pasted image 20231225143547.png]]

**推论 1**：有限增量公式
+ $f(x_0+\Delta x)-f(x_0)=f^{\prime}[x_0+\theta\Delta x]\Delta x\quad(0<\theta<1)$
+ 近似描述：$\Delta y\approx f^{\prime}(x_0)\Delta x$

**推论 2**：$\text{设 }f(x)\text{ 在区间 }I\text{ 上连续,在 }I\text{ 内可导,则在}$$I\text{ 上 }f(x)\equiv C\Leftrightarrow f^{\prime}(x)\equiv0$
+ 左推导右是很明显的；
+ 关键在于右怎么推左；

**证明**：使用分析法证明拉格朗日中值定理
+ 核心方法：**构造特殊函数，使用罗尔定理**
	+ 目标是证明：$\exists\xi\in(a,b)\text{,使 }f(b)-f(a)=f^{\prime}(\xi)(b-a)$
	+ 所以等于证明：$f^{\prime}(\xi)-\frac{f(b)-f(a)}{b-a}=0$
	+ 所以可以设置一个函数 $F^{\prime}(\xi)=0$
	+ 因此可得：令 $F (x)=f (x)-\frac{f (b)-f (a)}{b-a}x$
	+ 所以根据摩尔定理： $F^{\prime}(\xi)=0$

### 1.2.1 例题
**例题**：$\text{试证}\quad|\sin x-\sin y|\leq|x-y|$
+ 分析
	+ 分析过程：
+ 解析
+ 结论：$\mathrm{~sinx<x<tanx,x\in(0,\frac\pi2)}$


**例题**：$\text{证明:当 }x\in(0,\frac\pi2)\text{ 时, }\arctan x+\arctan\frac1x=\frac\pi2.$
+ 分析
	+ 因为是要证明一个函数值在一个范围内等于一个常数，所以可以考虑使用{拉格朗日中值定理的推论 2}；
+ 解析
	+ $f^{\prime}(x)=\frac{1}{1+x^{2}}+\frac{-\frac{1}{x^{2}}}{1+(\frac{1}{x})^{2}}=0.$
	+ 因此导数等于 0，根据推论 2->当前函数值在范围内为一个常数；
	+ 所以随便带入一个点，即可得到当前函数值恒定为 $\pi/2$
---
## 1.4 柯西中值定理
##### **定理**：柯西中值定理
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>若满足以下条件： 
> 1）$f,F\text{ 在 }[a,b]\text{上连续};$
> 2）$f,F\text{ 在 }(a,b)\text{ 内可导,且 }\forall x\in(a,b),F^{\prime}(x)\neq0$
> 则：$\exists\xi\in(a,b)\text{ ,使 }\frac{f(b)-f(a)}{F(b)-F(a)}=\frac{f^{\prime}(\xi)}{F^{\prime}(\xi)}$

**解释**
+ 几何含义
	+ ![[Pasted image 20231225225323.png]]
+ 举例
	+ $\lim_{x\to0}\frac{x-\sin x}{x^3}=\lim_{x\to0}\frac{(x-\sin x)-(0-\sin^{}0)}{x^3-0^3}$
	+ 由柯西中值定理 $\frac{f(b)-f(a)}{F(b)-F(a)}=\frac{f^{\prime}(\xi)}{F^{\prime}(\xi)}$，可知因此可得：$\lim_{x\to0}\frac{1-\cos^2}{3\xi^2}$
	+ 所以当前 $\xi$ 位于 $x$ 和 $0$ 之间
	+ 所以得到 $\lim_{x\to0}\frac{1-\cos x}{3x^{2}}=\lim_{x\to0}\frac{\frac{1}{2}x^{2}}{3x^{2}}.$
	+ 最后结果为 1/6；