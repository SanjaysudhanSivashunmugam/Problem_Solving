# Basic Array Problems
> 13/2/2025
## 1 Product of Array Except Self
```java
class Solution {
    public int[] productExceptSelf(int[] nums) {
      int p = 1;
      int arr[] = new int[nums.length];
      for(int i=0;i<nums.length;i++){
        arr[i] = p;
        p = p*nums[i];
      }
      p = 1;
      for(int i = nums.length-1;i>=0;i--){
        arr[i] = p* arr[i];
        p = p*nums[i];
      }
      return arr;
    }
}
```
## 2 Two Sum
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer, Integer> map = new HashMap<>();
        for(int i = 0; i < nums.length; i++) {
            int req = target - nums[i];
            if(map.containsKey(req)){
                return new int[] {map.get(req), i};
            }
            map.put(nums[i] , i);
        }
        return new int []{};
    }
}
```
## 3
