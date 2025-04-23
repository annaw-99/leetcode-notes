### 1. Two Sum
Solution: hash map
```java
public int[] twoSum(int[] nums, int target) {
    // key as num and value as the array index
    Map<Integer, Integer> map = new HashMap<>();

    for(int i = 0; i < nums.length; i++){
        int remain = target - nums[i];
        if(map.containsKey(remain)){
            return new int[]{map.get(remain), i};
        }
        map.put(nums[i], i);
    }
    return new int[]{0, 1};
}
```
Time Complexity = O(n)
Space Complexity = O(n)