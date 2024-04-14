```java
class Solution {
    public boolean hasPathSum(TreeNode root, int targetSum) {
        if (root == null) {
            return false;
        }
        
        // A little optimization
//        if (targetSum - root.val < 0) {
//            return false;
//        }
        
        if (root.left == null && root.right == null) {
            return targetSum == root.val;
        }
        
        int remainingTargetSum = targetSum - root.val;
        return hasPathSum(root.left, remainingTargetSum) 
                || hasPathSum(root.right, remainingTargetSum);
    }
}
```