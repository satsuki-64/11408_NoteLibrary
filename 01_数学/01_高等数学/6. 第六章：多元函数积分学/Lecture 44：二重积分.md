---
title: Lecture 44：二重积分
tags: 
categories: 
date: 2024-02-08
---
---
## 1.1 二重积分基本概念
### 1.1.1 概念引入
**曲面顶柱体的体积**
+ 在一个曲面顶柱体当中，当 $\lim_{\lambda\to0}\sum_{i=1}^{n}\Delta\sigma_{i}f\left(\xi_{i},y\right)$ 时，其为曲面柱体的二重积分；
+ 其中：$\sigma_{i}$ 为底面积，$f\left(\xi_{i},y\right)$ 为高，$lambda$ 为每一个小区间上，几何图形的直径；

##### **定义**： #二重积分
> <font color="#ccc1d9">描述：</font>如果 $f(x,y)$ 是区域 D 上的有界函数，将区域 D 任意的分成 n 个区域：$\sigma_{1}$ 、$\sigma_{2}$.... $\sigma_{n}$，每个 $\sigma_{n}$ 上任取一点 $(\xi_{i},\eta_{i})$，做 $f(\xi,\eta_{i})\Delta\sigma_{i}$ ，当 $\lambda\to0$ 时：
> 称下式为二重积分： $$\lim_{\lambda\to0}\sum_{i=1}^{n}\Delta\sigma_{i}f\left(\xi_{i},y\right)=\int\int_{D}f(x,y)d\sigma $$

**解释**
+ 区间
	+ 一重积分的积分区域是一个区间，比如 $(3,6)$；
	+ 二重积分的积分区域是一个图，因此通常用一个区域 D 来表示；
	+ 注意：积分区域不等于定义域，积分区域是要求积分的区域；
+ 面积元素
	+ $d\sigma$ 为面积元素；

### 1.1.2 直角坐标系的面积元素
**区分积分区域的面积元素的方式**
+ 横着分和竖着分；
+ $\sigma_{i}=\Delta x_{i}\cdot\Delta y_{j}$ 
+ 公式：$\int\int_{D}f(x,y)dxdy$

## 1.2 二重积分的性质
### 1.2.1 性质介绍
**基本性质**
1. 被积函数的常数因子可以提到二重积分的外面，即
$$
\int\int_Dkf(x,y)d\sigma=k\int\int_Df(x,y)d\sigma 
$$

2. 函数和 (或差)的二重积分等于各个函数二重积分的和 (或差), 即
$$
\int\int_D[f(x,y)\pm g(x,y)]d\sigma=\int\int_Df(x,y)d\sigma+\int\int_Dg(x,y)d\sigma 
$$

3. 如果在 D 上，f (x, y)=A, A 是常数，则σ为 D 的面积，则
$$
\sigma=\int\int_DA\cdot d\sigma=A\int\int_Dd\sigma 
$$

4. 如果闭区域 D 被有线条曲线分为有限个部分闭区域，则在 D 上的二重积分等于在各部分区域上
 的二重积分的和，例如 D 被分为两个闭区域 D 1 和 D2，则
$$
\int\int_Df(x,y)d\sigma=\int\int_{D_1}f(x,y)d\sigma+\int\int_{D_2}f(x,y)d\sigma 
$$
+ 几何含义：原本一个几何柱体可以一次二重积分求出来，现在将其一个柱体切分成两个柱体，然后分别对其求二重积分，求和即为完整的体积；

5. 如果在 D 上，$f(x,y)\leq g(x,y)$ ，则有不等式
$$
\int\int_Df(x,y)d\sigma\leq\int\int_Dg(x,y)d\sigma 
$$
+ 如果函数值恒小，则其二重积分的值也更小；

6. 如果 $f(x,y)$ 在区域 D 上的数值恒等于 1，则其二重积分就是
$$
\int_{D}\left(1)  d\sigma=\sigma\times1\right.
$$
