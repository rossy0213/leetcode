```java
// Backtracking
// Generate all subsets and use a map to remove duplicate
// Sort it frist, if the previous number is same with current number meaning that the subproblem of 
// the current number will be already consider in the previous number. So, we skip
// It can reduce the space complextity for the map
// That will increase the time complexity but order wouldn't change because the overal time complexity will depends on biggest order(2 ** n)
// Time complexity: O(2 ** N * N(list copy)) N: number of nums
// Space complexity: O(2 ** N) result
// Time spend: 12:21
class Solution {
    public List<List<Integer>> subsetsWithDup(int[] nums) {
        Arrays.sort(nums);
        List<List<Integer>> res = new ArrayList<>();
        backtrack(res, new ArrayList<>(), nums, 0);
        return res;
    }

    private void backtrack(List<List<Integer>> res, List<Integer> tempList, int[] nums, int start) {
        res.add(new ArrayList<>(tempList));
        for (int i = start; i < nums.length; i++) {
            if (i > start && nums[i] == nums[i - 1]) {
                continue;
            }
            tempList.add(nums[i]);
            backtrack(res, tempList, nums, i + 1);
            tempList.remove(tempList.size() - 1);
        }
    }
}
```