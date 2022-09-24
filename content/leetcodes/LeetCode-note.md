---
title: "LeetCode Note"
date: 2022-09-23T10:21:48+08:00
tags: ["leetcode"]
draft: true
---

## 链表

### 合并两个有序链表

#### 解法

略

详见：<https://blog.zhangmengyang.tk/leetcodes/leetcode-21/>

#### 题目

##### 1. [合并两个有序链表](https://leetcode.cn/problems/merge-two-sorted-lists/)

### 单链表的分解

#### 解法

从头到尾遍历一遍链表，将小于x的放到一个链表里，将大于等于x的放到一个链表里，最后再拼接这两个链表即可，注意dummy节点的使用。

详见：<https://blog.zhangmengyang.tk/leetcodes/leetcode-86/>

#### 题目

##### 1. [分隔链表](https://leetcode.cn/problems/partition-list/)

### 合并 k 个有序链表

#### 解法

每次取出一个最小的加到链表中去，那问题就是怎么高效的获取最小的节点，这很明显用优先队列（二叉堆）就可以解决这个问题。

详见：<https://blog.zhangmengyang.tk/leetcodes/leetcode-23/>

#### 题目

##### 1. [合并K个升序链表](https://leetcode.cn/problems/merge-k-sorted-lists/)

### 寻找单链表的倒数第 k 个节点

#### 解法

关键是找到倒数第n+1个节点，找到倒数第n个节点的做法：先让快指针走n步，然后快慢指针一起动，当快指针到头了的时候，慢指针指向的就是需要找的节点。

注意使用dummy节点可以避免特殊性，比如就5个节点，删除倒数第5个，那需要找倒数第6个节点，可是总共就5个节点，会有空指针。

详见：<https://blog.zhangmengyang.tk/leetcodes/leetcode-19/>

#### 题目

##### 1. [删除链表的倒数第 N 个结点](https://leetcode.cn/problems/remove-nth-node-from-end-of-list/)

### 单链表的中点

#### 解法

利用快慢指针的思想，每当慢指针 `slow` 前进一步，快指针 `fast` 就前进两步，这样，当 `fast` 走到链表末尾时，`slow` 就指向了链表中点。

需要注意的是，如果链表长度为偶数，也就是说中点有两个的时候，我们这个解法返回的节点是靠后的那个节点。

详见：<https://blog.zhangmengyang.tk/leetcodes/leetcode-876/>

#### 题目

##### 1. [链表的中间结点](https://leetcode.cn/problems/middle-of-the-linked-list/)

### 判断链表是否包含环

#### 解法

利用快慢指针的思想，如果快指针为空，说明没有环，如果快慢指针相遇说明有环

详见：<https://blog.zhangmengyang.tk/leetcodes/leetcode-141/>

#### 题目

##### 1. [环形链表](https://leetcode.cn/problems/linked-list-cycle/)

### 存在环的链表中寻找环起点

#### 解法

利用快慢指针的思想并且稍做分析，即可得出结论：当快慢指针相遇时，让其中任一个指针指向头节点，然后让它俩以相同速度前进，再次相遇时所在的节点位置就是环开始的位置。

详见：<https://blog.zhangmengyang.tk/leetcodes/leetcode-142/>

#### 题目

##### 1. [环形链表 II](https://leetcode.cn/problems/linked-list-cycle-ii/)

### 判断两个链表是否相交

#### 解法

找到相交点的关键是将相交点之前的节点数凑成相等的，这样的话同时遍历，如果相等的话就是相交了。怎么凑呢？将两个链表连接一下，节点数不就想等了吗。

代码实现方面，可以考虑四种情况：

1. 长度相等，有相交
2. 长度相等，无相交
3. 长度不等，有相交
4. 长度不等，无相交

符合这四种情况的链表连接方法如下：

l1 -> null -> l2 -> null

l2 -> null -> l1 -> null

另一种做法：将某一条链表首尾相连，该问题就转换为寻找有环链表的环起点问题。

详见：<https://blog.zhangmengyang.tk/leetcodes/leetcode-160/>

#### 题目

##### 1. [相交链表](https://leetcode.cn/problems/intersection-of-two-linked-lists/)

### 反转单链表

#### 解法

利用递归的思想，先反转head后面的，然后把head也反转即可。

详见：<https://blog.zhangmengyang.tk/leetcodes/leetcode-206/>

#### 思想

反转的过程就是改变指针方向的过程并且最后一个指向null，比如反转第2个---第5个：

1 -> 2 -> 3 -> 4 -> 5 -> null

反转后为：

1 -> 2 <- 3 <- 4 <- 5

​	 null

#### 题目

##### 1. [反转链表](https://leetcode.cn/problems/reverse-linked-list/)

### 反转链表前n个节点

#### 解法

解决思路和反转整个链表差不多，只要稍加修改即可：

1、base case 变为 `n == 1`，反转一个元素，就是它本身，同时**要记录后驱节点**。

2、刚才我们直接把 `head.next` 设置为 null，因为整个链表反转后原来的 `head` 变成了整个链表的最后一个节点。但现在 `head` 节点在递归反转之后不一定是最后一个节点了，所以要记录后驱 `successor`（第 `n + 1` 个节点），反转之后将 `head` 连接上。

详见：<https://blog.zhangmengyang.tk/leetcodes/反转链表前n个节点/>

#### 题目

无

### 反转链表节点(m, n)

#### 解法

与反转链表前n个节点区别在于不是从第一个节点开始反转，而是从left开始，那么只需要利用递归一次head往后移一位，left和right分别减一的特性，把head移到left的位置，然后反转前n个节点即可。

详见：<https://blog.zhangmengyang.tk/leetcodes/leetcode-92/>

#### 题目

##### 1. [反转链表 II](https://leetcode.cn/problems/reverse-linked-list-ii/)

### K 个一组翻转链表

#### 解法

**1、先反转以 `head` 开头的 `k` 个元素**。

**2、将第 `k + 1` 个元素作为 `head` 递归调用 `reverseKGroup` 函数**。

**3、将上述两个过程的结果连接起来**。

注意base case为最后元素不足 k 个时的情况

详见：<https://blog.zhangmengyang.tk/leetcodes/leetcode-25/>

#### 题目

##### 1. [K 个一组翻转链表](https://leetcode.cn/problems/reverse-nodes-in-k-group/)

### 链表的前后序遍历

```java
void traverse(ListNode head) {
    // 前序遍历代码
    traverse(head.next);
    // 后序遍历代码
}
```

### 回文串

#### 寻找回文串

核心思想是从中心向两端扩展

#### 判断回文串

核心思想是从两端向中间逼近

### 判断回文链表

#### 解法

可以将链表全部反转，也可以部分反转

##### 链表全部反转

链表全部反转的方法共3种：

###### 将原链表反转，然后与原链表比较

略

###### 链表后序遍历

链表也可以后序遍历，这道题只需要使用后序遍历，然后提前存一下head，从两边向中间逼近就可以了。

详见：<https://blog.zhangmengyang.tk/leetcodes/leetcode-234-链表后序遍历/>

###### 利用栈

同链表后序遍历

##### 链表部分反转

###### 快慢指针+反转链表

先用快慢指针找到链表的中点，从而找到回文串的后一半，然后将后一半反转，然后判断前后两部分是否相等就行了。

详见：<https://blog.zhangmengyang.tk/leetcodes/leetcode-234-快慢指针+反转链表/>

#### 题目

##### 1. [回文链表](https://leetcode.cn/problems/palindrome-linked-list/)

## 数组

### 快慢指针在数组中的应用

#### 数组元素去重

##### 解法

慢指针指向当前已经去重的数据的最后一个，快指针去前面探路，碰到和slow不一样的数据就让这个数据放在slow后面，slow++。

具体变种详见：<https://blog.zhangmengyang.tk/leetcodes/leetcode-26+83+27+283/>

##### 题目

###### 1. [删除有序数组中的重复项](https://leetcode.cn/problems/remove-duplicates-from-sorted-array/)

###### 2. [删除排序链表中的重复元素](https://leetcode.cn/problems/remove-duplicates-from-sorted-list/)

###### 3. [移除元素](https://leetcode.cn/problems/remove-element/)

###### 4. [移动零](https://leetcode.cn/problems/move-zeroes/)

#### ==滑动窗口==

##### 解法

`left` 指针在后，`right` 指针在前，两个指针中间的部分就是「窗口」，算法通过扩大和缩小「窗口」来解决某些问题。

详见：<https://labuladong.gitee.io/algo/2/20/27/>

##### 题目

暂无

### 左右指针在数组中的应用

#### ==二分查找==

详见：<https://labuladong.gitee.io/algo/2/20/29/>

#### 两数之和

##### 解法

利用左右指针的思想，从两边向中间逼近，如果左右之和太大，那就right--，否则left++，直到左右之和等于target。

详见：<https://blog.zhangmengyang.tk/leetcodes/leetcode-167/>

##### 题目

###### 1. [两数之和 II - 输入有序数组](https://leetcode.cn/problems/two-sum-ii-input-array-is-sorted/)

##### 扩展

==一个函数秒杀所有 nSum 问题==，详见：<https://labuladong.gitee.io/algo/1/15/>

## 思想

### 双指针

就是两个指针，分为左右指针和快慢指针，只要数组有序，就应该想到双指针技巧

#### 左右指针

两个指针一个左一个右，不解释

#### 快慢指针

两个指针一个快一个慢，不解释

### 递归

一个问题 = 规模更小的同类问题 + 扩展成该问题要解决的问题

这种情况就可以用递归，递归的关键是不要跳进递归，而是明确递归函数的定义

递归由两部分组成：递归出口和递归公式

注意递归需要递归出口（也就是base case）

值得一提的是，递归操作链表并不高效。和迭代解法相比，虽然时间复杂度都是 O(N)，但是迭代解法的空间复杂度是 O(1)，而递归解法需要堆栈，空间复杂度是 O(N)。

## 其他

### 零碎

从整体到细节，自顶向下，从抽象到具体的框架思维是通用的，不只是学习数据结构和算法，学习其他任何知识都是高效的。

数据结构的物理存储方式就是链式和顺序两种，基本操作就是增删改查，遍历方式无非迭代和递归。

计算机算法的本质就是枚举，只不过这里枚举需要做到两个方面：无遗漏和无冗余，有时候还可以利用一些定理进行优化（缩小搜索范围），比如剪枝和数学定理

难点在无遗漏的问题：

难点在无冗余的问题：递归类问题（动态规划）

难点在优化的问题：非递归类问题（并查集，贪心，KMP）

Java里优先队列就是二叉堆，也就是PriorityQueue

### 待做

https://labuladong.gitee.io/algo/1/3/的那几个算法框架及之后的几个框架文章都没看

### 技巧

dummy（虚拟头结点)：可以很好的避免第一个节点的特殊性，将第一个节点当作第二个节点，也即是所有节点统一处理

