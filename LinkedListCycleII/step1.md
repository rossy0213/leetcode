```java
// Create a hashMap to store all found node, if we find the same node again meaning there is a cycle then return itself.
// Time complexity: O(N) N: number of node
// Space complexity: O(N)
// Time spent: 2:20
// We can find the cycle by applying the solution of LinkedListCycle. 
// But can't find a way to find the beginning of the cycle. Hmmmmm
public class Solution {
    public ListNode detectCycle(ListNode head) {
        Set<ListNode> visitedNode = new HashSet<>();

        while (head != null) {
            if (visitedNode.contains(head)) {
                return head;
            }
            visitedNode.add(head);
            head = head.next;
        }

        return null;
    }
}
```

```java
// After checking solutions, found a faster O(1) space solution using two pointers
// reference: https://leetcode.com/problems/linked-list-cycle-ii/solutions/1701128/c-java-python-slow-and-fast-image-explanation-beginner-friendly/
// Hmmm, I'm not sure if I can come up this idea during the interview...
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

        while (oneStepNode != head) {
            head = head.next;
            oneStepNode = oneStepNode.next;
        }

        return oneStepNode;
    }
}
```