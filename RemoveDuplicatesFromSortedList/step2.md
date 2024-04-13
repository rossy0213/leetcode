```java
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        ListNode currentNode = head;
        
        while (currentNode != null && currentNode.next != null) {
            if (currentNode.val == currentNode.next.val) {
                currentNode.next = currentNode.next.next;
                continue;
            }

            currentNode = currentNode.next;
        }
        
        return head;
    }
}
```