```java
// From start, if the value of next node is same value
// Then connect the current node to the next node
// Time complexity: O(N) -> N is number of node
// Space complexity: O(1)
// Time spend: 05:12
class Solution {
    public ListNode deleteDuplicates(ListNode head) {
        ListNode startNode = head;
        while (head != null) {
            while (head.next != null && head.val == head.next.val) {
                head.next = head.next.next;
            }
            head = head.next;
        }
        return startNode;
    }
}
```