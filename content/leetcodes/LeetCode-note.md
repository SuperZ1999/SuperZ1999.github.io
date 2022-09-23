---
title: "LeetCode Note"
date: 2022-09-23T10:21:48+08:00
tags: ["leetcode"]
draft: true
---

## 链表

### 合并 k 个有序链表

#### 解法

每次取出一个最小的加到链表中去，那问题就是怎么高效的获取最小的节点，这很明显用优先队列（二叉堆）就可以解决这个问题。

#### 题目

#### 1. [合并K个升序链表](https://leetcode.cn/problems/merge-k-sorted-lists/)

### 寻找单链表的倒数第 k 个节点

#### 解法

关键是找到倒数第n+1个节点，找到倒数第n个节点的做法：先让快指针走n步，然后快慢指针一起动，当快指针到头了的时候，慢指针指向的就是需要找的节点。

注意使用dummy节点可以避免特殊性，比如就5个节点，删除倒数第5个，那需要找倒数第6个节点，可是总共就5个节点，会有空指针。

#### 题目

#### 1. [删除链表的倒数第 N 个结点](https://leetcode.cn/problems/remove-nth-node-from-end-of-list/)

### 单链表的中点

#### 解法

利用快慢指针的思想，每当慢指针 `slow` 前进一步，快指针 `fast` 就前进两步，这样，当 `fast` 走到链表末尾时，`slow` 就指向了链表中点。

需要注意的是，如果链表长度为偶数，也就是说中点有两个的时候，我们这个解法返回的节点是靠后的那个节点。

#### 题目

#### 1. [链表的中间结点](https://leetcode.cn/problems/middle-of-the-linked-list/)

### 判断链表是否包含环

#### 解法

利用快慢指针的思想，如果快指针为空，说明没有环，如果快慢指针相遇说明有环

#### 题目

#### 1. [环形链表](https://leetcode.cn/problems/linked-list-cycle/)

### 存在环的链表中寻找环起点

#### 解法

利用快慢指针的思想并且稍做分析，即可得出结论：当快慢指针相遇时，让其中任一个指针指向头节点，然后让它俩以相同速度前进，再次相遇时所在的节点位置就是环开始的位置。

详见：[](https://blog.zhangmengyang.tk/leetcodes/leetcode-142/)

#### 题目

#### 1. [环形链表 II](https://leetcode.cn/problems/linked-list-cycle-ii/)

## 思想

### 快慢指针

两个指针一个快一个慢，不解释

## 其他

### 零碎

Java里优先队列就是二叉堆，也就是PriorityQueue
