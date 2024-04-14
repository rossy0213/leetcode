```java
// Use DFS, return depth when node don't have children
// Increse depth before visit child node
// Time complexity: O(N) N: number of node
// Space complexity: O(N)
// Time spend: 04:26
class Solution {
    public int maxDepth(TreeNode root) {
        if (root == null) {
            return 0;
        }
        return Math.max(maxDepth(root.left), maxDepth(root.right)) + 1;
    }

    // BFS
    // Time spend: 04:30
    public int maxDepthFindByBfs(TreeNode root) {
        if (root == null) {
            return 0;
        }
        
        Queue<TreeNode> queue = new LinkedList<>();
        queue.add(root);

        int maxDepth = 0;
        while (!queue.isEmpty()) {
            int queueSize = queue.size();
            for (int i = 0; i < queueSize; i++) {
                TreeNode curr = queue.poll();
                if (curr.left != null) {
                    queue.add(curr.left);
                }
                if (curr.right != null) {
                    queue.add(curr.right);
                }
            }
            maxDepth++;
        }

        return maxDepth;
    }
}
```