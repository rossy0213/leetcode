```java
// Time spend: 04:20
class Solution {
    public int lengthOfLIS(int[] nums) {
        List<Integer> increasingNums = new ArrayList<>();
        increasingNums.add(nums[0]);

        for (int i = 1; i < nums.length; i++) {
            if (nums[i] > increasingNums.get(increasingNums.size() - 1)) {
                increasingNums.add(nums[i]);
                continue;
            }
            int low = Collections.binarySearch(increasingNums, nums[i]);
            if (low < 0) {
                // bit否定?
                low = -(low + 1);
            }
            increasingNums.set(low, nums[i]);
        }

        return increasingNums.size();
    }
}
```

```java
// Time spend: 03:30
class Solution {
    public int lengthOfLIS(int[] nums) {
        List<Integer> increasingNums = new ArrayList<>();
        increasingNums.add(nums[0]);

        for (int i = 1; i < nums.length; i++) {
            if (nums[i] > increasingNums.get(increasingNums.size() - 1)) {
                increasingNums.add(nums[i]);
                continue;
            }
            int index = Collections.binarySearch(increasingNums, nums[i]);
            if (index < 0) {
                increasingNums.set(-(index + 1), nums[i]);
            }
        }

        return increasingNums.size();
    }
}
```

```java
// Time spend: 02:20
class Solution {
    public int lengthOfLIS(int[] nums) {
        List<Integer> increasingNums = new ArrayList<>();
        increasingNums.add(nums[0]);

        for (int i = 0; i < nums.length; i++) {
            if (nums[i] > increasingNums.get(increasingNums.size() - 1)) {
                increasingNums.add(nums[i]);
                continue;
            }
            int index = Collections.binarySearch(increasingNums, nums[i]);
            if (index < 0) {
                increasingNums.set(-index-1, nums[i]);
            }
        }

        return increasingNums.size();
    }
}
```