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
  - 

## 202. 快乐数

## 1. 两数之和
