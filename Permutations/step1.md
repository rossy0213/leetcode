```java
// Backtrack
// Need to go thought all element again and again
// For each step, we run loop again to try to add all patterns.
// Keep a boolean array to keep the indexes already used, if it's used then we skip to add
// Time complextity: O(N! * N(array list)) N: Number of nums
// Space complextity: O(N!) nPn
// Time spend: 04:12
class Solution {
    public List<List<Integer>> permute(int[] nums) {
        List<List<Integer>> res = new ArrayList<>();
        backtrack(res, new ArrayList<>(), nums, new boolean[nums.length]);
        return res;
    }

    private void backtrack(List<List<Integer>> res, List<Integer> tempList, int[] nums, boolean[] used) {
        if (tempList.size() == nums.length) {
            res.add(new ArrayList<>(tempList));
            return;
        }

        for (int i = 0; i < nums.length; i++) {
            if (used[i]) {
                continue;
            }
            tempList.add(nums[i]);
            used[i] = true;
            backtrack(res, tempList, nums, used);
            tempList.remove(tempList.size() - 1);
            used[i] = false;
        }
    }
}
```