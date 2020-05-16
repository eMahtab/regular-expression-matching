# Regular Expression Matching
## https://leetcode.com/problems/regular-expression-matching


# Implementation 1 : Recursive
```java
class Solution {
    public boolean isMatch(String text, String pattern) {
        if (pattern.isEmpty()) return text.isEmpty();
        boolean first_match = (!text.isEmpty() &&
                               (pattern.charAt(0) == text.charAt(0) || pattern.charAt(0) == '.'));

        if (pattern.length() >= 2 && pattern.charAt(1) == '*'){
            return (isMatch(text, pattern.substring(2)) ||
                    (first_match && isMatch(text.substring(1), pattern)));
        } else {
            return first_match && isMatch(text.substring(1), pattern.substring(1));
        }
    }
}
```


# References :
1. https://leetcode.com/articles/regular-expression-matching
2. https://www.youtube.com/watch?v=bSdw9rJYf-I
