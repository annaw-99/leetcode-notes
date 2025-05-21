### 347. Top K Frequent Elements
Solution: using bucket sort
```java
public int[] topKFrequent(int[] nums, int k) {
    Map<Integer, Integer> count = new HashMap<>();
    // the INDEX would be the COUNT
    // the list would include the numbers that have this count
    List<Integer>[] freq = new List[nums.length + 1];

    for(int i = 0; i <= nums.length; i++){
        freq[i] = new ArrayList<>();
    }

    for(int i = 0; i < nums.length; i++){
        count.put(nums[i], count.getOrDefault(nums[i], 0) + 1);
    }

    // Map.Entry<Integer, Integer> is a method to loop through a
    // map and get both the key and value
    for(Map.Entry<Integer, Integer> entry : count.entrySet()){
        freq[entry.getValue()].add(entry.getKey());
    }

    int[] result = new int[k];
    int index = 0;

    for(int i = freq.length - 1; i >= 0 && index < k; i--){
        for(int n : freq[i]){
            result[index] = n;
            if(index == k){
                return result;
            }
            index++;
        }
    }
    return result;
}
```
Time Complexity = O(n) <br>
Space Complexity = O(n)