```java
554. Generate LinkedList
  
Generate a linked list of length n, where the nodes contains numbers from 0 to n-1 in order. 

Assumption: n > 0.

Example:

n = 3

Answer: 0->1->2->null
  
  
  
  
  public class Solution {

		public ListNode generate(int n) {

		ListNode head = new ListNode(0);

		ListNode cur = head;

		for (int i = 1; i < n; i++) {

			ListNode node = new ListNode(n);

			cur.next = node;

			cur = cur.next;		

		}

		return head;

	}

}



class ListNode {

	int value;

	ListNode next;

	public ListNode (int value) {

		this.value = value;	

	}

}
  
```

public class Solution {

​	public ListNode generate(int n) {

​		ListNode head = new ListNode(0);

​		ListNode cur = head;

​		for (int i = 1; i < n; i++) {

​			ListNode node = new ListNode(n);

​			cur.next = node;

​			cur = cur.next;		

​		}



​	}

}



class ListNode {

​	int value;

​	ListNode next;

​	public ListNode (int value) {

​		this.value = value;	

​	}

}