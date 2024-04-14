```java
// Go thought both of the trees and sum the value of those two trees.
// For nodes missing on both trees -> null;
// For nodes missing on one side -> return node in another side
// For nodes on both trees -> replace it with sum of two node then go thought the children.
// Time complexity: O(M + N) M: number of nodes of root1, N: number of nodes of root2
// Space complexity: O(M + N) for memory stack
// Time spend: 14:00
class Solution {
    public TreeNode mergeTrees(TreeNode root1, TreeNode root2) {
        if (root1 == null && root2 == null) {
            return null;
        }
        if (root1 == null) {
            return root2;
        }
        if (root2 == null) {
            return root1;
        }
        
        root1.val = root1.val + root2.val;
        root1.left = mergeTrees(root1.left, root2.left);
        root1.right = mergeTrees(root1.right, root2.right);
        return root1;
    }
}
```