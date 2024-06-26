---
title: Lecture 7：虚拟内存管理
tags:
  - 操作系统
  - 内存管理
categories: 
date: 2024-04-05
---
---
## 7.1 虚拟内存的基本概念
### 7.1.1 传统存储管理
**传统存储管理方式**
+ 连续分配：
	+ 单一连续分配
	+ 固定分区分配
	+ 动态分区分配
+ 非连续分配：
	+ 基本分页存储管理
	+ 基本分段存储管理
	+ 基本段页式存储管理

**传统存储管理方式特征**
+ 一次性：
	+ 概念：
		+ 作业必须一次全部装入内存后才能开始运行。
	+ 问题：
		+ 作业很大时，不能全部装入内存，导致大作业无法运行
		+ 当大量作业要求运行时，由于内存无法容纳全部作业，因此只有少量作业能运行，**导致多道程序并发度下降**；
+ 驻留性： 
	+ 概念：
		+ 一旦作业被装入内存，就会一直驻留在内存中，直至作业运行结束。
	+ 问题：
		+ 事实上，在一个时间段内，只需要访问作业一小部分数据即可正常运行，这就导致了内存中会驻留大量的，暂时用不到的数据，**浪费了宝贵的内存资源**；
+ 解决 `->` 虚拟存储技术；

### 7.1.2 虚拟内存概念 
**虚拟内存
+ 定义
	+ 在操作系统的管理下，在用户看来似乎有一个比实际内存大得多的内存，这就是虚拟内存技术；
+ 实现
	+ 基于局部性原理，在程序装入时，可以将**程序中很快用到的部分装入内存**，**暂时用不到的部分留在外存**，然后继续执行程序；
	+ 在程序执行过程中，当所访问的信息不在内存时，由操作系统负责将所需信息从外存调入内存，然后继续执行程序；
	+ 若内存空间不够，由操作系统负责**将内存中暂时用不到的信息换出外存**；

**易混淆知识点**
+ 虚拟内存的最大容量是由计算机的地址结构 (CPU 寻址范围)确定的
+ 虚拟内存的实际容量 = min (内存和外存容量之和，CPU 寻址范围)

**虚拟内存的 3 个主要特征**
+ 多次性：
	+ 无需在作业运行时一次性全部装入内存，而是**允许被分成多次调入内存**；
+ 对换性：
	+ 在作业运行时无需一直常驻内存，而是允许在作业运行过程中，将作业换入、换出；
+ 虚拟性：
	+ 从逻辑上扩充了内存的容量，使**用户看到的内存容量，远大于实际容量**；

### 7.1.3 虚拟内存实现 
**虚拟内存技术实现
+ 概念：建立在离散分配的内存方式基础上：
+ 方式：
	+ 请求分页存储管理
	+ 请求分段存储管理
	+ 请求段页式存储管理
+ 技术：
	+ **请求调页** (或请求调段)：
		+ 在程序执行过程中，当所访问的信息不在内存时，由操作系统负责将所需信息从外存调入内存，然后继续执行程序；
	+ **页面置换** (或段置换)：
		+ 若内存空间不够，由操作系统负责将内存中暂时用不到的信息换出到外存；

## 7.2 请求分页管理方式
### 7.2.1 页表机制
**页表机制**
+ 作用： 
	+ 在请求分页管理中，为了实现“请求调页”，操作系统需要知道每个页面是否已经调入内存；
	+ 如果还没调入，那么也需要知道该页面在外存中存放的位置；
+ 状态位：
	+ 表示页面是否已经在内存中
+ 访问字段：
	+ 记录**最近被访问过几次**，或记录上次访问的时间，供置换算法换出页面时参考；
	+ 可以把访问次数最少的换出内存；
+ 修改位：
	+ 表示页面调入内存后**是否被修改过**，只有修改过的页面才需在置换时写回外存；
	+ 只有“写指令”才需要修改“修改位”；
	+ 一般来说只需修改快表中的数据，只有要将快表项删除时才需要写回内存中的慢表。这样可以减少访存次数；
+ 外存地址：
	+ 页面在**外存中存放的位置**；
+ 图示：
	+ ![[1712311396922.png]]


### 7.2.2 缺页中断机构
**缺页中断
+ 概念： 
	+ 在请求分页系统中，每当要访问的页面不在内存时（页表的状态位为 0），便产生一个**缺页中断**，然后由操作系统的**缺页中断处理程序处理中断**；
	+ 因为当前执行的指令想要访问的目标页面未调入内存而产生的，因此属于内中断；
+ 实现（无快表时）：
	+ 1. 访问页面时，发现页表中对应页号的状态为为 0，产生缺页中断；
	+ 2. 调用缺页中断处理程序；
	+ 3. 此时缺页的进程阻塞，放入阻塞队列，调页完成后再将其唤醒，放回就绪队列；
	+ 4.1：如果内存中**有**空闲块，则为进程分配一个空闲块，将所缺页面装入该块，并**修改页表中相应的页表项**；
	+ 4.2：如果内存中**没有**空闲块，则**由页面置换算法选择一个页面淘汰**，若该页面在内存期间被修改过，则要将其写回外存；
+ 注意： 
	+ 一条指令在执行期间，可能产生多次缺页中断；
	+ 页面置换时，未修改过的页面不用写回外存；
+ 中断：
	+ 属于 `内中断` `->` `故障` 这一类型的中断；

### 7.2.3 地址变换机构 
**地址变换机构
+ 找到页表项是需要检查页面是否在内存中
+ 若页面不再内存中，需要请求调页
+ 若内存空间不够，还需换出页面
+ 页面调入内存后，需要修改相应页表项

**过程图示**：加入快表之后
+ 概念：查快表 (未命中) `->` 査慢表 (发现未调入内存) `->` 调页 (调入的页面对应的表项会直接加入快表) `->` 查快表 (命中) `->` 访问目标内存单元；
![[Pasted image 20240405181218.png]]

**流程图**
![[Pasted image 20240405181427.png]]

## 7.3 页面置换算法
**页面置换算法**
+ 概念： 
	+ 若内存空间不够，由操作系统负责将内存中暂时用不到的信息换出到外存； 
	+ 用页面置换算法决定应该换出哪个页面；
+ 目标： 
	+ 页面的换入、换出需要磁盘 I/0，会有较大的开销；
	+ 好的页面置换算法应该追求更少的**缺页率**；

### 7.3.1 最佳置换算法
**最佳置换算法 (OPT, Optimal)
+ 思想：
	+ 每次选择**淘汰的页面将是以后永不使用**，或者在最长时间内不再被访问的页面，这样可以保证最低的缺页率；
	+ 最佳置换算法可以保证最低的缺页率，但实际上，只有在**进程执行的过程中才能知道接下来会访问到的是哪个页面**；
	+ 操作系统无法提前预判页面访问序列。因此，最佳置换算法是无法实现的；
+ 问题：
	+ 不能预判，无法实现 
+ 实现：  
	+ 按最佳置换的规则往后寻找，最后一个出现的页号就是要淘汰的页面；

### 7.3.2 先进先出置换算法
**先进先出置换算法 (FIFO)
+ 思想
	+ 每次选择淘汰的页面是**最早进入内存的页面**；
+ 实现
	+ 把调入内存的页面根据调入的先后顺序排除一个队列，需要换出页面时选择对头页面即可。
	+ 队列的最大长度取决于系统为进程分配了多少内存块。
+ Belady异常:
	+ 当为进程分配的物理块数增大时，缺页次数不减反增的异常现象。
+ 注意
	+ 只有 FIFO 算法会产生 Belady 异常。
	+ 另外，FIFO 算法虽然实现简单，但是该算法与进程实际运行时的规律不适应，因为先进入的页面也有可能最经常被访问。因此，算法性能差； 

**分析举例**
+ 概念： 
	+ 把调入内存的页面根据调入的先后顺序排成一个队列，需要换出页面时选择队头页面即可；
	+ 队列的最大长度取决于系统为进程分配了多少个内存块；
+ 问题：
	+ 假设系统为某进程分配了四个内存块，并考虑到有以下页面号引用串：3,2，1,0，3，2，4，3，2，1,0，4
+ 分析：
	+ 分配四个内存块时缺页次数: 10 次 
	+ 分配三个内存块时缺页次数: 9 次
	+ 当为进程分配的物理块数增大时，缺页次数不减反增的异常现象 `->`  Belady 异常异常；
+ 图示：
	+ ![[Pasted image 20240405183229.png]]

### 7.3.3 最近最久未使用置换算法
**最近最久未使用置换算法 (LRU, least recently used)
+ 思想
	+ 每次淘汰的页面时**最近最久未使用的页面**；
+ 实现
	+ 赋予每个页面对应的页表项中，用访问字段记录该页面自上次被访问以来所经历的时间 t。
	+ 当需要淘汰一个页面时，选择现有页面中 t 值最大的，即最近最久未使用的页面。
+ 特点：
	+ 优点：
		+ 算法性能好，仅次于最佳置换算法；
	+ 缺点：
		+ 该算法的实现需要专门的硬件支持，虽然算法性能好，但是实现困难，开销大；
+ 方法： 
	+ 在手动做题时，若需要淘汰页面，可以逆向检查此时在内存中的几个页面号。在**逆向扫描过程中最后一个出现的页号**就是要淘汰的页面；
	+ 图示：
		+ ![[Pasted image 20240405183637.png]]
+ 图示：
	+ ![[Pasted image 20240405174616.png]]

### 7.3.4 时钟置换算法
**时钟置换算法 (NRU, Not Recently Used)
+ 概念：
	+ 时钟置换算法是一种性能和开销较均衡算法，又称 CLOCK 算法，或最近未用算法 (NRU，Not Recently Used)
	+ 称 CLOCK 算法，或**最近未用算法**（NRU）；
+ 结构：
	+ 访问位为 1，表示最近访问过。访问位为 0，表示最近没访问过；
	+ ![[Pasted image 20240405183904.png]]
+ 实现：
	+ 为每个页面设置一个访问位，再将内存中的页面都通过链接指针链接成一个循环队列；
	+ 当某页被访问时，其访问位置为 1。当需要淘汰一个页面时，只需检查页的访问位；
		+ 如果是 0，就选择该页换出；
		+ 如果是 1，则将它置换为 0，暂不换出，继续检查下一个页面；
	+ 若**第一轮扫描中所有页面都是 1，则将这些页面的访问依次置换为 0 后**，再进行第二轮扫描；
	+ 第二轮扫描中一定会有访问位为 0 的页面，因此简单的 CLOCK 算法选择一个淘汰页面最多会经过两轮扫描；
+ 图示：
	+ ![[Pasted image 20240405184239.png]]

### 7.3.5 改进型的时钟置换算法
**改进型的时钟置换算法**
+ 概念： 
	+ 如果被淘汰的页面没有被修改过，就不需要执行 IO 操作写回外存；
	+ 只有被淘汰的页面被修改过时，才需要写回外存；
	+ 除了考虑一个页面最近有没有被访问过之外，操作系统还应考虑**页面有没有被修改过**；
+ 思想：
	+ 在其他条件都相同时，应**优先淘汰没有修改过的页面**，避免 IO 操作； 
	+ `修改位=0`，表示页面没有被修改过; 
	+ `修改位=1`，表示页面被修改过;
+ 方法： 
	+ 用 $(访问位，修改位)$ 的形式表示各页面状态；
	+ 如 $(1，1)$ 表示一个页面近期被访问过、且被修改过；
+ 过程分析：
	+ 第一轮: 从当前位置开始扫描到第一个 (0,0)的帧用于替换。本轮扫描不修改任何标志位；
	+ 第二轮: 若第一轮扫描失败，则重新扫描，查找第一个 (0,1)的帧用于替换。本轮将所有扫描过的帧访问位设为 0；
	+ 第三轮: 若第二轮扫描失败，则重新扫描，查找第一个 (0,0)的帧用于替换。本轮扫描不修改任何标志位； 
	+ 第四轮: 若第三轮扫描失败，则重新扫描，查找第一个 (0,1)的帧用于替换； 
+ 结论：
	+ 由于第二轮已将所有帧的访问位设为 0，因此经过第三轮、第四轮扫描定会有一个帧被选中，因此改进型 CLOCK 置换算法**选择一个淘汰页面最多会进行四轮扫描**；

### 7.3.6 总结
![[Pasted image 20240405174704.png]]

## 7.4 页面分配策略
### 7.4.1 页面分配
**驻留集
+ 概念
	+ 指请求分页存储管理中**给进程分配的物理块的集合**；
	+ 在采用了虚拟存储技术的系统中，驻留集大小一般小于进程的总大小。
+ 问题
	+ 若驻留集太小 `->` 会导致缺页频繁，系统要花大量的时间来处理缺页，实际用于进程推进的时间很少；
	+ 若驻留集太大 `->` 又会导致多道程序并发度下降，资源利用率降低；
+ 分配策略
	+ 固定分配:
		+ 操纵系统为每个进程分配一组固定数目的物理块，在进程运行期间不再改变。
		+ 驻留集大小不变；
	+ 可变分配:
		+ 先为每个进程分配一定数目的物理块，在进程运行期间，可根据情况做适当的增加或减少。
		+ 驻留集大小可变；
+ 置换策略
	+ 局部置换:
		+ 发生缺页时只能选进程自己的物理块进行置换；
		+ 置换出的页面只能是自己的；
	+ 全局置换:
		+ 可以将操作系统保留的空闲物理块分配给缺页进程，也可以将别的进程持有的物理块置换到外存，再分配给缺页进程；
		+ 置换出的页面可以不是自己的；
		+ 全局置换意味着一个进程拥有的物理块数量必然会改变，因此不可能是固定分配；

### 7.4.2 置换策略
 **固定分配局部置换**
+ 思想
	+ 系统为每个进程分配一定数量的物理块，在整个运行期间都不可改变。
	+ 若进程在运行中发生缺页，则只能**从该进程在内存中的页面中选出一页换出**，然后再调入需要的页面。
+ 特点
	+ 优点:
		+ 很难在刚开始就确定应为每个进程分配多少个物理块才算合理；
	+ 缺点：
		+ 很难在刚开始就确定应为每个进程分配多少个物理块才算合理；

**可变分配全局置换**
+ 思想
	+ 刚开始会为每个进程分配一定数量的物理块。
	+ 操作系统会保持一个空闲物理块队列。
		+ 当某进程发生缺页时，从空闲物理块中取出一块分配给该进程
		+ 若无已空闲物理块，则可选择一个未锁定的页面换出外存，再将该物理块分配给缺页的进程。
+ 特点
	+ 缺点:
		+ 只要某进程发生缺页，都将获得新的物理块，仅当空闲物理块快用完时，系统才选择一个未锁定的页面调出。
		+ 被选择调出的页可能是系统中任何一个进程中的页，因此这个被选中的进程拥有的物理块会减少，缺页率会增加。
+ 补充：页面锁定
	+ 系统会锁定一些页面，这些页面中的内容不能置换出外存 (如: 重要的内核数据可以设为“锁定”）

**可变分配局部置换**
+ 思想
	+ 刚开始会为每个进程分配一定数量的物理块； 
	+ 当某进程发生缺页时，只允许从该进程自己的物理块中选出一个进程换出外存。
	+ 如果进程在运行中频繁缺页，系统会**为该进程分配几个物理块**，直至该进程缺页率趋势适当程度；
	+ 反之，如果进程在运行中缺页率特别低，**则可适当减少分配给该进程的物理块**；

**总结**
+ **可变分配全局置换
	+ 只要缺页就给分配新物理块
+ **可变分配局部置换
	+ 要根据发生缺页的频率来动态地增加或减少进程的物理块

### 7.4.3 何时调入所需页面
**预调页策略
+ 思想
	+ 根据空间局部性原理，一次调入若干个相邻的页面可能比调入一个页面更高效。
	+ 但如果提前调入的页面中大多数都没被访问过，则又是低效的；
+ 实现
	+ 因此可以预测不久之后可能访问到的页面，将它们预先调入内存，但目前预测成功率只有 50%左右。
+ 应用
	+ 故这种策略主要用于进程的首次调入，由程序员指出应该先调入哪些部分。
	+ 属于：运行前调入策略

**请求调页策略
+ 思想
	+ 进程在运行期间发生缺页时才将所缺页面调入内存。
	+ 由这种策略调入的页面一定会被访问到，但由于每次只能调入一页，而每次调页都要磁盘 I/O 操作，因此 I/O 开销较大。
+ 应用
	+ 运行时调入

### 7.4.4 从何处调入所需页面
**1. 系统拥有足够的对换区空间
+ 概念： 
	+ 页面的调入、调出都是在**内存与对换区之间进行**；
	+ 在进程运行前需将进程相关的数据从文件区复制到对换区；
+ 特点：
	+ 页面的调入、调出速度很快； 
+ 图示：
	+ ![[1712315397791.png]]

**2. 系统缺少足够的对换区空间
+ 概念： 
	+ 凡是**不会被修改的数据都直接从文件区调入**； 
	+ 由于这些页面不会被修改，因此换出时不必写回磁盘，下次需要时再从文件区调入即可；
	+ 对于**可能被修改的部分，换出时需写出磁盘对换区**，下次需要时再从对换区调入。

**补充：UNIX 方式
+ 概念： 
	+ 运行之前进程有关的数据全部放在文件区，故未使用过的页面，都可从文件区调入。
	+ 若被使用过的页面需要换出，则写会对换区，下次需要时从对换区调入。

### 7.4.4 常考概念：颠簸
**抖动 (颠簸)现象
+ 概念： 
	+ 刚刚换出的页面马上要换出内存，刚刚换入的页面马上又要换出外存；
	+ 这种频繁的页面调度行为称为**抖动**或**颠簸**；
+ 原因
	+ 进程频繁访问的页面数目高于可用的物理块数；
	+ 即：**分配给进程的物理块不够**；
+ 工作集
	+ 定义
		+ 指在某段时间间隔里，进程实际访问页面的集合；
	+ 内容
		+ 工作集大小可能小于窗口尺寸，实际应用中，操作系统可以统计进程的工作集大小，根据工作集大小给进程分配若干内存块。
		+ 一般来说，驻留集大小不能小于工作集大小，否则进程运行过程中将频繁缺页； 
	+ 举例
		+ 某进程的页面访问序列如下，窗口尺寸为 4；
		+ ![[Pasted image 20240405191354.png]]
+ 拓展
	+ 基于局部性原理可知，进程在一段时间内访问的页面与不久之后会访问的页面是有相关性的。
	+ 因此，可以根据进程近期访问的页面集合 (工作集)来设计一种页面置换算法——选择一个不在工作集中的页面进行淘汰

## 7.5 内存映射文件
**内存映射文件**
+ 概念： 
	+ 内存映射文件是操作系统向上层程序员提供的功能；
	+ 方便多个进程共享同一个文件的数据；
+ 传统方式：打开并修改文件
	+ `open` 系统调用：打开文件 
	+ `seek` 系统调用：将读写指针移到某个位置 
	+ `read` 系统调用：从读写指针所指位置读入若干数据 (从磁盘读入内存) 
	+ `write` 系统调用：将内存中的指定数据，写回磁盘
+ 内存映射文件：打开并修改文件 
	+ `open` 系统调用：打开文件 
	+ `mmap` 系统调用：将文件映射到进程的虚拟地址空间，返回起始地址
+ 特点：
	+ 1. 以访问内存的方式访问文件数据文件；
	+ 2. 数据的读入、写出由操作系统自动完成；
	+ 3. 进程关闭文件时，操作系统自动将文件被修改的数据写回磁盘；
+ 图示：自动分配与回收
	+ 当前访问指针在 2 位置时，OS 将自动将 2、3 位置的内容从磁盘读取进来，而不需要程序员自己调用 `read` 函数； 
	+ 回收内存时，只需要使用 `close` 系统调用，即可 OS 自动将内存回收；
	+ ![[1712316625033.png]]
+ 图示：实现文件共享 
	+ 多个进程可以实现映射同一个文件，实现共享；
	+ 在物理内存中，一个文件对应同一份数据，当一个进程修改文件数据时，另一个进程可以立马知道；
	+ ![[1712316820040.png]]