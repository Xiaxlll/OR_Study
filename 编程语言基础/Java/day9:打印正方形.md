# 打印正方形

注意：
- 输出的格式；
- 注意n=1的情况；
- `int i`作为一个局部变量，只在while循环的方法体中有效，而它的生命周期就是每一次的循环结束，也就是说每一次循环结束，它就失去作用了。

## 输出
``` java
System.out.println(); // 输出完自带换行
System.out.print(); // 输出完无换行
```
## 练习

- 错误答案1
``` java
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        while(sc.hasNextInt()){
            int n = sc.nextInt();
            for(int i = 0;i < n;i++){
                System.out.print('*');
            }
            System.out.println();
            for(int t = 0;t < n-2;t++){
                for(int j = 0;j < n;j++){
                    if(j==0 || j==(n-1)){
                        System.out.print('*');
                    }else{
                        System.out.print(' ');
                    }
                }
                System.out.println();
            }
            for(int s = 0;s < n;s++){
                System.out.print('*');
            }
        }
        sc.close();
    }
}
```
- 正确答案
``` java
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        while(sc.hasNextInt()){
            int n = sc.nextInt();
            for(int i = 0;i < n;i++){
                if((i==0)||(i==(n-1))){
                    for(int j = 0;j < n;j++){
                        System.out.print('*');
                    }
                }else{
                    for(int t = 0;t < n;t++){
                        if((t==0)||(t==(n-1))){
                            System.out.print('*');
                        }else{
                            System.out.print(' ');
                        }
                    }
                }
                if(i!=(n-1)){
                    System.out.println();
                }
            }
        }
        sc.close();
    }
}
```
