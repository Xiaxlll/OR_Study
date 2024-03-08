# A+B问题2

## 目录
* `for`循环
* `while`循环
* 自增和自减
* `do while`循环
* 包装类型
* 自动装箱和自动拆箱
* 数据类型转换

## 练习题
第一次错啦😲，因为忘了i++，且
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
