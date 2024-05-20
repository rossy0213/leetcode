```java
// After checking the solutions tab...What's an elegant solution
// Time complexity: O(NlogN)
// Time spend: 07:30
class Solution {
    public int lengthOfLIS(int[] nums) {
        int[] tails = new int[nums.length];
        int maxLength = 0;

        for (int num : nums) {
            int l = 0;
            int r = maxLength;
            while (l != r) {
                int mid = l + (r - l) / 2;
                if (tails[mid] < num) {
                    l = mid + 1;
                    continue;
                }
                r = mid;
            }
            tails[l] = num;
            if (l == maxLength) {
                maxLength++;
            }
        }

        return maxLength;
    }
}
```