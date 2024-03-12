# 句子缩写

## 目录
- 字符大小的比较、字符运算、字符拼接
- ASCII码和Unicode码
- 字符大小写转换
- 字符串trim()方法
- StringBuilder的使用

## 字符大小的比较
每个字符都有一个唯一的 ASCII 编码值，表示它在 ASCII 字符集中的位置。在比较字符大小时，实际上是比较它们的 ASCII 编码值，大小写字母之间的差值是32。
### 大小写字母的转换

- toUpperCase(): 将小写字母转换成大写形式
- toLowerCase(): 将大写字母转换成小写形式
``` java
char a = 'a'; // 小写字符 'a'
char uppercaseChar = Character.toUpperCase(a); // 大写字符 'A'
```
``` java
char lowercaseChar = Character.toLowerCase('A'); // 将 大写字符 'A' 转换为小写字符
```
* ASCII码是一个比较早的、简单的字符编码标准，仅仅包含128个不同的字符，主要是一些基本的拉丁字母、数字、标点符号和回车、换行等，每个字符都有一个唯一的整数数值与之对应。
* 而 Unicode 码是一个更为广泛的字符编码标准，它包含了世界上几乎所有已知的字符、符号和文字，常见的Unicode编码包括UTF-8、UTF-16和UTF-32，它们使用不同数量的字节来表示字符。
总结来说，就是ASCII码表示的字符比较少，只包含一些常用的字符，而Unicode包含几乎所有语言的字符。

## 延伸`StringBuilder`
StringBuilder 也用于处理字符串，但为什么要使用StringBuilder而不是String?
这是因为如果你使用 String 进行字符串拼接，每次拼接都会创建一个新的字符串对象，这会产生大量的临时对象，会影响性能。而使用 StringBuilder 可以避免这个问题，StringBuilder 是可变的，它允许你在不创建新的字符串对象的情况下进行字符串的连接和修改，不会创建大量的临时对象，因此更高效。

## 练习
- 注意toUpperCase()的使用方式
- sc.nextLine();的作用，吸收回车符号
  <img width="654" alt="image" src="https://github.com/Xiaxlll/OR_Study/assets/77572858/1a374d3f-7039-42eb-8295-ab5e86df4998">
- 函数`trim()`，去掉字符串中的空白字符
  ``` java
  String line = sc.nextLine().trim();
  ```
-函数`toCharArray();`
 ``` java
 char[] arr = line.toCharArray(); // 将字符串转为字符数组，方便遍历
 ```
- 注意如何跳过首字母和空格的
### 错误答案
错误原因：没有使用.toCharArray();等函数，导致由string组成的数组中有很多空格
``` java
public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        sc.nextLine();
        while(n-- > 0){
            String s = sc.nextLine().trim();
            String[] word = s.split(" ");
            System.out.print(word[3]);
            /*
            for(int i = 0;i < word.length;i++){
                System.out.print(word[i].charAt(0););
            }
            //System.out.print(word[1].charAt(0));
            
            /*
            for(int i = 0;i < word.length;i++){
                char a = word[i].charAt(0);
                System.out.print(a);
            }
                
                /*
                if(a < 129){
                    System.out.print(Character.toUpperCase());
                }else{
                    System.out.print(a);
                }
                System.out.println();
                */
            }
            
        }
    }
```
## 我的答案
``` java
import java.util.Scanner;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        sc.nextLine();
        while(n-- > 0){
            String s = sc.nextLine().trim();
            char[] a = s.toCharArray();
            int i = 0;
            while(i < a.length){
                if(a[i] < 129){
                    System.out.print(Character.toUpperCase(a[i]));
                }else{
                    System.out.print(a[i]);
                }
                while(i < a.length && a[i]!=' '){
                    i++;
                }
                while(i < a.length && a[i]==' '){
                    i++;
                }
                
            }
            
            
            System.out.println();
        }
            
        }
    }
```

