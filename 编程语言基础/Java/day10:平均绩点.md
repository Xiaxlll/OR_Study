# 平均绩点

字符串的基本使用

## 目录

- 字符串的声明和初始化
- 字符串的常见操作
- 字符串的特点
- 读取字符串输入
- `equals`方法
- 字符串格式化输出`format`和`printf`
- 字符串的遍历
- `flag`编程思想
- `switch-case`
- 浮点数运算

## `String`的使用
1. 声明和初始化
   - 创建字符串变量
     ``` java
     String name = "Hello, Java";
     ```
   - 创建字符串对象
     ``` java
     String message = new String("Hello");
     ```
3. 操作
   - 字符串拼接`+`
     注意：在Java中，`String`类的对象是不可变的，所以每次字符串拼接都会创建一个新的字符串对象
     ``` java
     string s1 = "hello";
     string s2 = "world";
     string s3 = s1 + " " + s2; // 对字符串进行连接，拼接之后的字符串是"hello world", 中间加了空格
     ```
   - 字符串长度`length()`
     ``` java
     int len = s1.length(); // 字符串的长度即字符串中字符的个数，"hello"的长度为5
     ```
   - 字符串比较`equals()`
     ``` java
     if(sex.equals("男")){
     }
     ```
   - 字符串索引`charAt()`
     字符串中的字符可以通过索引访问，索引从 0 开始。
     ``` java
     char c1 = s1.charAt(0);
     ```
   - 字符串切割和拆分
     可以使用 split() 方法将一个字符串根据指定的分隔符拆分成字符串数组。
     ``` java
     String[] parts = s3.split(" ") // 会将字符串根据空格拆分为多个部分
     ```
   - 字符串格式化`String.format()` 方法或 `printf()`
   - 字符串查找和替换 `indexOf()` 方法 or `replace()` 方法
   - 读取下一行字符串`nextLine()`
     ``` java
     String inputLine = scanner.nextLine();
     ```
     
## 扩展：`Switch-Case`
``` java
switch (expression) {
    case value1:
        // 与 value1 匹配时执行的代码
        break;
    case value2:
        // 与 value2 匹配时执行的代码
        break;
    // 可以有多个 case 分支
    default:
        // 如果没有匹配的 case 分支，执行 default 分支
}
```
* 注意：`case` 中不能使用变量，而不是一个确定的值
