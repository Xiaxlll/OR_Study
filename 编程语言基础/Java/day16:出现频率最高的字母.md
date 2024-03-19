# 出现频率最高的字母
本节学习：用数组来表示哈希表
## 哈希表的基本概念
* 哈希表是根据关键码`key`的值而直接进行访问的数据结构。
* 哈希表的作用是快速判断一个元素是否出现在集合里，它的核心思想是在关键码和存储位置之间建立一个确定的对应关系f, 使得每个关键字key对应一个存储位置，而这个对应关系，称之为散列函数（哈希函数）。（数组就是一种哈希表）
* 哈希表来解决问题的时候，一般选择以下三种数据结构。
  - 数组
  - set集合
  - map映射
## 哈希表
哈希表可以将其比喻为一个大抽屉，抽屉里面有很多小格子。每个格子可以用来存放一些东西。
* 抽屉编号： 抽屉有编号，这个编号就是数据的`key`，我们通过这个`key`来找到对应的抽屉。
* 散列函数： 哈希表使用一种特殊的函数(哈希函数），来决定数据应该放在哪个抽屉里。这个函数将数据的名字`key`转换成一个数字，然后根据这个数字来选择一个抽屉。
* 抽屉里的物品： 在每个抽屉里，可以放一些东西，这些东西就是我们要存储的数据。
* 解决冲突： 有时候不同的`key`经过散列函数后可能会得到相同的编号，这就是冲突。哈希表有特定的方法来处理这些冲突。
* 查找： 当我们需要找到某个数据时，哈希表可以通过名字`key`快速地找到对应的抽屉，然后取出里面的数据，就像从抽屉中拿出东西一样。

## 练习
* 方法在什么时候需要加`static`
  当一个方法或者变量需要初始化加载，或者是经常被调用的时候可以加上static。用static修饰的方法可以用类名直接调用，不用的一定要先实例化一个对象然后才可以调用。//      `public static`表明这是一个公共静态方法
* 函数`.toCharArray()`
* 注意函数的调用
### 我的答案
``` java
import java.util.*;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        for(int i = 0;i < n; i++){
            String input = sc.next();
            char fruqentchar = findFrequencyChar(input);
            System.out.println(fruqentchar);
        }
        sc.close();
    }

    public static char findFrequencyChar(String input){
        int[] frequency = new int[26];
        for(char c:input.toCharArray()){
            frequency[c-'a']++;
        }
        char highfrequncy = 'a';
        int maxfrequency = frequency[0];
        
        for(int i = 1;i < 26; i++){
            if(frequency[i] > maxfrequency){
                maxfrequency = frequency[i];
                highfrequncy = (char)('a'+i);
            }
        }
        return highfrequncy;
        
    }
}
```
