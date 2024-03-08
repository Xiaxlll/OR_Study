# A+B问题3

## 练习
一次就过啦
``` java
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        while(sc.hasNextInt()){
            int a = sc.nextInt();
            int b = sc.nextInt();
            if((a!=0)||(b!=0)){
                System.out.println(a+b);
            }else{
                break;
            }
        }
        sc.close();
    }
}
```
