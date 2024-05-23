```java
// Time spend: 05:39
class Solution {
    public boolean wordBreak(String s, List<String> wordDict) {
        Set<String> wordSet = new HashSet<>();
        Set<Integer> wordLengthSet = new HashSet<>();

        for (String word : wordDict) {
            wordSet.add(word);
            wordLengthSet.add(word.length());
        }

        var dp = new boolean[s.length() + 1];
        dp[0] = true;

        for (int i = 1; i <= s.length(); i++) {
            for (int wordLength : wordLengthSet) {
                var previousIndex = i - wordLength;
                if (previousIndex >= 0 && dp[previousIndex] && wordSet.contains(s.substring(previousIndex, i))) {
                    dp[i] = true;
                    break;
                }
            }
        }

        return dp[s.length()];
    }
}
```