```java
public class Solution {
    public boolean hasCycle(ListNode head) {
        Set<ListNode> visitedNode = new HashSet<>();

        while (head != null) {
            if (visitedNode.contains(head)) {
                return true;        
            }
            visitedNode.add(head);
            head = head.next;
        }

        return false;
    }
}
```

```java
// After checking solutions, found a faster O(1) space solution using two pointers
// Create 2 pointers, 1 pointer is trying to visit next node, and other pointer is trying to visit next next node
// If there is a cycle, the two-step pointer will eventually catch up with the slow pointer
//        Node1 -> Node2 -> Node3 -> Node4 -> Node5 -> Node2
// Index   0        1        2        3        4        5
//                  5        6        7        8        9
// Index of one-step pointer: 0(n1), 1(n2), 2(n3), 3(n4), 4(n5) 
// Index of two-step pointer: 0(n1), 2(n3), 4(n5), 6(n3), 8(n5)
// Time complexity: O(N) N: number of node
// Space complexity: O(1)
public class Solution {
    public boolean hasCycle(ListNode head) {
        ListNode oneStepNode = head;
        ListNode twoStepNode = head;

        while ((oneStepNode != null) && (twoStepNode != null) && (twoStepNode.next != null)) {
            oneStepNode = oneStepNode.next;
            twoStepNode = twoStepNode.next.next;

            if (oneStepNode == twoStepNode) {
                return true;
            }
        }

        return false;
    }
}
```

```java
// only need to check nullable condition for twoStepNode since it runs faster
public class Solution {
    public boolean hasCycle(ListNode head) {
        ListNode oneStepNode = head;
        ListNode twoStepNode = head;

        while ((twoStepNode != null) && (twoStepNode.next != null)) {
            oneStepNode = oneStepNode.next;
            twoStepNode = twoStepNode.next.next;

            if (oneStepNode == twoStepNode) {
                return true;
            }
        }

        return false;
    }
}
```

