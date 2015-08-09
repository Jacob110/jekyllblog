---
layout: post
title:  "Java Collection"
date:   2015-08-09 11:21:44
categories: java
---

# Java 集合框架

------

Java集合是Java 提供的工具包，包含了常用的数据结构：集合、链表、队列、栈、数组、映射等。集合工具包的位置是 `java.util.*`

-------
Java 集合主要可以划分为四个部分：**List**列表、**Set**集合、**Map**映射、工具类(Iterator迭代器、Enumerattion枚举类、Arrays和Collections)。


集合框架分为两大类：

> * Collection
> 1. List
 > > * LinkedList
 > > * ArrayList
 > > * Vector
 > > * Stack
 
> 2. Set
> > * HashSet
> > * TreeSet

> * Map
> > *  HashMap
> > * TreeMap

------
## List 集合
`List`集合特有的迭代器。`ListIterator`是`Iterator`的子接口。
在迭代的时，不可以通过集合对象的方法操作集合中的元素。因为会发生`ConcurrentModifictionException`异常

用迭代器操作集合元素时，只能对元素进行判断，取出和删除操作。
**`List` 集合判断元素是否相同，依据的时 元素的 `equals` 方法**

### 1. ArrayList

- 线程不安全
- 遍历方式可以用 `for` `iterator` `get(index)`

### 2. Vector
- 线程安全
- 遍历方式除了 上面 `ArrayList` 的三种以为，还有`Enumeration`遍历,如下：

``` java
Vector vec=new Vector();
for(Enumeration enu=vec.elements(),vec.hasMoreElements();){
    Enumeration e=vec.nextElement();
}
```

### 3. LinkedList
## Set集合
元素无序，存入和取出的顺序不一定一致，元素不可以重复。
### 1.HashSet
底层数据结构是**哈希表**

- `HashSet` 是如何拨正元素唯一性的呢？
通过`hashCode` 和 `equals` 来完成。
如果元素的 `hashCode`值相同，才会去判断`equals` 是否为 true。否则不会调用 `equals`.
- 判断元素是否存在，以及删除等操作，依赖的方法是元素的`hashCode` 和 `equals` 方法。

### 2.TreeSet
- 可以对Set集合中的元素进行自然排序。
- `TreeSet` 中的元素(`Object`) 必须是可排序的，及必须实现 `compareTo` 方法
- 排序时，当主要条件相同时，一定要判断下次要条件
- 底层数据结构是 **`二叉树`**
- 保证元素唯一性的依据：`compareTo`方法 `return` `0`


