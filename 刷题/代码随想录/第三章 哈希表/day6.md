# day6

## 242.有效的字母异位词
* 注意：
  - 字符串的常用函数`s.charAt(i)`
  - 注意字符串长度的调用`s.length()`,这里与数组是不同的
* 正确答案：
``` java
class Solution {
    public boolean isAnagram(String s, String t) {
        int[] hash = new int[26];
        for(int i = 0;i<s.length();i++){
            hash[s.charAt(i)-'a']++;
        } 
        for(int i = 0;i<t.length();i++){
            hash[t.charAt(i)-'a']--;
        }
        for(int i = 0;i<26;i++){
            if(hash[i]!=0){
                return false;
            }
        }
        return true;
    }
}
```
## 349. 两个数组的交集
* 注意：
  - 使用`ArrayList`，然后最终再转化为数组并返回
* 答案：
``` java
import java.util.HashSet;
import java.util.Set;

class Solution {
    public int[] intersection(int[] nums1, int[] nums2) {
        if (nums1 == null || nums1.length == 0 || nums2 == null || nums2.length == 0) {
            return new int[0];
        }
        Set<Integer> set1 = new HashSet<>();
        Set<Integer> resSet = new HashSet<>();
        //遍历数组1
        for (int i : nums1) {
            set1.add(i);
        }
        //遍历数组2的过程中判断哈希表中是否存在该元素
        for (int i : nums2) {
            if (set1.contains(i)) {
                resSet.add(i);
            }
        }
      
        //方法1：将结果集合转为数组

        return resSet.stream().mapToInt(x -> x).toArray();
        
        //方法2：另外申请一个数组存放setRes中的元素,最后返回数组
        int[] arr = new int[resSet.size()];
        int j = 0;
        for(int i : resSet){
            arr[j++] = i;
        }
        
        return arr;
    }
}
```

## 202. 快乐数
* 注意：
  - 由于不确定元素的个数，可以使用`HashSet`;
* 正确答案：
``` java
class Solution {
    public boolean isHappy(int n) {
        Set<Integer> set = new HashSet<>();
        int num = n;
        while(true){
            int sum = 0;
            while(num!=0){
                sum+=(num%10*(num%10));
                num = num/10;
            }
            if(sum==1){
                return true;
            }
            if(set.contains(sum)){
                return false;
            }else{
                set.add(sum);
            }
            num = sum;
        }
    }
}
```

## 1. 两数之和
