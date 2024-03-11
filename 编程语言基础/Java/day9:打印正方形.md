# 打印正方形

注意输出的格式；注意n=1的情况

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
