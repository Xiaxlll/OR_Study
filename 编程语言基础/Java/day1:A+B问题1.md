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
  方法包含以下四部分：返回类型、方法名、形参列表、方法体
  ``` java
  ReturnType methodName(/* 参数列表 */) {
  // 方法体
  }
  ```
- 输入输出
  * 标准输入：`System.in`；是一个标准的输入流，它允许你从控制台（键盘）获取用户输入的数据。
  * `Scanner` 是 Java 中的一个类，它位于 `java.util` 包中，它提供了一种简便的方式来处理输入数据。
  * `Scanner`类中的一些方法:
    - next()：读取下一个字符串。
    - nextInt()：读取下一个整数。
    - nextDouble()：读取下一个双精度浮点数。
    - nextLine()：读取下一行文本。
    - hasNext()：判断是否还有下一个输入项。如果有，返回 true；否则返回 false。
    - hasNextInt()：判断是否还有下一个整数输入项。
    - hasNextDouble()：检查是否还有下一个双精度浮点数输入项。
  * 标准输出：System.out
  ``` java
  import java.util.Scanner;
  public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        
        sc.close(); // 关闭Scanner对象
    }
  }
  ```
- 变量
  ``` java
  int a; // 定义一个变量，名称为a, 用于接收一个整数
  int b; // 定义一个变量，名称为b, 用于接收一个整数
  int a, b;// 不写初始值时，默认是0
  int a = 1; // 定义一个整数类型变量，并赋予初始值1
  ```
- 程序编写
  `Scanner`使用`nextInt()`方法读取并返回下一个整数
  ``` java
  int a = sc.nextInt(); // 读取下一个整数，并将之赋值给变量a
  int b = sc.nextInt(); // 读取下一个整数，并将之赋值给变量b
  ```
  ``` java
  import java.util.Scanner;

  public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
          int a = sc.nextInt();
        int b = sc.nextInt();
        System.out.println(a+b);
        sc.close(); 
    }
  }
  ```
- 延伸
  **数据类型**
  * 整数类型
    ``` java
    byte score = 98;
    short age = 130;
    int count = 100000;
    long gdp = 10000000000L;
    ```
  * 浮点类型
    ``` java
    float floatValue = 3.14159f; // 使用 'f' 后缀表示 float
    double price = 2.99; // 默认是double类型
    ```
  * 字符类型
    
  * 布尔类型
  * 
- 访问修饰符
  
  
  
