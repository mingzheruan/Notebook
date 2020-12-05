# Remove Nth Node From End of List



```java
/*
Given a linked list, remove the nth node from the end of list and return its head.

Assumptions
If n is not valid, you do not need to do anything to the original list.
Try to do this in one pass.

Examples:

Given linked list: 1->2->3->4->5, and n = 2.

After removing the second node from the end, the linked list becomes 1->2->3->5.
*/

public ListNode removeNthFromEnd(ListNode head, int n) {
        // sanity check
        if (head == null) {
            return head;
        }

        // find the length of LinkedList
        ListNode dummy = new ListNode(0);
        dummy.next = head;
        ListNode cur = dummy;
        int length = -1;
        while (cur != null) {
            length++;
            cur = cur.next;
        }
        if (length < n || n <= 0) {
            return head;
        }

        // remove the (length - n)th element
        int count = length - n;
        ListNode pre = dummy;
        while(count > 0) {
            count--;
            pre = pre.next;
        }
        pre.next = pre.next.next;
        return dummy.next;
    }
    
    
```

### Important and difficult points: 

1. 注意边界问题


