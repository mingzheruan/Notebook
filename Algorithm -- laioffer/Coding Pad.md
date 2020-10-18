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



public void selectionSort(int array) {
  for (int i = 0; i < array.length - 1; i++) {
    int minIndex = 0;
    for (int j = i + 1; j < array.length; j++) {
      if (array[j] < array[minIndex]) {
        minIndex = j;
      }
    }
    Swap(array, minIndex, i);
  }
}
  
```

1		2		3		4		5		6		null

​								

​																

面试注释问题

BQ  

开头部分自我介绍

Jamboard

讲题可以举例子

