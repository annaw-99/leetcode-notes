### 347. Top K Frequent Elements
Solution: use bucket sort
```java
public int[] topKFrequent(int[] nums, int k) {
    Map<Integer, Integer> count = new HashMap<>();
    // the index would be the count
    // the list would include the numbers that have this count
    List<Integer>[] freq = new List[nums.length + 1];

    for(int i = 0; i <= nums.length; i++){
        freq[i] == new ArrayList<>();
    }

    for(int i = 0; i < nums.length; i++){
        count.put(nums[i], count.getOrDefault(nums[i], 0) + 1);
    }

    for(Map.Entry(Integer, Integer) entry : count.entrySet()){
        
    }

    int[] result = new int[k];
    int index = 0;

    for(int i = nums.lengt)
}
```
Time Complexity = O(n) <br>
Space Complexity = O(n)