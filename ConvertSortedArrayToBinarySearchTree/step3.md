```java
// Time spend: 02:31
class Solution {
    public TreeNode sortedArrayToBST(int[] nums) {
        return convertSortedArrayToBst(nums, 0, nums.length - 1);
    }

    public TreeNode convertSortedArrayToBst(int[] nums, int l, int r) {
        if (l > r) {
            return null;
        }

        if (l == r) {
            return new TreeNode(nums[l]);
        }

        int mid = (l + r) / 2;
        TreeNode root = new TreeNode(nums[mid]);
        root.left = convertSortedArrayToBst(nums, l, mid - 1);
        root.right = convertSortedArrayToBst(nums, mid + 1, r);

        return root;
    }
}
```

```java
// Time spend: 01:42
class Solution {
    public TreeNode sortedArrayToBST(int[] nums) {
        return convertSortedArrayToBst(nums, 0, nums.length - 1);
    }

    public TreeNode convertSortedArrayToBst(int[] nums, int l, int r) {
        if (l > r) {
            return null;
        }
        if (l == r) {
            return new TreeNode(nums[l]);
        }

        int mid = (l + r) / 2;
        TreeNode root = new TreeNode(nums[mid]);
        root.left = convertSortedArrayToBst(nums, l, mid - 1);
        root.right = convertSortedArrayToBst(nums, mid + 1, r);

        return root;
    }
}
```

```java
// Time spend: 01:42
class Solution {
    public TreeNode sortedArrayToBST(int[] nums) {
        return convertSortedArrayToBst(nums, 0, nums.length - 1);
    }

    public TreeNode convertSortedArrayToBst(int[] nums, int l, int r) {
        if (l > r) {
            return null;
        }

        if (l == r) {
            return new TreeNode(nums[l]);
        }

        int mid = (l + r) / 2;
        TreeNode root = new TreeNode(nums[mid]);
        root.left = convertSortedArrayToBst(nums, l, mid - 1);
        root.right = convertSortedArrayToBst(nums, mid + 1, r);

        return root;
    }
}
```