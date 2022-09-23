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



#### 题目

#### 

## 其他

### 零碎

Java里优先队列就是二叉堆，也就是PriorityQueue