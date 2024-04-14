```java
// Time spend: 02:30
class Solution {
    public int minDepth(TreeNode root) {
        if (root == null) {
            return 0;
        }

        Queue<Pair<TreeNode, Integer>> queue = new LinkedList<>();
        queue.add(new Pair(root, 1));

        while (!queue.isEmpty()) {
            Pair<TreeNode, Integer> current = queue.poll();
            TreeNode left = current.getKey().left;
            TreeNode right = current.getKey().right;
            if (left == null && right == null) {
                return current.getValue();
            }

            if (left != null) {
                queue.add(new Pair(left, current.getValue() + 1));
            }

            if (right != null) {
                queue.add(new Pair(right, current.getValue() + 1));
            }
        }

        return -1;
    }
}
```

```java
// Time spend: 02:31
class Solution {
    public int minDepth(TreeNode root) {
        if (root == null) {
            return 0;
        }

        Queue<Pair<TreeNode, Integer>> queue = new LinkedList<>();
        queue.add(new Pair(root, 1));

        while (!queue.isEmpty()) {
            Pair<TreeNode, Integer> current = queue.poll();
            TreeNode left = current.getKey().left;
            TreeNode right = current.getKey().right;
            if (left == null && right == null) {
                return current.getValue();
            }

            if (left != null) {
                queue.add(new Pair(left, current.getValue() + 1));
            }
            if (right != null) {
                queue.add(new Pair(right, current.getValue() + 1));
            }
        }

        return -1;
    }
}
```

```java
// Time spend: 02:10
class Solution {
    public int minDepth(TreeNode root) {
        if (root == null) {
            return 0;
        }

        Queue<Pair<TreeNode, Integer>> queue = new LinkedList<>();
        queue.add(new Pair(root, 1));

        while (!queue.isEmpty()) {
            Pair<TreeNode, Integer> current = queue.poll();
            TreeNode left = current.getKey().left;
            TreeNode right = current.getKey().right;
            
            if (left == null && right == null) {
                return current.getValue();
            } 

            if (left != null) {
                queue.add(new Pair(left, current.getValue() + 1));
            }
            if (right != null) {
                queue.add(new Pair(right, current.getValue() + 1));
            }
        }

        return -1;
    }
}
```