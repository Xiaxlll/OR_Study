# day2

## 977 有序数组的平方（双指针）
* 注意：
  - 数组的定义`int[] answer = new int[6];`
  - 注意理解题意：当题目给的数列中有-3和3时，答案里需有两个9
* 正确答案：
  ``` java
  class Solution {
    public int[] sortedSquares(int[] nums) {
        int[] answer = new int[nums.length];
        int k = nums.length-1;
        int i = 0;
        int j = nums.length-1;
        while(k>=0 && i<=j){
            if(nums[j]*nums[j] >= nums[i]*nums[i]){
                answer[k--] = nums[j]*nums[j];
                j--;
            }else{
                answer[k--] = nums[i]*nums[i];
                i++;
            }
        }
        return answer;
    }
  }
  ```
## 209 长度最小的子数组（滑动窗口）
* 注意：
  - `java`必须要初始化
  - 滑动窗口法的最右边一直在增加
  - 当需要使用一个无穷大的值的时候，可以使用`Integer.MAX_VALUE`
  - 

## 59 螺旋矩阵（2）
