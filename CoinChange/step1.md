```java
// DP
// Create list to keep the min number of coins needs foreach amount
// Time complexity: O(N * M) N: amount, M: number of coins
// Space complexity: O(N) memory for dp array
// Time spend: 03:45
class Solution {
    public int coinChange(int[] coins, int amount) {
        int[] dp = new int[amount + 1];

        for (int i = 1; i <= amount; i++) {
            dp[i] = 10001;
            for (int coin : coins) {
                if (i - coin >= 0) {
                    dp[i] = Math.min(dp[i], dp[i - coin] + 1);
                }
            }
        }

        return dp[amount] == 10001 ? -1 : dp[amount];
    }
}
```