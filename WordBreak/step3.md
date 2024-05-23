```java
// Time spend: 03:59 
class Solution {
    public boolean wordBreak(String s, List<String> wordDict) {
        Set<String> wordSet = new HashSet<>();
        Set<Integer> wordLengthSet = new HashSet<>();
        for (String word : wordDict) {
            wordSet.add(word);
            wordLengthSet.add(word.length());
        }

        int l = s.length();
        var dp = new boolean[l + 1];
        dp[0] = true;
        for (int i = 1; i <= l; i++) {
            for (int length : wordLengthSet) {
                var previousIndex = i - length;
                if (previousIndex >= 0 && dp[previousIndex] && wordSet.contains(s.substring(previousIndex, i))) {
                    dp[i] = true;
                    break;
                }
            }
        }

        return dp[l];
    }
}
```

```java
// Time spend: 02:59
class Solution {
    public boolean wordBreak(String s, List<String> wordDict) {
        Set<String> wordSet = new HashSet<>();
        Set<Integer> wordLengthSet = new HashSet<>();
        for (String word : wordDict) {
            wordSet.add(word);
            wordLengthSet.add(word.length());
        }

        int l = s.length();
        var dp = new boolean[l + 1];
        dp[0] = true;
        for (int i = 1; i <= l; i++) {
            for (int length : wordLengthSet) {
                var previousIndex = i - length;
                if (previousIndex >= 0 && dp[previousIndex] && wordSet.contains(s.substring(previousIndex, i))) {
                    dp[i] = true;
                    break;
                }
            }
        }

        return dp[l];
    }
}
```

```java
// Time spend: 02:40
class Solution {
    public boolean wordBreak(String s, List<String> wordDict) {
        Set<String> wordSet = new HashSet<>();
        Set<Integer> wordLengthSet = new HashSet<>();
        for (String word : wordDict) {
            wordSet.add(word);
            wordLengthSet.add(word.length());
        }

        int l = s.length();
        boolean[] dp = new boolean[l + 1];
        dp[0] = true;
        for (int i = 1; i <= l; i++) {
            for (int length : wordLengthSet) {
                int previousIndex = i - length;
                if (previousIndex < 0 || !dp[previousIndex]) {
                    continue;
                }
                if (wordSet.contains(s.substring(previousIndex, i))) {
                    dp[i] = true;
                    break;
                }
            }
        }

        return dp[l];
    }
}
```