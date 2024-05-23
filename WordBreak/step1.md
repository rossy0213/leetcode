```java
// DP
// Create a boolean array with same length of given s
// Then foreach index of the DP, check if can we reach it
// Time complexity: O(N * M) -> N: length of given s, M: Number of unique lengths of the given word
// Space complexity: O(N + M + O) O: number of unique given word
// Time spend: 14:30
class Solution {
    public boolean wordBreak(String s, List<String> wordDict) {
        Set<String> wordSet = new HashSet<>();
        Set<Integer> wordLengthSet = new HashSet<>();
        for (String word : wordDict) {
            wordSet.add(word);
            wordLengthSet.add(word.length());
        }
        
        boolean[] dp = new boolean[s.length() + 1];
        dp[0] = true;

        for (int i = 0; i < dp.lenght; i++) {
            for (Integer wordLength : wordLengthSet) {
                int previousIndex = i - wordLength;
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