---
title: Lecture 28：不定积分
tags:
  - 数学
  - 不定积分
categories: 
date: 2024-01-17
---
---
## 本章常考题型与典型例题
**考试内容**
+ (一)不定积分的概念与性质
+ (二)不定积分基本公式 
+ (三)三种主要积分法
+ (四)三类常见可积函数的积分

**常考题型**
+ 求不定积分 (换元、分部)

## 1.1 什么是不定积分
**知识点分布**
+ 2+3+3
+ 2：两个概念 `->` 1. 原函数； 2. 不定积分；
+ 3：三种方法：两类换元+分布；
+ 3：三类常见积分

**重点**：三种方法 `->` 两类换元+分布；

**尺度**：基本的不定积分方法掌握即可；

### 1.1.1 基本概念
**原函数**
+ 概念：
	+ $F^{\prime}(x)=f(x)$
	+ $G^{\prime}(x)=f(x)$
+ 则：$G(x)-F(x)=C$ 

##### **定义**： #不定积分
> <font color="#ccc1d9">描述：</font>一个函数 $f(x)$ 的不定积分（或者说是原函数）是一个导数等于 $f(x)$ 的函数 $F(x)$ ，即 F′(x) = f (x)，或写成 $[F (x)+c]^{\prime}=f (x)$
> 或者：$\int f(x)dx=F(x)+C$

**解释**
+ 概念：
	+ 不定积分就是 $f(x)$ 原函数的一般表达式；
+ 举例：
	+ 比如在 $\int f_{(x)}dx=F_{(x)}+C$ 中：
	+ 设 $F(x)$ 是函数 $f(x)$ 的一个原函数；
	+ 把函数 $f(x)$ 的所有原函数 $F(x)+C$ 叫做函数 $f(x)$ 的不定积分，又叫做函数 $f(x)$ 的反导数；
+ 符号：
	+ $\int$ ：积分号；
	+ $f(x)$：被积函数；
	+ $dx$：积分变量；
	+ $f(x)dx$：被积式
	+ $C$：积分常数；

**不定积分的几何意义**
+ 一组在 Y 轴上相差常数大小的曲线；
### 1.1.2 原函数存在性
##### **定理**： #原函数存在定理
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>
> 1. 若 $f(x)$ 在区间 $I$ 上连续, 则 $f(x)$ 在区间 $I$ 上一定存在原函数；
> 2. 若 $f(x)$ 在区间 $I$ 上有第一类间断点，则 $f(x)$ 在区间 $I$ 上没有原函数；

**解释**
+ 关系：
	+ 连续的函数，一定存在原函数;
	+ 连续 `->` 存在原函数；
	+ 存在原函数 `-X>` 连续；
+ 结论：
	+ 不连续的函数可能会有原函数，但此函数不可以有第一类间断点，可以为第二类间断点；

**举例**
+ $g(x)=\operatorname{sgn}x=\begin{cases}-1,&x<0,\\0,&x=0,\\1,&x>0.&\end{cases}$ 有跳跃间断点 `->` 属于第一类间断点 `->` 没有原函数；
+ 原因：此函数在 $x=0$ 处的原函数为 $|x|+c$ ，而此函数不可导 `->` 零点这里就没有原函数；

### 1.1.3 不定积分基本性质
**性质 1**：
+  $(\int f(x)\mathrm{d}x)^{\prime}=f(x)$
+ $\mathrm{d}\int f(x)\mathrm{d}x=f(x)\mathrm{d}x$

**性质 2**：
+ $\int f^{\prime}(x)\operatorname{d}x=f(x)+C$
+ $\int\operatorname{d}f(x)=f(x)+C$

**性质 3**：
+ $\int[f(x)\pm g(x)]\operatorname{d}x=\int f(x)\operatorname{d}x\pm\int g(x)\operatorname{d}x$

**性质 4**：
+ $\int kf(x)\operatorname{d}x=k\int f(x)\operatorname{d}x$



## 1.2 常见积分公式
$1、\int adx=ax+C\:,\:a$ 是常数 
$2、\int x^{a}dx=\frac{x^{a+1}}{a+1}+C$ ,其中 a 为常数，且 $a\neq-1$
$3、\int\frac{1}{x}dx=\ln|x|+C$
$4、\int e^{x}dx=e^{x}+C$ 
$5、\int a^{x}dx=\frac{1}{\ln a}a^{x}+C$ ,其中 $a>0\:,\:目a\neq1$
$6、\int\sin xdx=-\cos x+C$
7、$\int\cos xdx=\sin x+C$ 
$8、\int\sec^{2}xdx=\tan x+C$ 
$9、\int\csc^{2}xdx=-\cot x+C$ 
$10、\int\tan xdx=-\ln|\cos x|+C$
$11、\int\cot xdx=\ln\lvert\sin x\rvert+C$
$12、\int\sec xdx=\ln\lvert\sec x+\tan x\rvert+C$
$13、\int\csc xdx=-\ln\lvert\csc x+\cot x\rvert+C$
$14、\int\frac{dx}{1+x^2}=\arctan x+C$
$15、\int\frac1{\sqrt{a^2-x^2}}dx=\arcsin\frac xa+C$
$16、\int\frac1{x^2-a^2}dx=\frac1{2a}\ln\left|\frac{x-a}{x+a}\right|+C$
$17、\int\frac{dx}{\sqrt{1-x^2}}=\arcsin x+C$
$18、 \int\frac 1{a^2+x^2}dx=\frac 1 a\arctan\frac xa+C$ 
$19、\int\frac{dx}{\sqrt{x^2+a^2}}=\ln (x+\sqrt{x^2+a^2})+C$
$20、\int\frac{dx}{\sqrt{x^2-a^2}}=\ln\left|x+\sqrt{x^2-a^2}\right.|+C$

**常见“积不出”函数**
+ $\begin{aligned}&\int\mathrm{e}^{x^2}\mathrm{d}x\\&\int\frac{\sin x}x\mathrm{d}x\\&\int\frac{\cos x}x\mathrm{d}x\end{aligned}$


## 1.3 三类常见可积函数积分 
**1. 有理函数积分**
+ 积分：$\int R(x)\operatorname{d}x$
+ 有理函数：$R(x)$
+ （1）一般方法（部分分式法）；
+ （2）特殊方法（加项减项拆或凑微分绛幂）

**2. 三角有理式积分**
+ 积分：$\int R(\sin x,\cos x)\mathrm{d}x$
+ 解释：表示 $sinx$ 和 $conx$ 经过有理运算得到；
+ 一般方法：万能代换
	+ 令 $\tan\frac x2=t$
	+ $\int R(\sin x,\cos x)\operatorname{d}x=\int R(\frac{2t}{1+t^2},\frac{1-t^2}{1+t^2})\frac2{1+t^2}dt$
+ 特殊方法（三角变形、换元、分部）
	+ 1. $\text{若 }R(-\sin x,\cos x)=-R(\sin x,\cos x)$，则令 $u=\cos x$
	+ 2. $\text{若 }R(\sin x,-\cos x)=-R(\sin x,\cos x)$，则令 $u=\sin x$
	+ 3. $\text{若 }R(-\sin x,-\cos x)=R(\sin x,\cos x)$，则令 $u=\tan x$
+ 举例：
	+ 特殊方法：$\int\frac{\operatorname{d}x}{1+\sin x}=\int\frac{1-\sin x}{\cos^2x}\mathrm{d}x=\tan x-\frac1{\cos x}+C.$
	+ 一般方法：设 $\tan\frac x2=t$，则 $\begin{aligned}\text{原式}& =\int\frac 1{1+\frac{2 t}{1+t^2}}\cdot{\frac 2{1+t^2}dt}  \\&=\int\frac{2 dt}{\left (1+t\right)^2}=-\frac 2{1+t}+C\end{aligned}$

**3. 简单无理式积分**
+ 积分：$\int R(x,\sqrt[n]{\frac{ax+b}{cx+d}})\operatorname{d}x$
+ 一般方法： $\text{令 }\sqrt[n]{\frac{ax+b}{cx+d}}=t$
+ 举例：$\int\frac1x\sqrt{\frac{x+1}x}dx$
	+ $\text{令}\sqrt{\frac{x+1}x}=t\text{,则}\quad x=\frac1{t^2-1},dx=-\frac{2t}{\left(t^2-1\right)^2}dt,\int\frac1x\sqrt{\frac{x+1}x}dx=\int(t^2-1)t\frac{-2t}{(t^2-1)^2}dt=-2\int\left(1+\frac1{t^2-1}\right)dt$