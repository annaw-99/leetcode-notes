### 128. Longest Consecutive Sequence
Solution: using a hash set to 
```java
public int longestConsecutive(int[] nums) {
    HashSet<Integer> set = new HashSet<>();
    // O(1) look ups
    for(int num : nums){
        set.add(num);
    }

    int max = 0;
    for(int num : set){
        // if num - 1 is not in the set, 
        // then num must be the beginning of a new sequence
        if(!set.contains(num - 1)){
            int length = 1;
            while(set.contains(num + length)){
                length++;
            }
            max = Math.max(max, length);
        }
    }
    return max;
}
```
Time Complexity = O(n) <br>
Space Complexity = O(n)