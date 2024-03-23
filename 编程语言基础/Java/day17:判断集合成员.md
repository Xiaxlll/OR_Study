# 判断集合成员

学习`set`集合，使用`set`来实现哈希表

* `set`的概念和特点
* `set`的基本操作，比如创建、插入、删除、查找
* `HashSet`的常用方法
* `Set`集合的遍历
* 迭代器

## `set`
在 Java 中，`Set` 是一种集合接口，和数学中的集合类似，它用于存储一组**不重复**的元素，并且不保证元素的顺序。查找通常是`Set`最重要的操作，它最常见的用法是判断某个对象是否在`Set`中和去除集合中的重复元素。

`Set` 接口的常见**实现类**包括 `HashSet`、`TreeSet` 和 `LinkedHashSet`，我们通常会选择`HashSet`作为实现。

## `HashSet`的使用
1. 导入`Set` 接口以及它的实现类`HashSet`
  ``` java
  import java.util.Set; // 导入Set
  import java.util.HashSet; // 导入HashSet
  ```
2. `Set`接口的常用方法
  * `add(element)：`向集合中添加元素，如果元素已存在，则不会重复添加。
  * `remove(element)：`从集合中移除指定元素。
  * `contains(element)：`检查集合中是否包含指定元素。
  * `isEmpty()：`判断集合是否为空。
  * `size()：`返回集合中的元素数量。
  * `clear()：`清空集合中的所有元素。
  ``` java
  // 创建一个HashSet实例
  Set<String> set = new HashSet<>();

  // 向集合中插入元素
  set.add("zs");
  set.add("ls");
  set.add("Mike");

  // 检查集合中是否包含特定元素
  boolean containMike = set.contains("mike");  // 返回true

  // 从集合中删除元素
  set.remove("zs");

  // 检查集合是否为空
  boolean isEmpty = set.isEmpty();
  ```
## 接口和实现类
接口是一种抽象数据类型，定义了一组抽象方法，但是**方法通常不包含方法体，而只有方法的声明**，主要是用来定义某种行为的规范，而实现类是**具体的类**，它实现了一个或多个接口定义的抽象方法，并且提供了这些方法的具体实现。

## 练习
