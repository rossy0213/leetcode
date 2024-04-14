```java
class Solution {
    public TreeNode sortedArrayToBST(int[] nums) {
         return convertSortedArrayToBST(nums, 0, nums.length - 1);
    }

    public TreeNode convertSortedArrayToBST(int[] nums, int start, int end) {
        if (start > end) {
            return null;
        }

        if (start == end) {
            return new TreeNode(nums[start]);
        }

        int mid = (start + end) / 2;
        TreeNode root = new TreeNode(nums[mid]);
        root.left = convertSortedArrayToBST(nums, start, mid - 1);
        root.right = convertSortedArrayToBST(nums, mid + 1, end);

        return root;
    }
}
```