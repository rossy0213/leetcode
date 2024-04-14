```java
// Create a hashSet to store all found node, if we find the same node again meaning there is a cycle then return true.
// Time complexity: O(N) N: number of node
// Space complexity: O(N)
// Time spent: 04:50
public class Solution {
    public boolean hasCycle(ListNode head) {
        Set<ListNode> foundNode = new HashSet<>();

        while (head != null) {
            if (foundNode.contains(head)) {
                return true;        
            } else {
                foundNode.add(head);
                head = head.next;
            }
        }

        return false;
    }
}
```