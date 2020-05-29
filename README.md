# Regular Expression Matching
## https://leetcode.com/problems/regular-expression-matching


# Implementation 1 : Recursive
```java
class Solution {
    public boolean isMatch(String s, String p) {
        if(p.isEmpty())
            return s.isEmpty();
        boolean firstMatch = (!s.isEmpty() && 
                              (s.charAt(0) == p.charAt(0) || p.charAt(0) == '.') );
           
        if(p.length() > 1 && p.charAt(1) == '*') {
            boolean excluding = isMatch(s, p.substring(2));
            boolean including = firstMatch && isMatch(s.substring(1), p);
            return excluding || including;    
        } else {
            return firstMatch && isMatch(s.substring(1), p.substring(1));
        }    
        
    }
}
```


# References :
1. https://leetcode.com/articles/regular-expression-matching
2. https://www.youtube.com/watch?v=bSdw9rJYf-I
