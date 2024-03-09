---
title: Lecture 28：不定积分
tags:
  - 数学
  - 不定积分
categories: 
date: 2024-01-17
---
---
## 1.1 什么是不定积分
### 1.1.1 基本概念
##### **定义**： #不定积分
> <font color="#ccc1d9">描述：</font>一个函数 $f(x)$ 的不定积分（或者说是原函数）是一个导数等于 $f(x)$ 的函数 $F(x)$ ，即 F′(x) = f (x)，或写成 $[F (x)+c]^{\prime}=f (x)$
> 或者：$\int f(x)dx=F(x)+C$

**解释**
+ 比如在 $\int f_{(x)}dx=F_{(x)}+C$ 中：
	+ 设 $F(x)$ 是函数 $f(x)$ 的一个原函数；
	+ 把函数 $f(x)$ 的所有原函数 $F(x)+C$ 叫做函数 $f(x)$ 的不定积分，又叫做函数 $f(x)$ 的反导数；
+ 其中 $\int$ 叫做积分号，f(x) $叫做被积函数，dx 叫做积分变量，$ f ( x) $d$ x 叫做被积式，C 叫做积分常数；

**原函数存在定理**
+ 连续的函数，一定存在原函数

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
$13、\int\csc xdx=\ln\lvert\csc x-\cot x\rvert+C$
$14、\int\frac{dx}{1+x^2}=\begin{cases}\arctan x+C\\-\operatorname{arccot}x+C\end{cases}$
$15、\int\frac1{\sqrt{a^2-x^2}}dx=\arcsin\frac xa+C$
$16、\int\frac1{x^2-a^2}dx=\frac1{2a}\ln\left|\frac{x-a}{x+a}\right|+C$
$17、\int\frac{dx}{\sqrt{1-x^2}}=\begin{cases}\arcsin x+C\\-\arccos x+C&\end{cases}$
$18、 \int\frac 1{a^2+x^2}dx=\frac 1 a\arctan\frac xa+C$ 
$19、\int\frac{dx}{\sqrt{x^2+a^2}}=\ln (x+\sqrt{x^2+a^2})+C$
$20、\int\frac{dx}{\sqrt{x^2-a^2}}=\ln\left|x+\sqrt{x^2-a^2}\right.|+C$
