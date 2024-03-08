# A+B问题4
2024.3.8

## 练习
也是一遍就过啦～
``` java
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        while(sc.hasNextInt()){
            int N = sc.nextInt();
            if(N==0){
                break;
            }
            int i = 1,sum = 0;
            while(i<=N){
                sum += sc.nextInt();
                i++;
            }
            System.out.println(sum);
        }
        sc.close();
    }
}
```
