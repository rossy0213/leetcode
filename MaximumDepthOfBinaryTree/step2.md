```java
class Solution {
    public int maxDepth(TreeNode root) {
        return maxDepthFindByBfs(root);
    }

    public int maxDepthFindByDfs(TreeNode root) {
        if (root == null) {
            return 0;
        }
        
        return Math.max(maxDepthFindByDfs(root.left), maxDepthFindByDfs(root.right)) + 1;
    }

    // BFS
    // Time spend: 04:30
    public int maxDepth(TreeNode root) {
        if (root == null) {
            return 0;
        }

        Queue<Pair<TreeNode, Integer>> queue = new LinkedList<>();
        queue.add(new Pair(root, 1));

        int maxDepth = 1;
        while (!queue.isEmpty()) {
            Pair<TreeNode, Integer> current = queue.poll();
            maxDepth = Math.max(current.getValue(), maxDepth);
            
            if (current.getKey().left != null) {
                queue.add(new Pair(current.getKey().left, current.getValue() + 1));
            }
            if (current.getKey().right != null) {
                queue.add(new Pair(current.getKey().right, current.getValue() + 1));
            }
        }

        return maxDepth;
    }
}
```