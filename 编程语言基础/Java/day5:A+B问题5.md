# A+B问题5
这一小节也不需要用到新的知识

## 练习
注意格式
``` java
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        while(sc.hasNextInt()){
            int N = sc.nextInt();
            //int i = 1;
            while(N-- > 0){
                int M = sc.nextInt();
                //int j = 1;
                int sum = 0;
                while(M-- > 0){
                    sum += sc.nextInt();
                    //j++;
                }
                System.out.println(sum);
                //System.out.println();
                if(N>0){
                    System.out.println();
                }
            }
            
        }
        sc.close();
    }
}
```
