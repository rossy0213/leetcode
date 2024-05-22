```java
// Time spend: 00:53
class Solution {
    public int maxSubArray(int[] nums) {
        int max = nums[0];

        for (int i = 1; i < nums.length; i++) {
            if (nums[i - 1] > 0) {
                nums[i] += nums[i - 1];
            }

            max = Math.max(max, nums[i]);
        }

        return max;
    }
}
```

```java
// Time spend: 00:45
class Solution {
    public int maxSubArray(int[] nums) {
        int max = nums[0];

        for (int i = 1; i < nums.length; i++) {
            if (nums[i - 1] > 0) {
                nums[i] += nums[i - 1];
            }

            max = Math.max(max, nums[i]);
        }

        return max;
    }
}
```

```java
// Time spend: 00:50
class Solution {
    public int maxSubArray(int[] nums) {
        int max = nums[0];

        for (int i = 1; i < nums.length; i++) {
            if (nums[i - 1] > 0) {
                nums[i] += nums[i - 1];
            }
            max = Math.max(max, nums[i]);
        }

        return max;
    }
}
```