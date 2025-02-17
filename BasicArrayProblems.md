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
> 17/02/2025
## 3 Print all subarray
```java
public class Main {
    public static void printAllSubarrays(int[] arr) {
        int n = arr.length;
        for(int i = 0; i < n; i++) {
            for(int j = i; j < n; j++) {
                for(int k = i; k <= j; k++){
                    System.out.print(arr[k] + " ");
                }
                System.out.println();
            }
        }
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 2 , 9, 0, 2};
        printAllSubarrays(arr);
    }
}
```
## 4 Maximum SubArray
```java
public class Main {
    public static void MaxSubarray(int[] arr) {
        int n = arr.length;
        int max = arr[0],sum = 0;
        for(int i = 0; i < n; i++) {
             sum+=arr[i];
             max = Math.max(sum,max);
             if(sum < 0) {
                 sum = 0;
             }
        }
         System.out.println(max);
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 2 , 9, 0, 2};
        MaxSubarray(arr);
    }
}
```
