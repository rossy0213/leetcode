```java
// Create a memory to store the maxLength for each element
// In each step, check if there is a smaller number in the past 
// If yes, then count up, then compare with the max number we already have
// Time complexity: O(N**2)
// Space complexity: O(N) memory of the dp.
// Time spend: 08:30
class Solution {
    public int lengthOfLIS(int[] nums) {
        int[] dp = new int[nums.length];
        dp[0] = 1;
        int maxLength = 1;

        for (int i = 1; i < nums.length; i++) {
            dp[i] = 1;
            for (int j = 0; j < i; j++) {
                if (nums[j] < nums[i]) {
                    dp[i] = Math.max(dp[i], dp[j] + 1);
                }
            }
            maxLength = Math.max(maxLength, dp[i]);
        }

        return maxLength;
    }
}
```