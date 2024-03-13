# 位置互换

## Java中的方法
Java 中方法参数是按值传递的，也就是说当你将一个变量传递给方法时，实际上是将该变量的值传递给了方法。这意味着方法内部对参数的任何修改都不会影响到调用方法的地方的原始变量。
<img width="542" alt="image" src="https://github.com/Xiaxlll/OR_Study/assets/77572858/c6aa0ad6-ed12-4022-b3bb-64574796b202">
<img width="544" alt="image" src="https://github.com/Xiaxlll/OR_Study/assets/77572858/d92883b2-9c0b-4430-895d-a568e087802a">
例子：
``` java
private static void swap(char[] chs, int j, int i) {
    char tmp = chs[j];
    chs[j] = chs[i];
    chs[i] = tmp;
}
```
## 练习
注意：
* 方法`toCharArray()`
* 在`int n = sc.nextInt();`后使用`sc.nextLine();`来吸收多余的换行符号


``` java
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        while(sc.hasNextInt()){
            int n = sc.nextInt();
            sc.nextLine();
            while(n-- > 0){
                String s = sc.nextLine().trim();
                char[] w = s.toCharArray();
                int j = 0;
                while(j < w.length){
                    char temp = w[j];
                    w[j] = w[j + 1];
                    w[j + 1] = temp;
                    System.out.print(w[j]);
                    System.out.print(w[j+1]);
                    j += 2;
                }
                System.out.print("\n");
            }
        }
    }
}
```
