# 奇怪的信

一遍过啦～
``` java
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        while(sc.hasNextInt()){
            int num = sc.nextInt();
            int sum = 0;
            while(num!=0){
                if((num%10)%2 == 0){
                    sum += num%10;
                }
                num = num/10;
            }
            System.out.println(sum);
            System.out.println();
        }
        sc.close();
    }
}
```
