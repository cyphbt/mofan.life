---
title: 数据库
categories:
  - 面试
  - 数据库
tags:
  - 面试
date: 2021-03-10 09:22:13
---

## 数据库分区、分表，读写分离

### 分区

就是把一张表的数据分成N个区块，在逻辑上看最终只是一张表，但底层是由N个物理区块组成的。

### 分表

就是把一张表按一定的规则分解成N个具有独立存储空间的实体表。系统读写时需要根据定义好的规则得到对应的字表明，然后操作它。

### 读写分离

读写分离，基本的原理是让主数据库处理事务性增、改、删操作（INSERT、UPDATE、DELETE），而从数据库处理SELECT查询操作。数据库复制被用来把事务性操作导致的变更同步到集群中的从数据库。

## 冷热数据怎么处理？redis和mysql，如何保证数据一致性



## 使用MySQL有哪些好处



## InnoDB的特性，底层，数据分区，如何加快读写效率



## innodb 和 myisam 的区别



## 主键和索引的联系和区别



## MySQL索引和B+树



## 索引优化 

 

## explain 执行计划 

 

## extra的 using indexing 和 using where 

 

## 覆盖索引 

 

## 聚簇索引和辅助索引 



##  讲一下Redis

简单来说 redis 就是一个数据库，不过与传统数据库不同的是 redis 的数据是存在内存中的，所以存写速度非常快，因此 redis 被广泛应用于缓存方向。另外，redis 也经常用来做分布式锁。redis 提供了多种数据类型来支持不同的业务场景。除此之外，redis 支持事务 、持久化、LUA脚本、LRU驱动事件、多种集群方案。

## 为什么要用Redis做缓存

在项目中使用 Redis，主要考虑两个角度：性能和并发。如果只是为了分布式锁这些其他功能，还有其他中间件 Zookpeer 等代替，并非一定要使用 Redis。

## nosql 说下 



## 数据库查询数据慢如何解决



## SQL优化



## 哈希索引和B+树索引的区别

1.在查询速度上，如果是等值查询，那么哈希索引有绝对的优势，因为只需要经过一次哈希计算就能找到相应的值，时间复杂度是O(1)，但是，如果存在哈希碰撞，那么其查询效率将会降低，时间复杂度会变成O(n)，所以，哈希索引一般不会用在重复多的列上，比如性别、年龄的情况等。（当然，B+树不适合用在这种离散程度低的列上）

2.Hash索引是无序的，所以，不能进行范围查找，即使原先有序的列，经过哈希计算后，也会变成不连续的。

3.Hash索引不支持多列联合索引，对于联合索引来说，哈希索引在计算哈希值的时候，是将索引键合并，然后计算哈希值。

4.因为哈希索引存在哈希碰撞问题，所以，在有大量重复键的情况下，哈希索引查询效率极低，而B+树的所有查询都要找到叶子结点，性能较为稳定。

## 哈希索引与B+索引场景区分

1.在大多数场景下，都会有组合查询、范围查询、排序、分组、模糊查询等查询特征，Hash索引无法满足要求，建议数据库使用B+树索引。

2.在数据离散度高，数据基数大，而且是等值查询的时候，建议使用哈希索引。

## 哈希索引在内存还是在磁盘

在内存


## 缓存击穿 缓存雪崩


