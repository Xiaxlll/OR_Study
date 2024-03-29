# A+B问题2

## 目录
* `for`循环
* `while`循环
* 自增和自减
* `do while`循环
* 包装类型
* 自动装箱和自动拆箱
* 数据类型转换

## 包装类型
基本数据类型(int、double)本身不是对象，因此Java内部将这些基础数据类型用“类”的形式包装起来，形成“包装类”，这些包装类内部提供了很多的方法方便我们使用，并且可以执行与对象有关的操作，下面就是常见的基本数据类型和其对应的包装类。
- `Integer`: 包装`int`类型。
- `Long`: 包装`long`类型。
- `Short`: 包装`short`类型。
- `Byte`: 包装`byte`类型。
- `Double`: 包装`double`类型。
- `Float`: 包装`float`类型.
- `Character`: 包装`char`类型。
- `Boolean`: 包装`boolean`类型。
包装类型就是在“基本数据”类型外面包装了一层，使其变成了对象，并在上面增加了一点功能而已。
## 自动装箱和自动拆箱
我们不是在“基本数据类型”上包装了一层形成“包装类”嘛，这个过程就叫自动装箱，而自动拆箱是把这个“包装”给拆掉，将包装类型对象转为对应的基本数据类型。
例子：
``` java
//自动装箱
int age = 10; // 基本数据类型10
Integer boxedAge = age; // Integer boxedAge声明了一个包装对象，直接将10赋予这个对象，系统会帮我们将 10 装箱后放入到 boxedAge
//自动拆箱
Integer boxedAge = 10;
int age = boxedAge;
```

## 练习题
第一次错啦😲，因为忘了`i++`，且测试的数据有可能有多组N，所以使用`hasNextInt()`函数十分有必要
``` java
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();
        int i = 1;
        while(i <= N){
            int a = sc.nextInt();
            int b = sc.nextInt();
            System.out.println(a+b);
            i++;
        }
        sc.close();
    }
}
```
正确答案：
``` java
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        while(sc.hasNextInt()){
            int N = sc.nextInt();
            int i = 1;
            while(i <= N){
                int a = sc.nextInt();
                int b = sc.nextInt();
                System.out.println(a+b);
                i++;
            }  
        }
        sc.close();
    }
}
```
<img width="653" alt="image" src="https://github.com/Xiaxlll/OR_Study/assets/77572858/ec032e34-04f0-4057-b365-13ee096212b1">

