```java
// First solution
// Go thought the linkedList from head to tail and store the duplicated values
// Then go thought the linkedList again to remove the duplicated ones.
// Time: O(N), Space: O(N)  N is number of Node

// Second solution
// Store the previous unique node,
// Go thought the list, When find the duplciated node, make a flag,
// Remove the duplicated node then link the previous unique node to the next Node
// Time complexity: O(N), 
// Space complexity: O(1)
// Time spend: 17:55
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        ListNode current = head;
        ListNode previousUniqueNode = null;

        boolean foundDuplicatedNode = false;
        while (current != null) {
            foundDuplicatedNode = false;
            while (current.next != null && current.val == current.next.val) {
                foundDuplicatedNode = true;
                current.next = current.next.next;
            }
            if (foundDuplicatedNode) {
                if (previousUniqueNode == null) {
                    head = current.next;
                } else {
                    previousUniqueNode.next = current.next;
                }
            }
            if (!foundDuplicatedNode) {
                previousUniqueNode = current;
            }
            current = current.next;
        }

        return head;
    }
}
```