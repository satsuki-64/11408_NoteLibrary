## 17.1 二叉树的递归遍历
**利用二叉树的递归特性遍历**
+ 等同于利用其左右节点来遍历；
+ 使用先中后三种顺序进行遍历；

### 17.1.1 二叉树的遍历 
**二叉树的递归特性:**
+ 1. 要么是空二叉树
+ 2. 要么就是由**根节点+左子树+右子树**组成的二叉树

**二叉树的遍历**
+ 二叉树的递归特性
	+ 1. 要么是空二叉树
	+ 2. 要么就是由**根节点+左子树+右子树**组成的二叉树
+ 三种遍历
	+ 先序遍历：根左右(NLR)
	+ 中序遍历：左根右(LNR)
	+ 后序遍历：左右根(LRN)
+ 图示：
	+ ![[Pasted image 20240327165156.png]]
	+ ![[Pasted image 20240327165204.png]]

### 17.1.2 先序遍历 
**先序遍历(ProOrder)** 
+ 操作过程:
	+ 1. 若二叉树为空，则什么也不做
	+ 2. 若二叉树非空
		+ 1. 访问根节点
		+ 2. 先序遍历左子树
		+ 3. 先序遍历右子树
+ 形象解释：
	+ 从根节点出发，画一条路；
	+ 1. 如果左边还有没走的路，优先往左边走，走到路的尽头 (空结点)就往回走；
	+ 2. 如果左边没路了，就往右边走；
	+ 3. 如果左、右都没路了，则往上面走；
	+ 总结：先序遍历 `->` 第一次路过时访问结点
 + 空间复杂度: $O(h)$
	+ 每一个结点都会被路过 3 次

**代码实现**
```c
//先序遍历
typedef struct BiTNode{
	ElemType data;
	struct BiTNode *lchild,*rchild;*
}BiTNode,*BiTree;

void PreOrder(BiTree T){
	if(T!=null){
		visit(T);           //访问根节点
		PreOrder(T->lchild);//递归遍历左子树
		PreOrder(T->rchild);//递归遍历右子树
	}
}
```
### 17.1.3 中序遍历
**中序遍历(ProOrder)** 
+ 操作过程：
+ 1. 若二叉树为空，则什么也不做
+ 2. 若二叉树非空
	+ 1. 先序遍历左子树
	+ 2. 访问根节点
	+ 3. 先序遍历右子树
+ 形象解释： 
	+ 从根节点出发，一条路如果左迈还有没走的路，优先往左边走
	+ 走到路的尽头 (空结点)就往回走
	+ 如果左边没路了，就往右边走
	+ 如果左、右都没路了，则往上面走
	+ 中序遍历：第二次路过时访问结点

**代码实现**
```c
//中序遍历
void InOrder(BiTree T){
	if(T!=NULL){
		InOrder(T->lchild);  //递归遍历左子树
		visit(T);            //访问根节点
		InOrder(T->rchild);  //递归遍历右子树
	}
}
```

### 17.1.4 后序遍历  
**后序遍历(ProOrder)** 的操作过程如下:
+ 1. 若二叉树为空，则什么也不做
+ 2. 若二叉树非空
	+ 1. 先序遍历左子树
	+ 2. 先序遍历右子树 
	+ 3. 访问根节点

**代码实现**
```c
//后序遍历
void PostOrder(BiTree T){
	if(T!=NULL){
		PostOrder(T->lchild);  //递归遍历左子树
		PostOrder(T->rchild);  //递归遍历右子树
		visit(T);            //访问根节点
	}
}
```

## 17.2 二叉树的层次遍历
### 17.2.1 基础概念
**算法思想**
+ 思想：
	+ 1. 初始化一个辅助**队列**
	+ 2. 根节点入队
	+ 3. 若队列非空，则对头结点出队，访问该结点，并将其左右孩子插入队尾(如果有的话)
	+ 4. 重复(3)直至队列为空
+ 图示：
	+ ![[Pasted image 20240327165537.png]]

### 17.2.2 代码实现
```c
//层序遍历
void LevelOrder(BiTree T){
	LinkQueue Q;
	InitQueue(Q);       //初始化辅助队列
	BiTree p;
	EnQueue(Q,T);       //将根节点入队
	while(!IsEmpty(Q)){ //队列不空则循环
		DeQueue(Q,p);   //对头结点出队
		visit(p);       //访问出队结点
		if(p->lchild!=NULL)
			EnQueue(Q,p->lchild);  //左孩子入队
		if(p->rchild!=NULL)
			EnQueue(Q,p->rchild);  //右孩子入队
	}
}
```

```c
//二叉树的结点(链式存储)
typedef struct BiTNode{
	char data;
	struct BiTNode *lchild,*rchild;
}BiTNode,*BiTree;

//链式队列结点
typedef struct LinkNode{
	BiTNode *data; //存指针而不是结点
	struct LinkNode *next;
}LinkNode;

typedef struct{
	LinkNode *front,*rear;  //队头队尾
}LinkQueue;
```

## 17.3 遍历序列构造二叉树
**引入**
+ 概念：
	+ 若只给出一颗二叉树的 **前/中/后** 序遍历序列中的一种，不能确定一颗二叉树；
+ 原因：
	+ **同一个遍历序列，可以对应成不同的二叉树**；
+ 方法：
	+ 给出先中后序列中的两种，可以唯一确定一颗二叉树；
	+ 用前后序确定根节点 (层序同理)，中序遍历确定左右子树；
+ 构造：
	+ 前序 + 中序；
	+ 后序 + 中序；
	+ 层序 + 中序；
 
**前序+中序**
+ 概念：
	+ 用前序序列结合中序序列，分别交叉判断成分；
	+ 前序序列 `->` 根节点 `->` 中序序列 `->` 左右节点； 
+ 图示：
	+ ![[Pasted image 20240327165646.png]]

**后序+中序**
+ 概念：
	+ 后序序列 `->` 根节点 `->` 中序序列 `->` 左右节点； 
+ 图示：
	+ ![[Pasted image 20240327165711.png]]

**层序+中序**
+ 图示：
	+ ![[Pasted image 20240327165730.png]]

**其他方式**： 前序、后序、层序序列两两组合 `->` **不能还原出二叉树**；

## 17.4 线索二叉树的概念
### 17.4.1 中序线索二叉树
**问题**
+ 树的中序遍历 `->` 必须总是从根节点开始遍历 `->` 如果只有普通节点、不知道根节点，此时往上找；
+ 并且传统的遍历，无法找到当前节点的前驱；
+ 概念：
	+ 从根节点出发，重新进行一次中序遍历；
	+ 指针 **q 记录当前访问**的结点； 
	+ 指针 **pre 记录上一个被访问**的结点
+ 判断：
	+ ①当 `q==p` 时，pre 为前驱；
	+ ②当 `pre==p` 时，q 为后继；

**中序线索遍历序列**
+ 中序遍历序列：
	+ 按照中序遍历得到的序列顺序，依次建立每个节点的前驱以及后驱序列；
	+ D `<->` G `<->` B `<->` E `<->` A `<->` F `<->` C
+ 存储图示：
	+ ![[Pasted image 20240327225633.png]]

**代码实现**
+ 线索二叉树结点
```c
//线索二叉树结点
typedef struct ThreadNode{
	ElemType data;
	struct ThreadNode *lchild,*rchild;
	int ltag,rtag;   //左，右线索标志
}ThreadNode,*ThreadTree;
```
+ 中序遍历对二叉树线索化的递归算法
```c
//中序遍历对二叉树线索化的递归算法:
void InTread(ThreadTree &p,ThreadTree &pre){
	if(p!=NULL){
		InTread(p->lchild,pre); //递归，先所化左子树
		if(p->lchild=NULL){     //左子树为空，建立前驱线索
			p->lchild = pre;
			p->ltag=1;
		}
		if(pre!=NULL&&pre->rchild==NULL){
			pre->child=p;       //建立前驱结点的后继线索
			pre->rtag=1;
		}
		pre=p;                  //标记当前结点成为刚刚访问过的结点
		InTread(p->rchild,pre); //递归，线索化右子树
	}//if(p!=NULL)
}
```
+ 中序遍历建立中序线索二叉树主过程算法
```c
//中序遍历建立中序线索二叉树主过程算法:
void CreateInTread(ThreadTree T){
	ThreadTree pre = NULL;
	if(T!=NULL){          //非空二叉树，线索化
		InThread(T,pre);  //线索化二叉树
		pre->rchild=NULL; //处理遍历的最后一个结点 
		pre->rtag=1;
	}
}
```

### 17.4.2 先序与后序线索二叉树

## 17.5 二叉树的线索化
### 17.5.1 中序遍历 
**老方法：通过中序遍历找到节点的前驱节点**
+ 概念： 
	+ 定义一个 pre 指针和 q 指针，q 指针递归获得树当中的节点，往下递归一层后，先进行一次判断，判断当前 p 和 q 节点是否一致；
	+ 如果不一致，则将当前 pre 节点指向当前 q 节点； 
	+ 如果一致，则表示找到目标节点。此时不要再将 pre 节点指向当前 q 节点，因为此时 pre 节点已经是 p 节点的前驱节点，如图所示；
+ 核心：
	+ 多用一个遍历，存储上一步结果；
+ 图示：
	+ ![[Pasted image 20240327170012.png]]

**代码实现**
```c
//中序遍历
void InOrder(BiTree T){
	if(T!=NULL){
		InOrder(T->lchild);  //递归遍历左子树
		visit(T);            //访问根结点
		InOrder(T->rchild);  //递归遍历右子树
	}
}

//访问结点q
void visit(BiTNode *q){
	if(q==p)        //当前访问结点刚好是结点p
		final = pre;//找到p的前驱
	else
		pre = q;    //pre指向当前访问的结点
}

//辅助全局变量，用于查找结点p的前驱
BiTNode *p;            //p指向目标结点
BiTNode *pre = NULL;   //指向当前访问结点的前驱
BiTNode *final = NULL; //用于记录最终结果
```

### 17.5.2 中序线索化 
**基本概念**
+ 概念： 
	+ 1. 中序/先序/后序遍历算法的改造，当访问一个结点时，连接该结点与前驱结点的线索信息；
	+ 2. 用一个指针 pre 记录当前访问结点的前驱结点；
+ 注意：
	+ 1. 最后一个结点的 `rchild`、`rtag` 的处理
	+ 2. 先序线索化中，注意处理爱滴魔力转圈圈问题，当 `ltag==` 0 时，才能对左子树先序线索化；
+ 图示：
	+ 节点：中序线索化遍历结果
		+  ![[Pasted image 20240327233453.png]]

**代码实现**
```c
//线索二叉树结点
typedef struct ThreadNode{
	ElemType data;
	struct ThreadNode *lchild,*rchild;
	int ltag,rtag;   //左，右线索标志
}ThreadNode,*ThreadTree;
```

```c
//访问根节点
void visit(ThreadNode *q){
	if(q->lchild == NULL){ //左子树为空，建立前驱线索
		q->lchild = pre;
		q->ltag = 1;
	}
	if(pre != NULL&&pre->rchild==NULL){
		pre->rchild=q;  //建立前驱结点的后继线索
		pre->rtag=1;
	}
	pre=q;
}

//全局变量pre 指向当前访问结点的前驱
ThreadNode *pre = NULL;
```

### 17.5.3 先序遍历线索化
**代码实现**
```c
//先序遍历二叉树，一边遍历一遍线索化
void PreThread(ThreadTree T){
	if(T!=NULL){
		visit(T);   //先处理根结点
		PreThread(T->lchild);
		PreThread(t->rchild);
	}
}

//先序遍历二叉树，一边遍历一遍线索化
vodi PreThread(ThreadTree T){
	if(T!=NULL){
		visit(T);      //先处理根节点
		if(T->ltag==0) //lchild不是前驱线索
			//对左指针指向的树线索化
			PreThread(T->lchild);
		PreThread(T->rchild);
	}
}
```
### 17.5.4 后序遍历线索化
**代码实现**
```c
//后序线索化
void PostThread(ThreadTree p,ThreadTree &pre){
	if(p!=NULL){
		PostThread(p->lchild,pre); //递归，线索化左子树
		PostThread(P->rchild,pre); //递归，线索化右子树
		if(p->lchild == NULL){     //左子树为空，建立前驱线索
			pre->lchild=p;         //建立前驱结点的后继线索
			pre->rtag=1;
		}
		pre=p;    //标记当前结点成为刚刚访问过的结点
	}//if(p!=NULL)
}
```

```c
//后序线索化二叉树T
void CreatePostThread(ThreadTree T){
	ThreadTree pre = NULL;
	if(T!=NULL){           //非空二叉树，线索化
		PostThread(T.pre); //线索化二叉树
		if(pre->rchild==NULL) //处理遍历的最后一个结点
			pre->rtag=1;
	}
}
```

## 17.6 线索二叉树找前驱后继
### 17.6.1 中序线索二叉树 
**中序遍历找中序后继**
+ 概念： 
	+ 如果 `p->rtag==1`，则当前后继节点即为 `next = p->rchild`；
	+ 如果 `p->rtag==0`，则当前节点有右节点，并且在右子树的最左下节点为其后继节点；
+ 代码：
	+ `ThreadNode *Nextnode(ThreadNode *p) {//右子树中最左下结点 if (p->rtag==0) return Firstnode (p->rchild); else return p->rchild;}`
+ 图示：
	+ ![[Pasted image 20240327170234.png]]

**代码实现**
```c
//找到以P为根的子树中，第一个被中序遍历的结点
ThreadNode *Firstnode(ThreadNode *p){
	//循环找到最左下结点(不一定是叶结点)
	while(p->ltag==0) 
		p=p->lchild;
	return p;
}
```

```c
//在中序线索二叉树中找到结点p的后继结点
ThreadNode *Nextnode(ThreadNode *p){
	//右子树中最左下角的结点
	if(p->rtag==0)
		return Firstnode(p->rchild);
	else
		return p->rchild; //rtag==1直接返回后继线索
}
```

**代码**：使用中序线索二叉树进行中序遍历 `->` 使用每个节点的后继节点，进行遍历 `->` 空间复杂度为 $O(1)$
```c
//对中序线索二叉树进行中序遍历(利用线索实现的非递归算法)
void Inorder(ThreadNode *T){
	for(ThreadNode *p=Firstnode(T);p!=NULL;p=Nextnode(p))
		visit(p);
}
//空间复杂度O(1):因为不需要递归调用函数
```

```c
//找到以P为根的子树中，最后一个被中序遍历的结点
ThreadNode *Lastnode(ThreadNode *p){
	//循环找到最右下结点(不一定是叶结点)
	while(p->rtag==0)
		p=p->rchild;
	return p;
}
```

**代码**：找前驱节点
```c
//在中序线索二叉树中找到结点p的前驱结点
ThreadNode *Prenode(ThreadNode *p){
	//左子树中最右下结点
	if(p->ltag==0)
		return Lastnode(p->child);
	else
		return p->lchild;  //ltag==1直接返回前驱线索
}
```

```c
//对中序线索二叉树进行逆向中序遍历
void RevInorder(ThreadNode *T){
	for(ThreadNode *p=Lastnode(T);p!=NULL;p=Prenode(p))
		visit(p);
}
```

### 17.6.2 先序线索二叉树 
**找先序后继**
+ ![[Pasted image 20240327170338.png]]

**先序线索二叉树找到先序前驱**
+ **注意:** 如果 p 是根节点，则 p 没有先序前驱
+ ![[Pasted image 20240327170351.png]]

### 17.6.3 后序线索二叉树 
**找后序前驱**
+ 图示：
	+ ![[Pasted image 20240327170426.png]]

**找后续后继(三叉链表)**
+ 图示：
	+ ![[Pasted image 20240327170443.png]]

**总结**
+ 对于先序以及后序：除非用三叉链表，或者用土办法从根开始遍历寻找，不然就无法**直接**（可以从头开始找）找前驱或者后继节点；
+ ![[Pasted image 20240328000807.png]]