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
> 18/02/2025
## 5 Subarray Sum divisible by k
```java
class Solution {
    public int subarraysDivByK(int[] nums, int k) {
        int c = 0;
        for(int i=0;i<nums.length;i++){
            int sum = 0;
            for(int j =i;j<nums.length;j++){
                sum+=nums[j];
                if(sum%k==0 ){
                    c++;
                }
            }
        }
        return c;
    }
}
```
> 19/02/2025
## 6 Majority Element
```java
class Solution {
    public int majorityElement(int[] nums) {
        int el = 0;
        int count = 0;
        for(int i:nums){
            if(count == 0) {
                count++;
                el = i;
            }
            else if(el == i) {
                count ++;
            }
            else{
                count--;
            }
        }
        int c1 = 0;
        for(int i :nums){
            if( i == el) c1++; 
        }
        if(c1 > nums.length/2) return el;
        return -1;
    }
}
```
## 7 Best Time to Sell Stocks
```java
class Solution {
    public int maxProfit(int[] arr) {
     int min = Integer.MAX_VALUE;
     int max = 0;
     for(int i:arr) {
        min = Math.min(min,i);
        max = Math.max(max,i-min);
     }
     return max;
    }
}
```
## 8 Rearrange Array Elements by Sign
```java
class Solution {
    public int[] rearrangeArray(int[] nums) {
        int[] arr = new int[nums.length];
        int pos = 0;
        int neg = 1;
        for(int i = 0;i<arr.length;i++){
            if(nums[i] > 0) {
                arr[pos] = nums[i];
                pos+=2;
            }  
            else{
                arr[neg] = nums[i];
                neg+=2;
            }
        }
        return arr;
    }
}
```
