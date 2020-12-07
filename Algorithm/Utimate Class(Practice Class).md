# Utimate Class ( Aha moment)

## Class1: Classes, objects, and reference I

Student firstStudent = new Student("Tom");    

"firstStudent" is an reference. "new Student" is instantiation and it stored in heap. 

<br>

![Image](https://github.com/mingzheruan/Notebook/blob/master/Algorithm%20--%20laioffer/Image(Utimate%20Class)/UtimateClass01.png)

<br>

Object 上所有的field 都在heap上，field又指向同在field上的数据

<br>

where to store local variables:

+ primative: stack
+ **object: its reference stores in stack, the object self stores in heap.**

<br>

where to store fields:

+ primitive: heap

+ object: heap (**its reference stores in heap as well!!!**)

    <br>

**Java pass by value(copy), not by reference**

+   primitive type: copy of the value itself

+   object: copy of the object reference



## Class2: Classes, objects, and references - II

## static : 

Members (fields, methods, classes) belong to class, not object(instance)【一旦使用static，这个就是此class的共有属性，不在属于单个实例】

<br>

## Final:

Constants: "Once assigned, cannot be changed." 

Final class: A class that cannot be derived.

Final method: A method that cannot be overridden.（无法重写）

Final variable: A variable that once assigned, cannot be assigned again.

<br>

## object

+   the elements in the array still occupy consecutive memory space on the heap
+   "length" is a field of the array object
+   **array length cannot be changed after the array object is created. (final)**

<br>

## Class3: Practice Problems

**CART**

Clarification:

1.  应用题转化为算法题
2.  Input: int array, target: int
    1.  int array: not null, not empty, sorted/ascending/duplicate, positive number
    2.  target: int, positive
3.  Output (index):
    1.  no solution: return -1
    2.  multiple solutionL return any
    3.  一个solution: return index

<br>

Solution

1.  High level: why binary search？ 本质： 执行一套逻辑使得每次的搜索空间是上一次搜索空间的一半
2.  物理意义：过例子（画图）
3.  Case1,2,3,4
4.  时空复杂度 

<br>

Coding

1.  readable 
2.  format/style

<br>

Test

------------

Example:

**CART**

Clarification:

1.  应用题转化为算法题
2.  Input: int array, target: int
    1.  int array: null, empty, sorted/ascending/duplicate, positive number
    2.  target: int, positive
3.  Output (index):
    1.  no solution: return -1
    2.  multiple solution: return any
    3.  一个solution: return index

<br>

Solution

1.  High level: why binary search？ 本质： 执行一套逻辑使得每次的搜索空间是上一次搜索空间的一半
2.  物理意义：过例子（画图）
3.  时空复杂度：T: LogN

<br>

Code

```java
public class closest {
    public int closest(int[] array, int target) {
        if (array == null || array.length == 0) {
            return -1;
        }
        
        int left = 0;
        int right = array.length - 1;
        while (left < right - 1) {
            int mid = left + (right - left) / 2;
            if (array[mid] == target) {
                return mid;
            } else if (array[mid] < target) {
                left = mid;
            } else {
                right = mid;
            }
        }
        
        if (Math.abs(array[left] - target) <= Math.abs(array[right] - target)) {
            return left;
        }
        
        return right;
    }
}
```



<br>

Test

----------------

Example:

**CART**

Clarification:

1.  应用题转化为算法题
2.  Input: int array, target: int,  k: int
    1.  int array: null, empty, sorted/ascending/duplicate, positive number
    2.  target: int, positive
    3.  k: k>= 0
3.  Output (int array with value):
    1.  没有 solution: return empty array
    2.  k > array.length: return original full array
    3.  multiple solution: return any
    4.  一个solution: return int array with value
    5.  order?

<br>

Solution:

1.  High level: why binary search？ 本质： 执行一套逻辑使得每次的搜索空间是上一次搜索空间的一半
    1.  step1: find the closest index to the target
    2.  step2: expand from the closest index to both left/right side
2.  物理意义：过例子（画图）
3.  时空复杂度：T: LogN + K 

<br>

Code:

```java
1 3 5 9 11
l
    	r
output: [5, 3, 9]
T: 6, K = 4 -> 1, 3, 5, 9 or 3, 5, 9, 11
    

public int[] kClosest(int[] array, int target, int k) {
    if (array == null || array.length == 0) {
        return new int[0];
    }
    if (k == 0) {
        return new int[0];
    }
    if (k >= array.length) {
        return array;
    }
    
    int left = closest(array, target);
    int right = left + 1;
    int[] result = new int[k];
    for (int i = 0; i < k; i++) {
        if (right >= array.length || left >= 0 && Math.abs(array[left] - target <= Math.abs(array[right] - target))) {
            result[i] = array[left--];
        } else {
            result[i] = array[right++];
        }
    }
    return result;
}    
```



<br>

Test:

<br>

## Class4: Linked list and Java List

### array vs linked list Comparison

+   Memory Layout

    +   Array: consecutive allocated memory space, no **overhead**
    +   Linked List: non-consecutive, overhead of multiple objects with the "next" reference

+   (Random) access time? - get i th element

    +   Array: O(1) -> calculating the offset is O(1) int value = array[5];
    +   Linked List: O(n) worst case -> we can only traverse from the HEAD

+   Search time (non-sorted)?

    +   Array: O(n)
    +   Linked List: O(n)

    ====================================

    Search time (sorted)

    +   Array: O(logn) - binary search
    +   Linked List: O(n)
    +   Reason: random access time is different for array and list.

    ====================================

### Linked List Operations

length()

get(index)

appendHead()

appendTail()

<br>

head could be changed - we need to return the new head if changed

usually need to consider

+   head == null
+   head.next == null

while loop - we need to understand what is the terminate condition

<br>

linked list (自己拼的乐高小火车，车厢是ListNode)

vs

LinkedList（高铁)

<br>

### LinkedList in Java

```java
class ListNode<E> {
    E e;
    private ListNode<E> prev;
    private ListNode<E> next;
}

E cannot be a primitive type
```

**Interface  提要求**

LinkedList 不能失去对头的控制

快慢指针， N3更好（偶数）， 当将链表拆分为2半的时候，方便断开



## Class 5: Practice Problems

## ArrayList

### ArrayList is regarded as a **resizable** array.

+   maintain an array with potential unused cells
+   will expand the array if there is no unused cells available
    +   by replacing the maintained array with a new larger array (1.5 times larger by default)

```java
class ArrayList<E> {
    private E[] array; // the maintained array, the current maximum capacity is array.length;
    private int size; // the number of actually used cells in the maintained array
}
```



### 注意区分:

1.  size: 目前装进去的元素个数
2.  capacity: 能装元素个数的上限 -- unlimited
3.  current capacity: 能装元素个数目前的上限（不用extend的情况下） -- array.length

关系：size <= current capacity

### APIs:

get(int index): array[index], index: [0, size)

set(int index, E e): array[index] = e, index: [0, size)

size(): size

add(E e) 

### ArrayList vs LinkedList

1.  If you have a lot of **random access** operations, use ArrayList
2.  If you always **add/remove at the tail**, use ArrayList
    1.  when the **time complexity is similar** for using ArrayList and LinkedList, use ArrayList. (**Overhead and Locality**)
3.  **Stack** and **Vector** class are not recommended, whenever you need a vector, use ArrayList, whenever you need a Stack, use Deque(LinkedList, ArrayDeque).

## Class 6: Queue, Stack, and Deque

| 数据结构|  数据结构|  

|        ----:                       |               :----                 |

|        Queue                 |         Queue                   |



