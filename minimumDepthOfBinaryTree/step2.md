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
}
```