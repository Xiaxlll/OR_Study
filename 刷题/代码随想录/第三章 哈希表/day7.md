# day7

## 454.四数相加II
* 注意：
  - 这道题的思路不好想qwq
  - 注意方法`map.getOrDefault`的使用
* 正确答案：
``` java
class Solution {
    public int fourSumCount(int[] nums1, int[] nums2, int[] nums3, int[] nums4) {
        int result = 0;
        Map<Integer,Integer> map = new HashMap<>();
        int n = nums1.length;
        for(int i : nums1){
            for(int j : nums2){
                map.put(i+j, map.getOrDefault(i+j,0)+1);
            }   
        }
        for(int i : nums3){
            for(int j : nums4){
                result = result + map.getOrDefault(0-i-j,0);
            }
        }
        return result;
    }
}
```

## 383. 赎金信
* 正确答案：
``` java
class Solution {
    public boolean canConstruct(String ransomNote, String magazine) {
        int[] hash = new int[26];
        for(char c : magazine.toCharArray()){
            hash[c - 'a']++;
        }
        for(char c : ransomNote.toCharArray()){
            if(hash[c - 'a'] == 0){
                return false;
            }else{
                hash[c - 'a']--;
            }
        }
        return true;
    }
}
```

## 15. 三数之和
* 注意：
  - 时刻注意去重
* 正确答案：
``` java
class Solution {
    public List<List<Integer>> threeSum(int[] nums) {
        List<List<Integer>> result = new ArrayList<>();
        Arrays.sort(nums);
        for(int i = 0;i < nums.length;i++){
            if(nums[i]>0){
                return result;
            }
            if(i>0 && nums[i] == nums[i-1]){
                continue;
            }
            int left = i+1;
            int right = nums.length-1;
            while(left < right){
                int sum = nums[i]+nums[left]+nums[right];
                if(sum<0){
                    left++;
                }else if(sum>0){
                    right--;
                }else{
                    result.add(Arrays.asList(nums[i],nums[left],nums[right]));
                    while(left<right &&nums[left]==nums[left+1]){
                    left++;
                }
                while(right>left&&nums[right]==(nums[right-1])){
                    right--;
                }
                    left++;
                    right--;
                }
                
            }
        }
        return result;
    }
}
```

## 18. 四数之和

