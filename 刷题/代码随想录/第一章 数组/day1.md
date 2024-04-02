# day1

## 704 二分查找
* 知识点：
  - 二分查找的前提条件：数组为**有序数组**，**无重复元素**。
  - 时间复杂度 O(log n)
* 注意：
  - 得到数组长度的函数`nums.length`，没有括号！
  - 边界条件（左闭右闭or左闭右开）
 
* 第一个答案（超时长了TAT）
  <img width="691" alt="image" src="https://github.com/Xiaxlll/OR_Study/assets/77572858/c9a3d98a-d0dd-49c3-b158-f29e632e0b99">

  ``` java
  class Solution {
    public int search(int[] nums, int target) {
        int s = 0;
        int l = nums.length - 1;
        int mid;
        while(s <= l){
            mid = (s + l) / 2;
            if(nums[mid] == target){
                return mid;
            }else if(nums[mid] > target){
                l = mid;
            }else{
                s = mid;
            }
        }
        return -1;
    }
  }
  ```
* 正确答案：
  ``` java
  class Solution {
    public int search(int[] nums, int target) {
        int s = 0;
        int l = nums.length - 1;
        int mid;
        while(s <= l){
            mid = (s + l) / 2;
            if(nums[mid] == target){
                return mid;
            }else if(nums[mid] > target){
                l = mid - 1;
            }else{
                s = mid + 1;
            }
        }
        return -1;
    }
  }
  ```
## 27 移除元素
* 知识点：双指针法
* 答案（一遍过！）
  ``` java
  class Solution {
    public int removeElement(int[] nums, int val) {
        int flag = 0;
        for(int i = 0;i < nums.length;i++){
            if(nums[i]==val){
                flag++;
                continue;
            }
            nums[i-flag] = nums[i];
        }
        return nums.length-flag;
    }
  }
  ```
