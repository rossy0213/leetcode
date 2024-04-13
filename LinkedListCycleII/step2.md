```java
// Memorize by muscle
public class Solution {
    public ListNode detectCycle(ListNode head) {
        ListNode oneStepNode = head;
        ListNode twoStepNode = head;

        while (twoStepNode != null && twoStepNode.next != null) {
            oneStepNode = oneStepNode.next;
            twoStepNode = twoStepNode.next.next;
            
            if (oneStepNode == twoStepNode) {
                break;
            }
        }
        if (twoStepNode == null || twoStepNode.next == null) {
            return null;
        }

        while (head != oneStepNode) {
            head = head.next;
            oneStepNode = oneStepNode.next;
        }

        return head;
    }
}
```