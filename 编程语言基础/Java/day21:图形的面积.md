# 图形的面积

面向对象中的三大特性：封装、继承、多态

## 类
1. 类的基本写法。一个类中包含属性（成员变量）和方法（成员方法），属性表示类的静态特征，方法表示类的动态行为。
``` java
public class Person {
  // 成员变量
  private String name;
  // 构造方法
  public Person(String name) {
    this.name = name;
  }
  // 成员方法
  public void sayHello() {
    
  }
  // 主方法，程序的入口
  public static void main(String[] args) {
    // 创造一个 Person 对象
    Person person1 = new Person("Tom");
    // 调用对象的方法
    person1.sayHello();
  }
}
```
2. 成员变量
  * 成员变量的定义（访问修饰符、数据类型、变量名。）
    - 访问修饰符
      * `private`（私有，只能在类内部访问）
      * `public`（公共，可以从任何地方访问）
      * `protected`（受保护，可以在类内部和子类中访问）
3. 成员方法
   ``` java
   public class MyClass {
    // 成员方法的定义
    // 访问修饰符 返回类型 方法名(参数列表) {
    //     方法体
    // }

    // 无参数的成员方法，返回类型为void
    public void doSomething() {
        // 方法体, 在这里执行操作
    }

    // 带参数的成员方法，返回整数类型
    public int add(int a, int b) {
        // 方法体,在这里执行操作，并 return 结果
        return a + b;
    }
   }
   MyClass obj1 = new MyClass();
   obj1.doSomething(); // 调用无参数方法
   int sum = obj1.add(5, 3); // 调用带参数方法，将结果存储在 sum 变量中
   ```
4. 构造函数是一种特殊类型的成员方法，在创建对象时自动调用，通常用于为成员变量赋初始值。
   ``` java
   public class MyClass {
    // 成员变量
    private int age;
    private String name;

    // 无参构造函数
    public MyClass() {
        // 在构造函数中进行初始化
        age = 20;
        name = "zs";
    }

    // 带参数的构造函数
    public MyClass(name, age) {
        // 在构造函数中进行初始化
        this.name = name;
          this.age = age;
    }
   }
   ```
## 封装（保证数据的安全性）
通过封装隐藏对象中一些不希望被外部所访问到的属性或方法，具体怎么做呢？可以分为两步：
* 将对象的属性名，修改访问修饰符为private, 这样就只能在内部类中访问，其他类访问不了。
* 提供`getter`和`setter`来获取和设置对象的属性
``` java
public class Circle {
      // 1. 将属性名，设置为私有的
    private int radius;

    // 构造函数
    public Circle(int radius) {
        setRadius(radius);
    }

    // 2. 定义set方法，设置属性
    public void setRadius(int radius) {
        this.radius = radius
    }

    // 2. 定义get方法，获取属性
    public int getRadius() {
        return radius;
    }
}
```

``` java
Circle circle = new Circle(5);

// 获取半径
int radius = circle.getRadius();

// 设置半径
circle.setRadius(8);
```
## 继承(使得一个类获取到其他类中的属性和方法)
在类名后使用`extends`指定当前类的父类（超类), 子类可以直接继承父类中的所有属性和方法，从而避免编写重复性的代码，此外我们还可以对子类进行扩展。
* 继承的格式
  ``` java
  class A{  
    
  }

  class B extends A{
    
  }
  ```
* 例子（`abstract`的意思是抽象类，不能被实例化）
  ``` java
  abstract class Shape {
      // 定义属性 type
    protected String type;
         // 定义方法CalculateArea，用来计算图形面积，方法体为空
    public double CalculateArea();
 
    // 构造方法
    public Shape(String type) {
        this.type = type;
    }
  }

  // extends表示继承，即Circle类继承自Shape类
  class Circle extends Shape {
    private int radius;
 
    public Circle(String type, int radius) {
          super(type); // 调用父类的构造方法，传递 type属性
        this.radius = radius;
    }
         // 重写父类的求面积方法
      @Override
    public double CalculateArea() {
        return 3.14 * radius * radius;
    }
  }
  ```
  * 在上面的示例代码中，图形类Shape拥有属性type，Circle类由于继承了Shape类，在其构造函数中，使用super(type)调用父类的构造方法后，子类的实例就会拥有父类的type属性。
  * 在子类和父类中都有CalculateArea这个方法，这被称为方法的重写，这是对父类继承的方法的修改。
  * 方法的重写要求子类中的方法（方法名、参数类型和个数、返回类型）必须与父类中的方法相同，然后子类会调用自己的方法而不是父类的同名方法。
## 抽象类
抽象方法是一种没有具体的方法，只有方法的声明，没有方法体，并且只能存在于抽象类中。
``` java
// 抽象类 Shape
abstract class Shape {
      // 抽象方法
    public abstract double calculateArea();
}
```
## 多态
多态常常和继承紧密相连，它具有两种形式：编译时多态（静态多态）和运行时多态（动态多态）。
* 编译时多态：类有基类和子类，最初，我们可能不知道应该使用哪个类，所以使用基类来调用方法。
* 运行时多态：程序运行的时候，会根据对象实际的类来调用相应的方法。

例子：基类 Shape 实现了`` calculateArea方法, 两个派生类Circle和Rectangle则是重写了 calculateArea` 方法，它们有着不同的计算逻辑。
``` java
// Shape 类
abstract class Shape {
    public abstract double calculateArea();
}

// Circle 类
class Circle extends Shape {
    private int radius;

    // 构造方法
    public Circle(int radius) {
        this.radius = radius;
    }

    // 实现父类的抽象方法，计算圆形的面积
    @Override
    public double calculateArea() {
        return 3.14 * radius * radius;
    }
}

// Rectangle 类
class Rectangle extends Shape {
    private int length;
    private int width;

    // 构造方法
    public Rectangle(int length, int width) {
        this.length = length;
        this.width = width;
    }

    // 实现父类的抽象方法，计算长方形的面积，返回的width和height为整数类型，Java采用类型转换将其转为double
    @Override
    public double calculateArea() {
        return length * width;
    }
}
```
而在调用时，最初不知道是哪种类型，所以统一创建Shape类型的引用, 分别指向了 Circle 和 Rectangle 对象。
``` java
// 创建 Shape 类型的引用，指向 Circle 对象
Shape myCircle = new Circle(5);

// 创建 Shape 类型的引用，指向 Rectangle 对象
Shape myRectangle = new Rectangle(4, 6);
```
``` java
// 创建 Shape 类型，指向 Circle 对象
Shape myCircle = new Circle(5);
// 虽然是Shape类型，但是调用方法时根据对象本身的类型来处理
double circleArea = myCircle.calculateArea();
System.out.println("圆形的面积：" + circleArea);

// 创建 Shape 类型，指向 Rectangle 对象
Shape myRectangle = new Rectangle(4, 6);
// 虽然是Shape类型，但是调用方法时根据对象本身的类型来处理
double rectangleArea = myRectangle.calculateArea(); 
System.out.println("长方形的面积：" + rectangleArea);
```

## 练习
* 注意.判断字符串是否相等要用`.equals()`

``` java
import java.util.*;

abstract class Shape{
    protected String type;
    public abstract double Calculate();
    public String getType(){
        return type;
    }
}

class Rectangle extends Shape{
    private int width;
    private int height;

    // 构造方法
    public Rectangle(int width, int height){
        this.type = "Rectangle";
        this.width = width;
        this.height = height;
    }
    @Override
    public double Calculate(){
        return width*height;
    }

}

class Circle extends Shape{
    private int radius;

    public Circle(int radius){
        this.type = "Circle";
        this.radius = radius;
    }

    @Override
    public double Calculate(){
        return 3.14 * radius * radius;
    }
}

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        
        ArrayList<Shape> shapes = new ArrayList<>();

        while(true){
            String inputLine = sc.nextLine();
            String[] data = inputLine.split(" ");
            String ShapeType = data[0];

            if(ShapeType.equals("end")){
                break;
            }else if(ShapeType.equals("rectangle")){
                int width = Integer.parseInt(data[1]);
                int height = Integer.parseInt(data[2]);
                shapes.add(new Rectangle(width, height));
            }else if(ShapeType.equals("circle")){
                int radius = Integer.parseInt(data[1]);
                shapes.add(new Circle(radius));
            }
        }

        for(Shape shape : shapes){
            System.out.printf("%s aresa: %.2f\n",shape.getType(), shape.Calculate());
        }

    }
}
```









