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

