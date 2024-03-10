# 摆平积木

## 练习
- 注意ArrayList的定义
- 注意要用hasNextInt()来是否有新的例子
- 注意输出格式

``` java
import java.util.ArrayList;
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        while(sc.hasNextInt()){
            int n = sc.nextInt();
            if(n==0){
                break;
            }
            int sum = 0;
            ArrayList<Integer> nums = new ArrayList<Integer>();
            for(int i = 0;i < n;i++){
                nums.add(sc.nextInt());
                sum+=nums.get(i);
            }
            int height = sum/n;
            int answer = 0;
            for(int i = 0;i < n;i++){
                if(nums.get(i)>height){
                    answer = answer + nums.get(i)-height;
                }
            }
            System.out.println(answer);
            System.out.println();
        }
        sc.close();
    }
}
```
<img width="662" alt="image" src="https://github.com/Xiaxlll/OR_Study/assets/77572858/ab6dc09d-5dbf-48b8-babd-bd09f138fbae">

