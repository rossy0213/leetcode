```java
class Solution {
    public int minDepth(TreeNode root) {
        if (root == null) {
            return 0;
        }

        Queue<Pair<TreeNode, Integer>> queue = new LinkedList<>();
        queue.add(new Pair(root, 1));

        while (!queue.isEmpty()) {            
            Pair<TreeNode, Integer> current = queue.poll();
            TreeNode leftNode = current.getKey().left;
            TreeNode rightNode = current.getKey().right;
            if (leftNode == null && rightNode == null) {
                return current.getValue();
            }

            if (leftNode != null) {
                queue.add(new Pair(leftNode, current.getValue() + 1));
            }
            if (rightNode != null) {
                queue.add(new Pair(rightNode, current.getValue() + 1));
            }
        }

        return -1;
    }

    // DFS 
    // If root is null, the depth will de decided by parent node, so return 0
    // If both of left and right is null, meaning is leaf then return 1
    // If on of the children is null, meaning the leaf in the other side
    // If both of left and right has node, meaning we need to go to both and take the smaller one.
    public int minDepth(TreeNode root) {
        if (root == null) {
            return 0;
        }
        if (root.left == null && root.right == null) {
            return 1;
        }

        if (root.left == null) {
            return minDepth(root.right) + 1;
        }

        if (root.right == null) {
            return minDepth(root.left) + 1;
        }

        return Math.min(minDepth(root.left), minDepth(root.right)) + 1;
    }
}
```