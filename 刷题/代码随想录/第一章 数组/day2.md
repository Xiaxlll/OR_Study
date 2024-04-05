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
  - 在判断大小的时候可以使用库函数`Math.min`或者`Math.max`
* 思路：
  - `j`不断增加，在`j`增加的每一个循环中，若`sum>=target`,`i`不断增加，直到`sum<target`
* 正确答案：
  ``` java
  class Solution {
    public int minSubArrayLen(int target, int[] nums) {
        int i = 0;
        int sum = 0;
        int result = Integer.MAX_VALUE;
        for(int j = 0;j < nums.length;j++){
            sum += nums[j];
            while(sum >= target){
                result = Math.min(j-i+1, result);
                sum -= nums[i++];
            }
        }
        return result == Integer.MAX_VALUE ? 0 : result;
    }
  }
  ```

## 59 螺旋矩阵（2）
* 注意：
  - 判断循环次数
  - 开始位置
  - 填充数字

* 正确答案
  ``` java
  class Solution {
    public int[][] generateMatrix(int n) {
        int[][] matrix = new int[n][n];
        int loop = 0;
        int start = 0;
        int count = 1;
        int i = 0;
        int j = 0;
        while(loop++ < n/2){
            // 从左往右
            for(j = start;j<n-loop;j++){
                matrix[start][j] = count++;
            }
            // 从上往下
            for(i = start;i< n-loop;i++){
                matrix[i][n-loop] = count++;
            }
            // 从右往左
            for(j = n-loop;j>= loop;j--){
                matrix[i][j] = count++;
            }
            // 从下往上
            for(i = n-loop;i>= loop;i--){
                matrix[i][j] = count++;
            }
            start++;
        }
        if(n%2==1){
            matrix[start][start] = count;
        }
        return matrix;
    }
  }
  ```
