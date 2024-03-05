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
  
  **类**：对现实世界中所存在的事物的一种抽象，举个例子，将人抽象为一个类`Person`, 并具有一些“属性”和“方法”，类的名称通常以大写字母开头
  
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
  // 使用class关键字定义一个public(公开)类，类的名称是Main
  public class Main {
    public static void main(String[] args){
    }
  }
  ```
  * `public`是一个访问修饰符， 除了可以修饰`class`外，也可以修饰方法，表示该方法是公开的，对于`main`来说，它必须是`public`的。
  * 关键字`static`是另一个修饰符，它表示静态方法，后面我们会讲解方法的类型，目前，我们只需要知道，Java入口程序规定的方法必须是静态方法。
  * `void` 表示该方法不返回任何值。
  * `main`是方法的名称，作为程序的入口点，而且入口的名称方法名必须为`main`
  * `String[] args`：这是 `main` 方法的参数。
- 方法的组成
  
- 输入输出
- 变量
- 程序编写
- 延伸
- 访问修饰符
  
  
  
