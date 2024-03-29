## 19.1 二叉排序树
### 19.1.1 查找
**如何查找**
- <mark style="background: #FFB86CA6;">左子树结点值<根结点值<右子树结点值</mark>
- 若树非空，目标值与根结点的值比较：
1. 若相等，则查找成功
2. 若小于根结点，则在左子树上查找，否则在右子树上查找。
3. 查找成功，返回结点指针。查找失败返回 NULL

**代码实现**

```c
//二叉排序树结点
typedef struct BSTNode{
	int key;
	struct BSTNode *lchild,*rchild;
}BSTNode,*BSTree;
```

```c
//在二叉排序树中查找值为key的结点
BSTNode *BST_Search(BSTree T,int key){
	while(T!=NULL&&key!=T->data){ //若树空或等于根结点值，则结束循环
		if(key<T->data)	
			T=T->lchild; //小于，则在左子树上查找
		else
			T=T->rchild; //大于，则在右子树上查找
		
	}
	return T;
}
//最坏空间复杂度O(1)
```

```c
//在二叉排序树中查找值为key的结点(递归实现)
BSTNode *BSTSearch(BSTree T,int key){
	if(T==NULL)
		return NULL;   //查找失败
	if(key==T->key)
		return T;      //查找成功
	else if(key<T->key)
		return BSTSearch(t->lchild,key); //在左子树中找
	else
		return BSTSearch(t->rchild,key); //在右子树中找
}
```

### 19.1.2 插入
**如何插入**
- 若原二叉排序树为空，则直接插入结点。
- 否则，若关键字 k 小于根结点值，则插入到左子树，若关键字 k 大于根结点值，则插入到右子树。
- **注意:** <mark style="background: #FFF3A3A6;">新插入的结点一定是叶子结点</mark>
- **最坏空间复杂度 O (h)**

**代码实现**
```c
//在二叉排序树插入关键字为k的新结点(递归实现)
int BST_Insert(BiTree &T,KeyType k){
	if(T==NULL){     //原树为空，新插入的结点为根结点
		T=(BiTree)malloc(sizeof(BSTNode));
		T->data=k;
		T->lchild=T->rchild=NULL;
		return 1;    //返回1,插入成功
	}
	else if(k==T->data)
		return 0;
	else if(k<T->key)//插入到T的左子树
		return BST_Insert(T->lchild,k);
	else             //插入到T的右子树
		return BST_Insert(T->rchild,k);
}
```

### 19.1.3 构造与删除
**二叉排序树的构造**
```c
//按照str[]中的关键字序列建立二叉排序树
void Creat_BST(BiTree &T,KeyType str[],int n){
	T=NULL;     //初始时T为空树
	int i=0;
	while(i<n){ //依次将每个关键字插入到二叉排序树中
		BST_Insert(T,str[i]);
		i++;
	}
}
```

**删除**
+ 先搜索找到目标节点：
1. 若被删除结点 z 是叶结点，则直接删除，不会破坏二叉排序树的性质。
2. 若结点 z 只有一棵左子树或右子树，则让 z 的子树称为 z 父结点的子树，替代 z 的位置。
3. 若结点 z 有左，右两棵子树，则令 z 的直接后继 (或直接前驱)替代 z，然后从二叉排序书中删除这个直接后继 (或直接前驱)，这样就转换成了第一或第二种情况。

### 19.1.4 查找效率分析
**查找长度**
+ 在查找运算中，<mark style="background: #FFF3A3A6;">需要对比关键字的次数</mark>称为查找长度，反映了查找操作时间复杂度
+ **最好情况:**
	- n 个结点的[[5 - 2 - 2 二叉树的性质#^mk-202301121753|二叉树最小高度]]为 $\lfloor \log_{2}n\rfloor+1$
	- 平均查找长度 $O(\log_{2}n)$
- **最坏情况:**
	- 每个结点只有一个分支，树高 $h=$ 结点数 $n$
	- 平均查找长度 $O(n)$
- 总结：
	- $每层*每层的结点数/总结点数$

**查找失败**
+ 公式：
	+ $ASL=\sum\limits\frac{\mbox{本层高度}*\mbox{本层叶子数}}{\mbox{补上的叶子数}}$
+ 图示：
	+ ![[Pasted image 20240329142723.png]]


## 19.2 平衡二叉树
### 19.2.1 定义
**平衡二叉树 (Balanced Binary Tree):**
- 简称平衡树 (AVL 树)：树上任一结点的左子树和右子树的<font color=#FF0212>高度之差不超过 1</font>
- <mark style="background: #FFF3A3A6;">结点的平衡因子</mark>=左子树高-右子树高

**代码实现**
```c
//平衡二叉树结点
typedef struct AVLNode{
	int key;       //数据域
	int balance;   //平衡因子
	struct AVLNode *lchild,*rchild;
}AVLNode,*AVLTree;
```

### 19.2.2 调整最小不平衡子树
**LL：** 在 A 的左孩子的左子树中插入导致不平衡
+ 操作
	- LL 平衡旋转 (<font color=#FF0212>右单旋转</font>)。
	- 由于在结点 A 的左孩子 (L)的左子树 (L)上插入了新结点，A 的平衡因子由 1 增至 2，导致以 A 为根的子树失去平衡，需要一次向右的旋转操作。
		- 将 A 的左孩子<mark style="background: #FFF3A3A6;">B 向右上旋转</mark>替代 A 成为根结点，将<mark style="background: #FFF3A3A6;">A 结点向右下旋</mark>转成为 B 的右子树的根结点，而 B 的原右子树则作为 A 结点的左子树。
+ 图示：
	+ ![[Pasted image 20240329142828.png]]



**RR：** 在 A 的右孩子的右子树中插入导致不平衡
+ **操作:**
	- RR 平衡旋转 (<font color=#FF0212>左单旋转</font>)
	- 由于在结点 A 的右孩子 (R)的右子树 (R)上插入了新结点，A 的平衡因子由-1 减至-2，导致以 A 为根的子树失去平衡，需要一次向左的旋转操作。 
		- 将 A 的右孩子<mark style="background: #FFF3A3A6;">B 向左旋转</mark>代替 A 成为根结点，将<mark style="background: #FFF3A3A6;">A 结点向左下旋转</mark>成为 B 的左子树的根结点，而 B 的原左子树则作为 A 结点的右子树

**LR：** 在 A 的左孩子的右子树中插入导致不平衡 
**操作:**
- LR 平衡旋转 (<font color=#FF0212>先左后右</font>双旋转)
- 由于在 A 的左孩子 (L)的右子树 (R)上插入新结点，A 的平衡因子由 1 增至 2，导致以 A 为根的子树失去平衡，需要进行两次旋转操作，先左旋转后右旋转。
	- 先将 A 结点的左孩子 B 的右子树的根结点<mark style="background: #FFF3A3A6;">C 向左上旋转提升到 B 结点的位置</mark>，然后再把该<mark style="background: #FFF3A3A6;">C 结点向右上旋转提升到 A 结点的位置</mark>。

**RL：** 在 A 的右孩子的左子树中插入导致不平衡 
**操作:**
	- RL 平衡旋转 (<font color=#FF0212>先右后左</font>双旋转)

### 19.2.3 调整二叉树总结
1. **LL：**
		1. 在 A 的左孩子的左子树中插入导致不平衡 
		2. **调整:** A 的<mark style="background: #ADCCFFA6;">左孩子</mark>结点<mark style="background: #FFF3A3A6;">右上旋</mark>
2. **RR：**
	1. 在 A 的右孩子的右子树中插入导致不平衡 
	2. **调整:** A 的<mark style="background: #ADCCFFA6;">右孩子</mark>结点<mark style="background: #FFF3A3A6;">左上旋</mark>
3. **LR：**
	1. 在 A 的左孩子的右子树中插入导致不平衡 
	2. **调整:** A 的<mark style="background: #ADCCFFA6;">左孩子的右孩子</mark>先<mark style="background: #FFF3A3A6;">左上旋</mark>再<mark style="background: #FFF3A3A6;">右上旋</mark>
4. **RL：**
	1. 在 A 的右孩子的左子树中插入导致不平衡 
	2. **调整:** A 的<mark style="background: #ADCCFFA6;">右孩子的左孩子</mark>先<mark style="background: #FFF3A3A6;">右上旋</mark>后<mark style="background: #FFF3A3A6;">左上旋</mark>
注意：插入操作导致"最小不平衡子树"高度+1，经过调整后高度恢复

### 19.2.4 查找效率分析 
**效率分析**
- 概念：
	- 若树高为 h，则最坏情况下，查找一个关键字最多需要对比 h 次，即查找操作的时间复杂度不可能超过 $O(h)$
- 平衡二叉树：
	- 树上任一结点的左子树和右子树的<font color=#FF0212>高度之差不超过 1</font>
	- 假设以 $n_{h}$ 表示深度为 $h$ 的平衡树中含有的<mark style="background: #FFB86CA6;">最少结点数</mark>
	- 则有 $n_{0}=0,n_{1}=1,n_{2}=2$
	- 并且有: $n_{h}=n_{h-1}+n_{h-2}+1$
- 可以证明：
	- 含有 n 个结点的平衡二叉树的最大深度为 $O(\log_{2}n)$，平衡二叉树的<font color=#FF0212>平均查找长度</font>为 $O(\log_{2}n)$

## 19.3 哈夫曼树
### 19.3.1 带权路径长度
**基本概念**
结点的 `权`：有某种现实含义的数值 
	- 例如：表示结点的重要性等
- **结点的带权路径长度:**
	- 从树的根到该结点的路径长度 (经过的边数)与该结点上权值的乘积
- **树的带权路径长度:**
	- 树中所有叶结点的带权路径长度之和 (WPL，Weighted Path Length)
+ 树的带权路径长度：
	+ $$WPL=\sum\limits^{n}_{i=1}w_{i}l_{i}$$

### 19.3.2 哈夫曼树的定义与构造
**哈夫曼树的定义**
- 在含有 n 个带权**叶结点**的二叉树中，其中<mark style="background: #FFF3A3A6;">带权路径长度 (WPL)最小的二叉树</mark>称为<font color=#FF0212>哈夫曼树</font>，也称<font color=#FF0212>最优二叉树</font>

**哈夫曼树的构造**
+ 图示：
	+ ![[Pasted image 20240329143321.png]]
**给定 n 个**权值分别为 $W_{1},W_{2},...,W_{n}$ 的结点，构造哈夫曼树的算法描述如下：
1. 将这 n 个结点分别作为 n 棵仅含一个结点的二叉树，构成森林 F。
2. 构造一个新结点，从 F 中**选取两棵根结点权值最小的树**作为新结点的左，右子树，并且将新结点的权值置为左，右子树上根结点的权值之和。
3. 从 F 中删除刚才选出的两棵树，同时将新得到的树加入 F 中。
4. 重复 (2)和 (3)，直至 F 中只剩下一颗树为止；
- **特点:**
	1. 每个初始结点最终都成为叶结点，且<mark style="background: #ADCCFFA6;">权值越小的结点到根结点的路径长度越大</mark>
	2. 哈夫曼树的结点总数为 $2n-1$
	3. 哈夫曼树中<mark style="background: #FFF3A3A6;">不存在度为 1 的结点</mark>
	4. 哈夫曼树并**不唯一**，但 WPL 必然相同且为最优


### 19.3.3 哈夫曼编码
- **可变长度编码**—— 允许对不同字符用不等长的二进制位表示
---
- **固定长度编码**——每个字符用相等的二进制表示
- 若没有一个编码是另一个编码的前缀，则称这样的编码为**前缀编码**
- 有哈夫曼树得到<mark style="background: #FFF3A3A6;">哈夫曼编码</mark>：
	- 字符集中的每个字符作为一个叶子结点，各个字符出现的频度作为结点的权值，根据之前介绍的方法构造哈夫曼树

## 19.4 并查集
### 19.4.1 树
**查找操作:**
- 如何 `查` 到一个元素到底属于哪一个集合？
	- 从制定元素出发，一路向北，<font color=#FF0212>找到根节点</font>
- 如何判断两个元素是否属于同一个集合？
	- 分别查找到两个元素的根，<font color=#FF0212>判断根节点是否相同</font>
**合并操作:**
- 让一棵树成为另一颗树的子树即可

### 19.4.2 存储结构
**并查集的存储结构**
+ 图示：
	+ ![[Pasted image 20240329143501.png]]

### 19.4.3 基本操作
**集合的基本操作:**
- **查:**
	- `Find`：确定一个指定元素所属集合
- **并:**
	- `Union`：将两个不想的集合合并为一个
- 注: 并查集 (Disjoint Set)是逻辑结构—— ——集合的一种具体实现。只能进行“并”和“查”两种基本操作

**时间复杂度**
+ **Find:** $O(n)$
- **Union：** $O(1)$

**代码实现**
```c
//并查集的初始化:
#define SIZE 13
int UFSets[SIZE];    //集合元素数组

//初始化并查集
void Initial(int S[]){
	for(int i=0;i<SIZE;i++)
		S[i]=-1;
}
```

```c
//查操作，找x所属集合(返回x所属根节点)
int Find(int S[],int x){
	while(S[x]>=0)    //循环寻找x的跟
		x=S[x];
	return x;
}

//并操作
void Union(int S[],int Rootl,int Root2){
	//要求Root1与Root2是不同的集合
	if(Root1==Root2) return;
	//将根Root2连接到另一根Root1下面
	S[Root2]=Root1;
}
```

### 19.4.4 优化
**Union 操作的优化:**
- **思路:**
	- 在每次 Union 操作构建树的时候，<font color=#FF0212>尽可能让树不长高</font>
- **操作:**
	1. 用根节点的绝对值表示树的结点总数
	2. Union 操作，让小树合并到大数
+ 树高：
	+ 该方法构造的树高不超过 $\lfloor \log_{2}n \rfloor+1$
+ 图示
	+ ![[Pasted image 20240329143623.png]]