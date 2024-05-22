```java
// Just DP, what we need to care is only about the previous element.
// If it's positive then we add it into the current number
// For array that contains positive number only, the sum will be sum of all elements.
// For array that contains negative number only, the sum will the smallest number.
// For array that contains positive and negative number
// If there is a negative number between positive number, 
// if the negative number is smaller than the previous element then we will add it to next element.
// If the negative number is bigger than the previous element then we ignore it then to next.
// Time spend: 05:32
class Solution {
    public int maxSubArray(int[] nums) {
        int max = nums[0];

        for (int i = 1; i < nums.length; i++) {
            if (nums[i - 1] > 0) {
                nums[i] += nums[i-1];
            }
            max = Math.max(max, nums[i]);
        }

        return max;
    }
}
```