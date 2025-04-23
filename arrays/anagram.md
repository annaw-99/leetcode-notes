### 242. Valid Anagram
Solution #1: sorting each string
```java
public boolean isAnagram(String s, String t) {
    if(s.length() != t.length()){
        return false;
    }

    // O(nlogn)
    char[] sSort = s.toCharArray();
    char[] tSort = t.toCharArray();

    Arrays.sort(sSort);
    Arrays.sort(tSort);

    for(int i = 0; i < sSort.length; i++){
        if(sSort[i] != tSort[i]){
            return false;
        }
    }
    return true;
}
```
Time Complexity = O(nlogn + mlogm)
Space Complexity = O(n + m)

Solution #2: hash map
```java
public boolean isAnagram(String s, String t) {
    if(s.length() != t.length()){
        return false;
    }

    Map<Character, Integer> mapS = new HashMap<>();
    Map<Character, Integer> mapT = new HashMap<>();

    for(int i = 0; i < s.length(); i++){
        mapS.put(s.charAt(i), mapS.getOrDefault(s.charAt(i), 0) + 1);
        mapT.put(t.charAt(i), mapT.getOrDefault(t.charAt(i), 0) + 1);
    }

    return mapS.equals(mapT);
}
```
Time Complexity = O(n + m)
Space Complexity = O(1)