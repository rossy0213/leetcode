```java
// Go thought the tree
// Using dfs to visit all node
// Before visit the node, add parent val into children value
// If it's leaf then compare value with target
// Time complexity: O(N) N: number of nodes
// Space complexity: O(N) stack memory for dfs
// Time spend: 05:31
class Solution {
    public boolean hasPathSum(TreeNode root, int targetSum) {
        if (root == null) {
            return false;
        }

        if (root.left == null && root.right == null) {
            return targetSum == root.val;
        }
        if (root.left != null) {
            root.left.val += root.val;
        }
        if (root.right != null) {
            root.right.val += root.val;
        }

        return hasPathSum(root.left, targetSum) || hasPathSum(root.right, targetSum);
    }
}
```