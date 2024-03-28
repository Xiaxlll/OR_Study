# 洗盘子

## 目录
* 栈的基本概念（空栈、栈顶、栈底）和特点（先入后出）
* 入栈、出栈、获取栈顶元素和判断栈是否为空栈等基本操作
* `Stack`类的使用

## 栈的基本介绍
* 后进先出LIFO
* 栈顶，栈低，空栈
<img width="555" alt="image" src="https://github.com/Xiaxlll/OR_Study/assets/77572858/16944def-ad46-4dea-813a-e3fe3c41c271">

## 栈的操作

1. 导入栈（`Stack`）
  ``` java
  import java.util.Stack; // 导入 Java 标准库的 Stack
  ```
2. 创建一个栈对象
  ``` java
  Stack<Integer> stack = new Stack<>();  // 创建一个栈对象
  ```
3. 栈的常用操作
  * isEmpty(): 判断栈是否为空栈，如果为空栈返回true， 否则或者false
  * push(): 进栈操作，将新的元素放入到栈中，新的元素成为栈顶元素。
  * pop()： 出栈操作，栈顶元素从栈中离开, 并且返回栈顶元素。
  * peek(): 获取栈顶元素，但是不会移除它。
  * size(): 获取栈的长度，即栈中元素的数量。
   ``` java
   stack.push(1);
   stack.push(10);
   stack.push(100); // 往栈中添加元素，现在栈底元素是1，栈顶元素是100

   stack.pop(); // 移除栈顶元素100，新的栈顶元素是10

   int topNumber = stack.peek(); // 获取栈顶元素10，但是不会移除

   boolean isEmpty = stack.isEmpty(); // 如果栈为空，返回true；否则返回false

   int stackSize = stack.size(); // 获取栈的长度（元素数量）
   ```
## 练习

* 注意：pop的时候注意判断栈不为空

``` java
import java.util.Stack;
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        while(sc.hasNextInt()){
            Stack<Integer> stack = new Stack<>();
            int n = sc.nextInt();
            while(n-- > 0){
                int num = sc.nextInt();
                stack.push(num);
            }
            int m = sc.nextInt();
            while(m-- > 0){
                int act = sc.nextInt();
                if(act == 1){
                    if(!stack.isEmpty()){
                        stack.pop();
                    }
                }else if(act == 2){
                    int wash = sc.nextInt();
                    stack.push(wash);
                }
                
            }
            if(stack.size()==0){
                System.out.println("All the dishes have been washed.");
            }else{
                System.out.println(stack.peek()); 
            }
        }
        sc.close();
    }
}
```
