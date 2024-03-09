---
title: Lecture 52：对坐标的曲面积分
tags:
  - 数学
  - 曲面积分
categories: 
date: 2024-02-12
---
---
## 1.1 有向曲面及曲面元素的投影
### 1.1.1 基本曲面分类
**双侧曲面**
+ 有两侧

**只有一侧**
+ 莫比乌斯带

**指定了侧的曲面，称之为有向曲面，其方向用法向量指向表示**
![[Pasted image 20240212153621.png]]
+ $\text{设 }\Sigma\text{为有向曲面},\text{其面元 }\Delta S\text{ 在 }xOy\text{ 面上的投影记为}\left(\Delta S\right)_{xy}$

### 1.1.2 有向曲面基本概念
##### **定义**： #第二类曲面积分
> <font color="#ccc1d9">描述：</font> $\text{设}\Sigma\text{为光滑的有向曲面},\text{在}\Sigma\text{ 上定义了一个}\vec{\text{向量场 }A}=(P(x,y,z),Q(x,y,z),R(x,y,z)),若对\sum的任意分割和在局部面元上任意取点，$ 下列极限都存在：$\iint_{\Sigma}P\operatorname{d}\gamma\operatorname{d}z+O\operatorname{d}z\operatorname{d}x+R\operatorname{d}x\operatorname{d}\nu = \iint_{\Sigma}\vec{A}\cdot\overrightarrow{n}{\mathrm{d}}S=\iint_{\Sigma}\vec{A}\cdot{\mathrm{d}}\vec{S}$

**解释**
+ [图解数学分析 (mathpretty.com)](https://mathpretty.com/category/mathshow/shuxuefenxi/)
$$
\begin{aligned}&\iint_{\Sigma}P\operatorname{d}y\operatorname{d}z\text{称为}P\text{ 在有向曲面}\Sigma\text{上对 }{\text{对 }y,z\text{ 的曲面积分}} ; \\ & \iint _ { \Sigma }Q\operatorname{d}z\operatorname{d}x\text{ 称为}Q\text{ 在有向曲面}\Sigma\text{上对 }z,x\text{ 的曲面积分};\\&\iint_{\Gamma}R\operatorname{d}x\operatorname{d}\text{y 称为}R\text{ 在有向曲面}\Sigma\text{上对 }x,y\text{ 的曲面积分}.\end{aligned}
$$

### 1.1.3 对坐标的曲面积分的计算
##### **定理**： #第二类曲面积分的计算
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font> $\text{设光滑曲面 }\Sigma:z=z(x,y),(x,y){\in}D_{xy}\text{ 取上侧}R(x,y,z)\text{是 }\Sigma\text{ 上的连续函数, 则}$：
> $\iint_{\Sigma}R(x,y,z)\operatorname{d}x\operatorname{d}y=\iint_{D_{xy}}R(x,y,z(x,y))\operatorname{d}x\operatorname{d}y$

**解释**
