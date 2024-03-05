# A+B问题1
## 目录
* 变量定义
* 基本数据类型
* 面向对象
* 类的定义、属性和方法
* `new`关键字
* `private`和`public`
* `static`
* `import`关键字
* 输入：`Scanner`类的使用
* 输出语句
* `while`控制多次输入
## 笔记
- 类和面向对象
  
  **类**：对现实世界中所存在的事物的一种抽象，举个例子，将人抽象为一个类`Person`, 并具有一些“属性”和“方法”
  
  **属性**：`Person`类所具有的特征，比如姓名、年龄、性别，通过这些特征，我们可以描述一个“人”的基本状态。
  
  **方法**：表示`Person`类的行为和功能，比如吃饭、睡觉、行走，通过这些动作，我们可以描述一个“人”的动态行为。

  ``` java
  Person {
    // 姓名、性别、年龄等属性
    name;
    gender;
    age;
      // 吃饭的方法
      eat() {
    }
    // 行走的方法
    walk() {
    }
  }
  ```
  **创造一个类的实例**:
  ``` java
  // new Person()创建一个实例
  // 将这个实例起名为xiaoming
  // Person xiaoming表示这是一个Person的实例，xiaoming属于Person这种类型
  Person xiaoming = new Person();
  ```
- c程序的基本结构
  **文件名和主类名相对应**:假如文件名是`Main.java`，程序内要包含以下结构
  ``` java
  public class Main {
  
  }
  ```
  
  
