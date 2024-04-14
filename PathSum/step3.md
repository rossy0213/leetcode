```java
// Time spend; 01;30
class Solution {
    public boolean hasPathSum(TreeNode root, int targetSum) {
        if (root == null) {
            return false;
        }

        if (root.left == null && root.right == null) {
            return targetSum == root.val;
        }

        int remainingTargetSum = targetSum - root.val;
        return hasPathSum(root.left, remainingTargetSum)
                || hasPathSum(root.right, remainingTargetSum);
    }
}
```

```java
// Time spend: 01:10
class Solution {
    public boolean hasPathSum(TreeNode root, int targetSum) {
        if (root == null) {
            return false;
        }

        if (root.left == null && root.right == null) {
            return targetSum == root.val;
        }

        int remainingTargetSum = targetSum - root.val;
        return hasPathSum(root.left, remainingTargetSum)
            || hasPathSum(root.right, remainingTargetSum);
    }
}
```

```java
// Time spend: 00:50
class Solution {
    public boolean hasPathSum(TreeNode root, int targetSum) {
        if (root == null) {
            return false;
        }

        if (root.left == null && root.right == null) {
            return targetSum == root.val;
        }

        int remainingTargetSum = targetSum - root.val;
        return hasPathSum(root.left, remainingTargetSum)
                || hasPathSum(root.right, remainingTargetSum);
    }
}
```