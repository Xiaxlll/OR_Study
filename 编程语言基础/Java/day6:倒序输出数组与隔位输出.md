# 倒序输出数组与隔位输出

主要内容：数组的相关操作

## 目录
- 数组的概念和特点
- 数组的声明和定义、索引、数组元素的访问、以及数组的循环遍历。

## 数组的基础概念
数组是一种用于存储**相同数据类型**的元素的数据结构。

1、数组的特点：
- 固定大小：数组一旦声明，其大小通常是固定的，不能在运行时动态更改。就好比开设了一个30人的班级，班级大小已经固定，不能再改变班级的规模。
- 相同数据类型： 数组中的所有元素必须具有相同的数据类型，假设这个班都是男生或者都是女生，只能有一种性别存在。
- 连续存储： 数组的元素在内存中是连续存储的，班级里的同学按照顺序就坐，中间没有留空位。
- 下标访问： 数组中的元素通过下标（索引）进行访问，每个人都有一个学号，学号就是自己的座位，这个学号被称为索引，但是数组里的索引是从0开始的，也就是说，第一个元素的索引是0，第二个元素的索引是1，依次类推

2、数组的定义
* 数组的声明（此时还没有为数组分配存储空间）
  ``` java
  int[] nums; // 声明一个整数数组
  double scores[]; // 声明一个浮点数数组
  ```
  `dataType[] arrayName`或者为`dataType arrayName[]`
  - dataType表示数组元素的类型，比如int、double、char等。
  - arrayName是为数组指定的名称，类似于变量名称。
* 数组的初始化（使用`new`为数组分配内存）
  ``` java
  // 动态初始化
  int[] numbers = new int[3]; // 动态初始化一个包含3个整数的数组
  // 静态初始化
  int[] numbers = {1, 2, 3}; // 静态初始化一个包含初始值的整数数组
  ```
* 访问、修改、获取数组长度、输出
  ``` java
  int value = arr[2]; // 获取数组 arr 的第三个元素的值，即 3
  arr[0] = 100;  // 修改数组 arr 的第一个元素的值为 100
  int[] nums = {1, 2, 3};
  int length = nums.length; // 获取数组的长度（值为3）
  int[] numbers = {1, 2, 3, 4, 5};
  for (int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]);
  }
  ```
## `ArrayList`类

数组的长度是固定的，但是我们往往并不知道一组数据的大小，这个时候直接使用数组并不太满足需求，可以考虑使用ArrayList。在Java中，ArrayList 是 java.util 包中的一个类，可以在运行时对其动态添加和删除元素以满足我们的操作需要。
1、导入`ArrayList`类
``` java
import java.util.ArrayList;
```

2、创建一个 ArrayList（集合类只能存储对象而不是原始数据类型。）
``` java
ArrayList<Integer> nums = new ArrayList<Integer>();
```

3、添加数据元素`add`、获取数据元素`get`、删除数据元素`remove`、获取元素数量`size`、遍历
``` java
\\ 添加数据元素
nums.add(10);
nums.add(100);
nums.add(1000);
\\ 获取数据元素
int firstNumber = nums.get(0); // 获取第一个元素 1
\\ 删除数据元素`remove`
nums.remove(1); // 删除第二个元素
\\ 获取元素数量
int size = nums.size(); // 获取 ArrayList 的大小
\\ 遍历(增强型for循环)
for (Integer num : nums) {
    System.out.println(num);
}
```

## 增强型for循环(适用于ArrayList)
``` java
for (elementType element : collection) {
    // 在此处处理 element
}
```
- elementType 是元素的数据类型
- element 是在每次迭代中表示一个元素的变量
- collection 是要迭代的数组或其他的对象（比如后面讲到的集合）

## 练习
### 使用数组
约等于一遍过，只不过第一次把`String`输成了`Strings`
``` java
//import java.util.Arraylist;
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] nums = new int[n];
        for(int i = 0;i < n;i++){
            nums[i] = sc.nextInt();
        }
        // 倒序
        for(int i = 0;i < n;i++){
            System.out.println(nums[n-i-1]);
        }
        
        // 正序
        for(int i = 0;i < n;i++){
            if(i%2 == 0){
                System.out.println(nums[i]);
            }
            
        }
        sc.close();
    }
}
```
### 使用Arraylist
注意`ArrayList`类的大小写，`add`与`get`方法

``` java
import java.util.ArrayList;
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        ArrayList<Integer> nums = new ArrayList<Integer>();
        for(int i = 0;i < n;i++){
            nums.add(sc.nextInt());
        }
        for(int i = 0;i < n;i++){
            System.out.println(nums.get(n-i-1));
        }
        for(int i = 0;i < n;i++){
            if(i%2 == 0){
                System.out.println(nums.get(i));
            }
        }
        sc.close();
    }
}
```




  



