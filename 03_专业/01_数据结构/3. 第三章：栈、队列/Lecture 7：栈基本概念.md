---
title: Lecture 7：栈基本概念
tags:
  - 数据结构
  - 栈
categories: 
date: 2024-03-12
---
---
## 7.1 栈的定义
##### **定义**： #栈
> <font color="#ccc1d9">描述：</font>只允许一段进入插入或删除操作的线性表；

**解释**
- 栈顶 (Top)
- 栈底 (Button)
- 空栈

**栈的基本操作**
- `InitStack(&S):` 初始化栈。构造一个空栈 S，分配内存空间
- `DestroyStack(&L):` 销毁栈。销毁并释放栈 S 所占用的内存空间
- `Push(&S,x):` 进栈，若栈 S 未满，则将 x 加入使之成为新**栈顶**
- `Pop(&S,&x):` 出栈，若栈 S 非空，则弹出**栈顶**元素，并用 x 返回
- `GetTop(S,&x):` 读栈顶元素。若栈 S 非空，则用 x 返回栈顶元素

**总结:**
- **创，消:** InitStack DestroyStack 
- **增，删:** Push Pop
- **查:** GetTop 
- **StackEmpty (S)**：判断一个栈 S 是否为空。若 S 为空，则返回 true，否则返回 false；

**补充：卡特兰数**
+  n 个不同元素进栈，出栈元素不同排列的个数为：$\frac{1}{n+1}C^{n}_{2n}$
+ 上述公式称为卡特兰 (Catalan)数，可采用数学归纳法证明；

**常考习题**
+ 出栈顺序是否合法；
## 7.2 栈的顺序存储实现
### 7.2.1 顺序栈定义
**定义**
+ 和顺序表的定义类似

**代码定义**
```c
//顺序栈的定义
#define MaxSize 10         //定义栈中元素的最大个数
typedef struct{
	ElemType data[MaxSize];//静态数组存放栈中元素
	int top;               //栈顶指针  
}SqStack;  //Sq:sequence —— 顺序
```

**初始化**
```c
//初始化操作
void InitStack(SqStack &S){
	S.top = -1;            //初始化栈顶指针
}

//下面是初始化声明
void testStack(){
	SqStack S;   //声明一个顺序栈(分配空间)
	InitStack(S);
	//...后续操作
	//函数运行结束后，系统自动回收空间(不需理会)
}
```

### 7.2.2 顺序栈基本操作
**判断栈空**
+ 最开始栈中无元素时，`s.top=-1`，表示当前无元素，所以栈顶在数组中的下表为-1（无）;
+ 如果 `s.top` 的初始值设置为 `s.top=0`，则表示初始时栈顶指针指向 `a[0]` 的位置，当压入一个数据时，栈顶指针指向 `a[1]` 的位置、栈满的条件为 `s.top==MaxSize`；
```c
//判断栈空
bool StackEmpty(SqStack S){
	if(S.top == -1)  //栈空
		return true;
	else             //不空
		return false;
}
```

**出入栈**
```c
//新元素进栈操作
bool Push(SqStack &S,ElemType x){
	if(S.top == MaxSize-1)  //栈满，报错
		return false;
	S.top = S.top + 1;      //指针先加1
	S.data[S.top] = x;      //新元素入栈
	return true;
}
```
+ 注意: 等价写法 S.data[++S.top]=x, 其中的++号不能写反；

```c
//出栈操作
bool Pop(SqStack &S,ElemType &x){
	if(S.top == -1)    //栈空，报错
		return false;
	x=S.data[S.top];   //栈顶元素先出栈
	S.top = S.top -1;  //指针再减1
	return true;
}
```
+ 注意: 此时数据还存留再内存中，知识逻辑上被删除了 (没有 free)；

**读取栈顶元素**
```c
//读栈顶元素
bool GetTop(SqStack S,ElemType &x){
	if(S.top == -1)    //栈空，报错
		return false;
	x=S.data[S.top];   //x记录栈顶元素
	return true;
}
```

### 7.2.3 共享栈
**共享栈**
+ 图示：
	+ ![[Pasted image 20240312163144.png]]
+ 代码：
```c
//共享栈的定义
#define MaxSize 10         
typedef struct{
	ElemType data[MaxSize];//静态数组存放栈中元素
	int top0;               //0号栈顶指针  
	int top1;               //1号栈顶指针  
}SqStack; 

//初始化栈
void InitStack(ShStack &S){
	S.top0 = -1;      //初始化栈顶指针
	S.top1 = MaxSize;
}
```
**栈满的条件：** `top0` + 1 == `top1`
+ 实现了两个栈，但是却共享了一个存储空间，提高资源利用率；

## 7.3 栈的链式存储实现
**概念**
+ 和单链表的定义几乎没有区别，名词变化；
+ 图示：
	+ ![[Pasted image 20240312163456.png]]

**定义**
```c
typedef struct Linknode{
	ElemType data;         //数据域
	struct Linknode *next; //指针域
}*LiStack;                 //栈类型定义
```

