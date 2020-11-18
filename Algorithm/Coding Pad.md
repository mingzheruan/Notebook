# Coding Pad

```JAVA


ListNode appendHead(ListNode head, int value) {
    ListNode newHead = new ListNode(value);
    newHead.next = head;
    return newHead;
}

ListNode appendTail(ListNode head, int value) {
    if (head == null) {
        return new ListNode(value);
    }
    
    ListNode add = new ListNode(value);
    ListNode cur = head;
    while (cur != null) {
        cur = cur.next;
    }
    cur.next = add;
    return head;
}
```

