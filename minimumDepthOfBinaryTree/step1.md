```java
// Go thought the tree, by using BFS, once we find the first node that is leaf
// Then we just return it. No need to go thought all node
// Time complexity: O(N) N: number of node
// Time complexity: O(N) 
// Time spend: 09:51
class Solution {
    public int minDepth(TreeNode root) {
        if (root == null) {
            return 0;
        }

        Queue<TreeNode> queue = new LinkedList<>();
        queue.add(root);

        int currentDepth = 0;
        while (!queue.isEmpty()) {
            currentDepth++;
            
            int currentQueueSize = queue.size();
            for (int i = 0; i < currentQueueSize; i++) {
                TreeNode currentNode = queue.poll();
                if (currentNode.left == null && currentNode.right == null) {
                    return currentDepth;
                }
                if (currentNode.left != null) {
                    queue.add(currentNode.left);
                }
                if (currentNode.right != null) {
                    queue.add(currentNode.right);
                }
            }
        }

        return currentDepth;
    }
}
```