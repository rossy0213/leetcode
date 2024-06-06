```java
// Sort the nums first, if the previous number is same and we already used it the skip
// Time complextity: O(N! * N(new list)) N: number of nums
// Space complextity: O(N!)
// Time spend: 04:28
class Solution {
    public List<List<Integer>> permuteUnique(int[] nums) {
        Arrays.sort(nums);
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
            if (used[i] || (i > 0 && nums[i] == nums[i - 1] && used[i - 1])) {
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