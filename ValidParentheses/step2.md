```java
class Solution {
    public boolean isValid(String s) {
        Map<Character, Character> bracketPair = Map.of(
                ')', '(',
                ']', '[',
                '}', '{'
        );

        Deque<Character> foundLeftBrackets = new LinkedList<>();
        for (int i = 0; i < s.length(); i++) {
            Character c = s.charAt(i);
            if (bracketPair.containsKey(c)) {
                if (foundLeftBrackets.isEmpty()) {
                    return false;
                }
                if (foundLeftBrackets.pop() != bracketPair.get(c)) {
                    return false;
                }
                continue;
            }
            foundLeftBrackets.push(c);
        }

        // return foundLeftBrackets.isEmpty();
        if (!foundLeftBrackets.isEmpty()) {
            return false;
        }

        return true;
    }
}
```