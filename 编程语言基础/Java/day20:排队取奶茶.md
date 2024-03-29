# 排队取奶茶

## 目录
* 队列的基本概念（队头、队尾）和特点（先入先出）
* 双端队列
* 入队、出队、获取队头元素和判断队列是否为空等基本操作
* `ArrayDeque`的使用

## 队列和双端队列
先进先出FIFO
<img width="549" alt="image" src="https://github.com/Xiaxlll/OR_Study/assets/77572858/844b6c98-f38c-4f4b-8280-8d8b0ac9bddb">

双端队列允许在队列的两端（前端和后端）都能进行插入（添加元素）和删除（移除元素）操作，结合了队列（先进先出，FIFO）和栈（后进先出，LIFO）的特性，因此可以使用双端队列来实现队列这种结构，这使得它拥有更多的应用场景。

## 队列的操作
1. 导入`java.util.Queue`接口，然后选择具体的队列实现类（例如 ArrayDeque 或 LinkedList）来创建队列对象。
   * 使用`ArrayDeque`实现队列
   ``` java
   import java.util.Queue;
   import java.util.ArrayDeque; // 如果要使用 ArrayDeque 实现队列
   ```
   * 使用`LinkedList`实现队列
   ``` java
   import java.util.Queue;
   import java.util.LinkedList; // 如果要使用 LinkedList 实现队列
   ```
2. 创建队列
   ``` java
   Queue<String> queue = new LinkedList<>(); // 使用LinkedList实现队列

   Queue<Integer> queue = new ArrayDeque<>(); // 使用ArrayDeque实现队列
   ```
3. 队列的常用操作
   * isEmpty(): 判断队列是否为空，如果队列为空返回true， 否则返回false
   * add(): 入队操作，将新的元素添加到队列的尾部。
   * poll()： 出队操作，获取并移除队列的头部元素。
   * peek(): 访问队列的头部元素，但不会将其移除。
   * size(): 获取队列的长度，即队列中元素的数量。

   ``` java
   queue.add("Jack"); 
   queue.add("Mike"); // 入队了两个名称字符串

   String name = queue.poll(); // 移除队列头部的元素

   String name = queue.peek(); // 获取队列头部的元素但是不会将其移除,如果队列为空，返回null

   boolean isEmpty = queue.isEmpty(); //  如果队列为空，返回true；否则返回false

   int queueSize = queue.size(); // 获取队列中元素的数量
   ```
