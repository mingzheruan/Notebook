# Experience (Aha-moment)

## General Experience

**写代码要分逻辑来写，不要将多重逻辑综合在一块写，否则会很难写以及很难读。**

## Binary Search

1. BinarySearch有两个难点：
   1. loop中循环的条件，这决定loop将会留有几个元素，但是有可能陷入死循环(使用left < right - 1这个条件不会陷入死循环，但需要后续判断两个元素的值；如果是left <= right 注意可能陷入死循环)
   2. 在调整mid与right、left的值时，需要注意是否有可能漏掉重要元素

2. BinarySearch中：
   
   1. 需要想target一定不在哪个区间内，并且排除这部分区域以减少搜索空间
   
3. BinarySearch套路:

    1. 定义左右边界

    2. while循环

        1. 定义mid的边界 mid  = left + (right - left) / 2

        2. 判断条件

            1. 情况一：left <= right 

                需判断 mid == target

                以及后续左右边界的变化

            2.  情况二： left < right - 1

                会保留两个元素，所以在判断完后续左右边界变化的同时，
            
                需另外判断这两个元素

<br>

Principles of Binary Search:

1.  We must guarantee that the search space decreases over time (after each iteration)
2.  We must guarantee that the target (if exists) cannot be ruled out accidentally, when we change the value of left or right (it is critical to define the rule about how to move the range for search)

----------------------

## BFS

### BFS-1 ()

1.  Data structure:
    1.  FIFO queue
    2.  Flag: whether i detected bubbles
2.  Expand: dequeue
3.  Generate:
    1.  when the flag is off, if the left child or the right child is null, set the flag
    2.  when the flag is on, if the left child or the right child is not null, return false
4.  Terminate
    1.  queue is empty or return false in the generation process



**Solution**

1.  BFS: expand + generate
2.  case 1: left = null, right = non-null, return false
3.  case 2: after detecting the first node that misses one child, then check whether all following nodes expanded to see whether they have any node generated (if any -> then false)

​				

### BFS-2 (Date structure: priority_queue)

经典算法: Dijkstra's Algorithm (runtime efficiency improvement: A* algorithm)

1.  Usages: Find the shortest path cost from a single node (source node) to any other nodes in that graph （点到面（==所有点）的最短距离算法）
2.  Data structure: Priority_queue(Min_Heap)

-----------------

## Recursion

1. subproblem
2. recursion role
3. base case

<br>

static belong to class, not ot object

<br>

物理意义：干什么的

---------------

## Practice Speaking

**CART**

Clarification & Assumption

1.  应用题转化为算法题
2.  Input: int array, target: int
    1.  int array: not null, not empty, sorted/ascending/duplicate, positive number
    2.  target: int, positive
3.  Output (index):
    1.  no solution: return -1
    2.  multiple solution: return any
    3.  一个solution: return index

<br>

Solution(example)

1.  High level: why binary search？ 本质： 执行一套逻辑使得每次的搜索空间是上一次搜索空间的一半
2.  物理意义（一一对应 开闭区间）：过例子（画图）
3.  Case1,2,3,4
4.  时空复杂度 

<br>

Coding

1.  readable 
2.  format/style

<br>

Test

<br>

------------



1. explain high-level idea by one sentence
2. explain every important data structure and physical significance of variable
3. explain the algorithm in mid-level, for example, initialization, how to do in each step, terminal condition, and base case + recursive rule
4. time complexity and space complexity



1.  Document your assumptions
2.  Explain your approach and how you intend to slove the problem
3.  Provide code comments where applicable
4.  Explain the big-O run time complexity of your solution. justfy your answer
5.  Identify andy additional data structures you used and justify why you used them
6.  only provide your best answer to each part of the question.

------------

## LinkedList

如果涉及对表头进行操作，一定要使用dummy.

当涉及到尾结点，需要仔细考虑NPE问题

