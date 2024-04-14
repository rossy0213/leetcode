```java
// Create a dummy node and point next of itself to head
// So we can remove node from the first duplicated node without keeping the previous unique node
// Reference: https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii/solutions/2419088/very-easy-100-fully-explained-java-c-python-js-c-python3/
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        ListNode dummyHead = new ListNode(-1);
        dummyHead.next = head;
        ListNode current = dummyHead;

        while (current.next != null && current.next.next != null) {
            if (current.next.val == current.next.next.val) {
                int duplicatedVal = current.next.val;
                while (current.next != null && current.next.val == duplicatedVal) {
                    current.next = current.next.next;
                }
                continue;
            }
            current = current.next;
        }

        return dummyHead.next;
    }
}
```