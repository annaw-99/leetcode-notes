### 271. Encode and Decode Strings
Solution: 
```java
public class Codec {

    // Encodes a list of strings to a single string.
    public String encode(List<String> strs) {
        StringBuilder encoded = new StringBuilder();

        for(String str : strs){
            encoded.append(str).append(":;!");
        }

        return encoded.toString();
    }

    // Decodes a single string to a list of strings.
    public List<String> decode(String s) {
        List<String> decoded = new ArrayList<>();
        int i = 0;
        StringBuilder temp = new StringBuilder();
        while(i < s.length() - 2){
            if(s.charAt(i) == ':' && s.charAt(i + 1) == ';' && s.charAt(i + 2) == '!'){
                decoded.add(temp.toString());
                temp = new StringBuilder();
                i += 2;
            } else {
                temp.append(s.charAt(i));
            }
            i++;
        }
        return decoded;

    }
}
```
Time Complexity =  O(n) (both)<br>
Space Complexity = O(n) (both)