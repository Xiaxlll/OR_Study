# 开房门

##目录
* `map`的概念和特点
* `map`的创建、添加、删除、查找等基本操作
* `HashMap`的常用方法
* 遍历`HashMap`的键值对

## `map`的基本介绍
我们常常把`map`称之为映射，就是将一个元素（通常称之为`key`键）与一个相对应的值（通常称之为`value`）关联起来
* `key`与`value`是一一对应的
<img width="551" alt="image" src="https://github.com/Xiaxlll/OR_Study/assets/77572858/b1294a56-c494-4ac9-8d63-a721ab778cb0">

## `HashMap`的使用
`Map`接口，实现类包括 `HashMap`、`TreeMap`、`LinkedHashMap`
1. 导入`HashMap`
   ``` java
   import java.util.Map; // 引入 Map 接口
   import java.util.HashMap; // 引入 HashMap 实现类
   ```
2. 创建一个`HashMap`实例
   需要指定键的类型和值的类型，键为`String`类型，而值为`Integer`类型。
   ``` java
   // 创建一个HashMap实例，用于表示学生分数
   Map<String, Integer> studentScores = new HashMap<>();
   ```
3. `map`结构还提供了一些常见方法方便使用：
   * put(key, value)：将指定的键和值添加到map中，如果键已存在，则替换对应的值。
   * get(key)：根据key获取对应的值value。
   * remove(key)：根据key移除对应的键值对。
   * containsKey(key)：检查map中是否包含key键。
   * containsValue(value)：检查map中是否包含value值。
   * keySet()：返回包含所有键的集合。
   * values()：返回包含所有值的集合。
   * entrySet()：返回包含所有键值对的集合。
   ``` java
   // 创建一个HashMap实例
   Map<String, Integer> studentScores = new HashMap<>();

   // 添加键值对到映射
   studentScores.put("zs", 100);
   studentScores.put("ls", 97);
   studentScores.put("Mike", 99);

   // 获取键对应的值
   int score = studentScores.get("Mike");

   // 移除zs对应的键值对
   studentScores.remove("zs");
   ```
## 练习
``` java
import java.util.Scanner;
import java.util.Map;
import java.util.HashMap;

public class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        while(sc.hasNextInt()){
            int s = sc.nextInt();
            while(s-- > 0){
                int n = sc.nextInt();
                Map<Integer, Integer> map = new HashMap<>();
                while(n-- > 0){
                    int k = sc.nextInt();
                    int d = sc.nextInt();
                    map.put(d, k);
                }
                int x = sc.nextInt();
                if(map.containsKey(x)){
                    System.out.println(map.get(x));
                }else{
                    System.out.println("Can't open the door.");
                }
            }
        }
        sc.close();
    }
}
```
