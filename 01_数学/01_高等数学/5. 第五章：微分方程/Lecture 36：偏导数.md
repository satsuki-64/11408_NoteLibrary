## 1.1 什么是偏导数
### 1.1.1 基本概念
##### **定义**： #偏导数
> <font color="#ccc1d9">描述：</font>如果是对 $z=f(x,y)$ 函数，会有两个偏导数的定义：
> 1. 对 X 的偏导数：对 X 偏导时，Y 固定在 $y_0$ 处（对 x 没有任何影响），$x在x。处有\Delta x$ 的增量，此时只有 x 一个变量，此时称： 
>     $\lim_{\Delta x\to0}\frac{f\left(x_{0}+\Delta x,y_{0}\right)-f\left(x_{0},y_{0}\right)}{\Delta x}$ 为对 X 的偏导数；
>     记作：$\left.\frac{\partial z}{\partial x}\right|_{(x_{0},y_{0})},\left.\frac{\partial f}{\partial x}\right|_{(x_{0},y_{0})},z_{_z}(x_{0},y_{0})或$ $f_{x}(x_{0},y_{0})$
> 2. 对 Y 的偏导数：和 X 同理，
>     $lim_{\Delta y\to0}\frac{f(x_{0},y_{0}+\Delta y)-f(x_{0},y_{0})}{\Delta y}$；
>     记为：$\left.\text{}\frac{\partial z}{\partial y}\right|_{(x_{0},y_{0})},\left.\frac{\partial f}{\partial y}\right|_{(x_{0},y_{0})},z_{y}(x_{0},y_{0})\text{或}f_{y}(x_{0},y_{0}).$

**解释**

**方法**：如何求对 x 或者 y 的偏导
+ 当 $z=f(x,y)$ 时，把 y 或者 x 视为常数，直接对 x 或者 y 求导；
+ 例：$z=x^{2}+3xy+y^{2}在(1.2)处$ 的偏导数；
	+ 第一步：求出偏导后的函数
		+ 对 x 求偏导：$\frac{\partial z}{\partial x}=2x+3y$
		+ 对 y 求偏导：$$\frac{\partial z}{\partial y}=3x+2y$$
	+ 第二步：将 $(1.2)$ 点带入对 x 求偏导或者对 y 求偏导后的函数： 2 x+3 y 或者 3 x+2 y，即可得到结果

**二元函数偏导**
+ 一元函数中
	+ 可导 -> 连续
	+ 可导是一个很强的条件
+ 二元函数中
	+ 二元函数对 x 的偏导存在的前提 <- 在 y= $y_0$ 这一条直线上，它是连续的；
	+ 对二元函数来说，偏导存在，在 $(x_0,y_0)$ 未必连续；
 
