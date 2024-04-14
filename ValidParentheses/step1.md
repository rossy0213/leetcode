```java
// Use stack
// When we find the left side bracket, put it into stack
// If we find the right side bracket, then pop 1 bracket from the stack
// If it's pair then go next, if not return false
// Time complexity: O(N) N -> length of s
// Space complexity: O(N/2) -> O(N) for the stack
// Time spend: 12:48
class Solution {
    public boolean isValid(String s) {
        Set<Character> leftBrackets = Set.of('(', '[', '{');
        Map<Character, Character> bracketPair = Map.of(
            ')', '(',
            ']', '[',
            '}', '{'
        );

        Deque<Character> stack = new LinkedList<>();
 
        for (int i = 0; i < s.length(); i++) {
            if (leftBrackets.contains(s.charAt(i))) {
                stack.push(s.charAt(i));
                continue;
            }
            if (stack.isEmpty()) {
                return false;
            }

            Character leftBracket = stack.pop();
            if (leftBracket != bracketPair.get(s.charAt(i))) {
                return false;
            }
        }
        
        if (!stack.isEmpty()) {
            return false;
        }

        return true;
    }
}
```