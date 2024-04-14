```java
// Time spend: 02:11
class Solution {
    public int maxDepth(TreeNode root) {
        return maxDepthByDfs(root, 1);
    }

    public int maxDepthByDfs(TreeNode root, int currentDepth) {
        if (root == null) {
            return currentDepth - 1;
        }

        int nextDepth = currentDepth + 1;
        return Math.max(maxDepthByDfs(root.left, nextDepth),
            maxDepthByDfs(root.right, nextDepth));
    }
}
```

```java
// Time spend: 02:03
class Solution {
    public int maxDepth(TreeNode root) {
        return maxDepthByDfs(root, 1);
    }

    public int maxDepthByDfs(TreeNode root, int currentDepth) {
        if (root == null) {
            return currentDepth - 1;
        }

        int nextDepth = currentDepth + 1;
        return Math.max(maxDepthByDfs(root.left, nextDepth),
            maxDepthByDfs(root.right, nextDepth));
    }
}
```

```java
// Time spend: 01:42
class Solution {
    public int maxDepth(TreeNode root) {
        return maxDepthByDfs(root, 1);
    }

    public int maxDepthByDfs(TreeNode root, int currentDepth) {
        if (root == null) {
            return currentDepth - 1;
        }

        int nextDepth = currentDepth + 1;
        return Math.max(maxDepthByDfs(root.left, nextDepth), maxDepthByDfs(root.right, nextDepth));
    }
}
```