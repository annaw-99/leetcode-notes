### 217. Contains Duplicate
Solution: using a hash set to check if there are duplicate nums
```java
public boolean containsDuplicate(int[] nums) {
    Set<Integer> set = new HashSet<>();
    for(int num : nums){
        if(set.contains(num)){
            return true;
        }
        set.add(num);
    }
    return false;
}
```
Time Complexity = O(n)
Space Complexity = O(n)