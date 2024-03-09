---
title: Lecture 51：对面积的曲面积分
tags:
  - 数学
  - 曲面积分
categories: 
date: 2024-02-12
---
---
## 1.1 对面积的曲面积分基本概念
### 1.1.1 基本概念
**引例**：已知曲面构件具有连续面密度ρ(x, y, z)，求其质量 M；
+ 图示
	+ ![[Pasted image 20240212143059.png]]
+ 用每一个小面积上的密度乘以其面积，然后全部求和，得到完整的质量：$M=\lim_{\lambda\to0}\sum_{k=1}^n\rho(\xi_k,\eta_k,\zeta_k){\Delta S_k}$

##### **定义**： #第一类曲面积分
> <font color="#ccc1d9">描述：</font> $\text{设}\sum\text{为光滑曲面},f(x,y,z)\text{ 是定义在}\sum\text{上的一}\text{个有界函数,若对}\Sigma\text{ 做任意分割和局部区域任意取点},$ 可以得到
> 乘积和式极限：$\lim_{\lambda\to0}\sum_{k=1}^nf\left(\xi_k,\eta_k,\zeta_k\right)\Delta S_k$
> 都存在，则称此极限为函数 $f(x,y,z)$ 在曲面 $\Sigma$ 上对面积的曲面积分；
> 记作：$\iint_{\Sigma}f(x,\gamma,z)\operatorname{d}S$

**解释**
+ $ds$ 相当于小曲面的面积；
+ $f(x,y,z)$ 相当于曲面的密度；
+ $f(x,\gamma,z)\operatorname{d}S$ 表示求一小块的质量；
+ $\iint_{\Sigma}f(x,\gamma,z)\operatorname{d}S$ 表示对整个面上，每个小块求和极限；
+ $\Sigma$ 称之为积分曲面；

**性质**
+ 积分的存在性：$若 f(x,y,z)\text{在光滑曲面}\sum\text{ 上连续}$，则对面积的曲面积分存在；
+ 对积分域的可加性：若 $\sum$ 是分片光滑的，则有：$\iint_{\Sigma}f(x,y,z)\operatorname{d}S=\iint_{\Sigma_{1}}f(x,y,z)\operatorname{d}S+\iint_{\Sigma_{2}}f(x,y,z)\operatorname{d}S$
+ 线性性质：$\begin{aligned}\iint_{\Sigma}[k_1f(x,y,z)\pm k_2g(x,y,z)]&\operatorname{d}S=k_1\iint_{\Sigma}f(x,y,z)\operatorname{d}S\pm k_2\iint_{\Sigma}g(x,y,z)\operatorname{d}S\end{aligned}$


### 1.1.2 对面积的曲面积分的计算
##### **定理**： #第一类曲面积分的计算
> <font color="#8db3e2"><font color="#c6d9f0">描述：</font></font>有光滑曲面，其 $\Sigma:z=z(x,y),(x,y)\in D_{xy}，f(x,y,z)\text{ 在 }\sum\text{上连续}$。则曲面积分 $\iint_{\Sigma}f(x,y,z)\text{dS 存在},\text{且有}$：
> $\iint_{\Sigma}f(x,\nu,{z}){\mathrm{d}S}=\iint_{D_{xy}}f(x,y,z(x,y))\sqrt{1+{z_x}^2(x,y)+{z_y}^2(x,y)}\mathrm{d}x\mathrm{d}y$

**解释**
+ 本质：把**难求的曲面面积，投影成一个对 x、y 上的平面二重积分**来完成计算；
+ 把曲面 $\sum$ 投影到 $D_{xy}$ 上；
+ $\tilde{\text{若曲面由方程 }x}=x(y,z){\text{或 }\operatorname*{y}}=y(z,x)\text{ 给出,也可类似地把对面积的面积分化为相应}\text{的二重积分}$；

### 1.1.3 例题
**例题**：$\text{计算曲面积分}\iint_{\Sigma}(x^2+y^2+z^2)dS,\text{ 其中}\sum\text{是球面}x^2+y^2+z^2=1$
+ 分析
	+ 因为被积区域是一个圆，所以被积函数恒等于 1；
	+ 即
+ 解析
+ 题型：#